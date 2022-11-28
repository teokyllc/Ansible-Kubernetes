# Ansible-Kubernetes
An Ansible playbook to create a local Kubernetes instance.<br>

<b>Features:</b><br>

* Flannel CNI
* Metal LB
* Cert-manager with Hashicorp Vault issuer
* Istio
* Argo CD & Argo Rollouts
* Github Actions Runners 


Copy your SSH key to the target host prior to running playbook.<br>
```
ssh-keygen
ssh-copy-id 192.168.1.5
```
<br>

This playbook has dependency on the kubernetes.core Ansible module.
```
ansible-galaxy collection install kubernetes.core


ansible-playbook -K -i inventory k8s-single-node.yaml
```