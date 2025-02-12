"auths": {
 "bastion.mirror.dev.mindsparks.io:8443": {
   "auth": "aW5pdDpHMU41aTlZZWQ3YjQwajN6NmYyRVdCcXlGRGhRUDh0eA==",
   "email": "yankova@hpe.com"
 },

======================================



kind: ImageSetConfiguration
apiVersion: mirror.openshift.io/v1alpha2
archiveSize: 4                                                      
storageConfig:                                                      
  registry:
    imageURL: bastion.mirror.dev.mindsparks.io:8443/mirror/oc-mirror-metadata                 
    skipTLS: false
mirror:
  platform:
    channels:
    - name: stable-4.17                                             
      type: ocp
    graph: true                                                     
  operators:
  - catalog: registry.redhat.io/redhat/redhat-operator-index:v4.17  
    packages:
    - name: serverless-operator                                     
      channels:
      - name: stable                                                
  additionalImages:
  - name: registry.redhat.io/ubi9/ubi:latest                        
  helm: {}