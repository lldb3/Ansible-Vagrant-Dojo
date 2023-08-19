# Ansible X Vagrant Lab

### Docs for vagrant parallels config

https://parallels.github.io/vagrant-parallels/docs/configuration.html


### Usage

Adding the box to the vagrant repo and init the Vagrantfile if it doesn't exist
```shell
vagrant box add bento/ubuntu-22.04-arm64
vagrant init bento/ubuntu-22.04-arm64
```

```
## provision the VM
vagrant up 
## destroy the vm
vagrant destroy
```