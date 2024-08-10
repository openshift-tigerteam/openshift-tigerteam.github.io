# Tools

## Network Tools in a Pod
```
apiVersion: v1
kind: Pod
metadata:
  name: network-multitool
  namespace: default
spec:
  containers:
    - name: network-multitool
      image: wbitt/network-multitool
```