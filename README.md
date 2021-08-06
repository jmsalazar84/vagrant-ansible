# Description
This is a demo repo using ansible with vagrant

## Technologies
- Vagrant
- Ansible
- Virtualbox

## Building
    vagrant up
    vagrant provision    

## SSH
To generate the ssh-config file:
```
    vagrant ssh-config > vagrant-ssh
```  

To connect to a machine using ssh-config file
```
    ssh -F vagrant-ssh machine-a
    ssh -F vagrant-ssh machine-b
```  

## Ansible Vault
Ansible Vault encrypts variables and files so you can protect sensitive content such as passwords or keys rather than leaving it visible as plaintext in playbooks or roles.

First, it is necessary to create an .vault_pass file with a demo password.
```
	echo 'demo' > .vault_pass
```

Decrypt vault file:
```
	ansible-vault decrypt ./vault.yml
```

Encrypt vault file:
```
	ansible-vault encrypt ./vault.yml
```

If you want to change the demo password, you should follow these steps:
1. decrypt the vault.yml file
2. change the password in .vault_pass
3. encrypt the vault.yml file
