# mysql-static-nfsvol
Example of a Deployment Configuration and Template using the OpenShift MySQL with Persistence Container Image, where the Persistent Volume Claim has been replaced with a Static NFS Server and Mount Path.   This is potentially useful where a true "Cloud Storage" allocation paradigm may not support Legacy Application and data availability constraints, and the allocation of storage needs to be managed outside of OpenShift.  In the provided examples the **template.spec.volumes stanza** of the pod definition was changed.

*Example YAML*
```yaml
      volumes:
        -
          name: mysql-data
          nfs:
            server: 127.0.0.1
            path: /mnt/openshift/pv0004
````
