# Deploy one Vault node and 3 Consul nodes on EC2 instances
## Structure of repository
- hosts - modify this file and paste IP addresses of your instances and ssh keys
- main.yml - main Ansible file for deploy Vault and Consul
- roles
  - vault - contains configuraion files for Vault role
  - consul - contains configuraion files for Consul role

> How to use

Modify **host** and paste IP addresses of your instances and ssh keys.
IP addresses should be public, and ssh keys had read only permissions.
```shell
export ANSIBLE_HOST_KEY_CHECKING=False
ansible-playbook -i hosts -u ec2-user main.yml
```

After execution output shows commands that should be runs on Vault node.
Expl.
```shell
export VAULT_ADDR=http://{vault_address}:8200
vault operator init
export VAULT_TOKEN={vault_token}
```
