# Busybox Examples for OpenShift

## Busybox as a Webserver

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: busybox-http-deployment
  labels:
    app: busybox-http
spec:
  replicas: 2
  selector:
    matchLabels:
      app: busybox-http
  template:
    metadata:
      labels:
        app: busybox-http
    spec:
      containers:
      - name: busybox-http
        image: busybox
        command:
          - sh
          - -c
          - |
            mkdir -p /tmp/www
            echo "<!DOCTYPE html><html lang=\"en\"><head><meta charset=\"UTF-8\"><title>Busybox HTTP Server</title></head><body><h1>Welcome to the Busybox HTTP Server</h1><p>This is a simple HTML page served by Busybox.</p></body></html>" > /tmp/www/index.html
            httpd -f -v -p 8080 -h /tmp/www
        ports:
        - containerPort: 8080
---
apiVersion: v1
kind: Service
metadata:
  name: busybox-service
  labels:
    app: busybox-http
spec:
  selector:
    app: busybox-http
  ports:
    - protocol: TCP
      port: 8080
      targetPort: 8080
---
kind: Route
apiVersion: route.openshift.io/v1
metadata:
  name: busybox-route
  labels:
    app: busybox-http
spec:
  to:
    kind: Service
    name: busybox-service
    weight: 100
  port:
    targetPort: 8080
  tls:
    termination: edge
    insecureEdgeTerminationPolicy: Redirect
  wildcardPolicy: None
```