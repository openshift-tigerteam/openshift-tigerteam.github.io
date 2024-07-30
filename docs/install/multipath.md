# Multipath

```
apiVersion: machineconfiguration.openshift.io/v1
kind: MachineConfig
metadata:
    name: 99-worker-multipathd-config
    labels:
        machineconfiguration.openshift.io/role: worker
spec:
    config:
        ignition:
            version: 3.2.0
        systemd:
            units:
            - enabled: true
            name: multipathd.service
        storage:
            files:
            - filesystem: root
              mode: 420
              path: /etc/multipath.conf
            contents:
                inline: |
                    # For a complete list of the default configuration values, run either:
                    #  multipath -t
                    # or
                    #  multipathd show config
                    # For a list of configuration options with descriptions, see the
                    # multipath.conf man page.
                    defaults {
                        user_friendly_names yes
                        find_multipaths yes
                    }
                    # include devices for exclusion
                    # see 
                    blacklist {
                    }
```