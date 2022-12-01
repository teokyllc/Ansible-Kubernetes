# Ansible-Kubernetes
An Ansible playbook to create a local Kubernetes instance.<br>

<b>Features:</b><br>

* Flannel CNI
* Metal LB
* Cert-manager with Hashicorp Vault issuer
* Istio
* Argo CD & Argo Rollouts
* Github Actions Runners 


Copy your SSH key to the target host prior to running playbook if running manually, otherwise add the Vault CA cert to SSH config.<br>
```
ssh-keygen
ssh-copy-id 192.168.1.5

or

sudo curl -o /etc/ssh/trusted-user-ca-keys.pem https://vault.teokyllc.internal:8200/v1/ssh-client-signer/public_key
echo 'TrustedUserCAKeys /etc/ssh/trusted-user-ca-keys.pem' | sudo tee -a /etc/ssh/sshd_config
sudo systemctl restart sshd
sudo useradd ansible
echo 'ansible ALL=(ALL) NOPASSWD: ALL' | sudo tee -a /etc/sudoers.d/ansible
```
<br>

This playbook has dependency on the kubernetes.core Ansible module.
```
ansible-galaxy collection install kubernetes.core


ansible-playbook -K -i inventory k8s-single-node.yaml
```