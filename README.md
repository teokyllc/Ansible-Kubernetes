# Ansible-Kubernetes
Copy SSH keys to a target host.<br>
```
ssh-keygen
ssh-copy-id 192.168.1.5
```
<br>

This playbook has dependency on the kubernetes.core module.
```
ansible-galaxy collection install kubernetes.core


ansible-playbook -K -i inventory k8s-single-node.yaml
```