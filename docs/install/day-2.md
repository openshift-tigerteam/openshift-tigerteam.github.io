## Day 2 Tasks

<a href="https://docs.openshift.com/container-platform/4.16/web_console/customizing-the-web-console.html#creating-custom-notification-banners_customizing-web-console" target="_blank">
Customize the WebUI - Mark the UI as a sandbox
</a>

```
apiVersion: console.openshift.io/v1
kind: ConsoleNotification
metadata:
  name: sandbox-notification
spec:
  text: SANDBOX
  location: BannerTop 
  color: '#fff'
  backgroundColor: '##6e0101'
```

<a href="https://docs.redhat.com/en/documentation/red_hat_openshift_data_foundation/4.15/html/deploying_openshift_data_foundation_using_bare_metal_infrastructure/deploy-using-local-storage-devices-bm" target="_blank">Install ODF</a>

<a href="https://docs.openshift.com/container-platform/4.15/registry/configuring-registry-operator.html" target="_blank">Configure the Registry</a>

<a href="https://docs.openshift.com/container-platform/4.16/security/certificates/replacing-default-ingress-certificate.html" target="_blank">Red Hat OpenShift cert-manager - Replace Certificates</a>

<a href="https://docs.openshift.com/container-platform/4.16/virt/install/installing-virt.html" target="_blank">Install OpenShift Virtualization</a>
* <a href="https://docs.openshift.com/container-platform/4.16/virt/post_installation_configuration/virt-post-install-network-config.html#virt-post-install-network-config" target="_blank">OCPv post install - NMState Operator and SR-IOV Operators</a>
* <a href="https://docs.redhat.com/en/documentation/migration_toolkit_for_virtualization/2.6/html/installing_and_using_the_migration_toolkit_for_virtualization/installing-the-operator_mtv#installing-mtv-operator_web"  target="_blank">Migration Toolkit for Virtualization</a>

### Other Tools

<a href="https://github.com/m88i/nexus-operator" target="_blank">Nexus Operator</a>