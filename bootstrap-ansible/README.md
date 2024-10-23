# Bootstrap GitOps

Use Ansible to bootstrap GitOps

## Variables

Need to edit `host_vars/localhost/connection.yaml` to name the cluster.

Edit `host_vars/localhost/openshift-gitops.yaml` to set the Repo and kustomize path for the **application of applications".

## Ansible and CSB

On a Fedora CSB, need to edit `/etc/ansible/hosts` and comment out the `[localhost]` block

## Running it

Need to extract the CA certificates from the cluster to run the bootstrap:

`$ oc get configmap -n openshift-kube-apiserver  kube-root-ca.crt -o jsonpath='{.data.ca\.crt}' > kube-root-ca.crt`

Note that the filename is referenced in `connection.yaml`.
