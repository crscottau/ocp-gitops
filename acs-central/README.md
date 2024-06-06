# Create declarative config 

`$ oc create configmap declarative-configurations --from-file acs-central-declarative-auth-provider.yaml --namespace=central --dry-run=client -o yaml> acs-central-declarative-configmap.yaml`