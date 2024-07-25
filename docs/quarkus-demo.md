# Quarkus Demo Examples

<a href="https://github.com/openshift-tigerteam/quarkus-demo-api" target="_blank">https://github.com/openshift-tigerteam/quarkus-demo-api</a>

To deploy using static manifests:
```shell
oc new-project quarkus-demo
oc apply -f https://raw.githubusercontent.com/openshift-tigerteam/quarkus-demo-api/main/deploy/manifests/deploy.yml
```

You can also deploy using s2i, in multiple ways. 

