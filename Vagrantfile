# -*- mode: ruby -*-
# vi: set ft=ruby :

# The most common configuration options are documented and commented below.
# For a complete reference, please see the online documentation at
# https://docs.vagrantup.com.

VAGRANTFILE_API_VERSION = '2'
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.ssh.insert_key = false
  config.vm.synced_folder '.', '/vagrant', disabled: true

  # boxes at https://vagrantcloud.com/search.
  config.vm.box = 'bento/ubuntu-22.04-arm64'

  config.vm.provider 'parallels' do |prl|
    # prl.name = 'Ansible X Vagrant Lab'
    prl.memory = 2048
    prl.cpus = 2
    prl.update_guest_tools = false
  end

  ##### ANSIBLE Provision configuration
  config.vm.provision 'ansible' do |ansible|
    ansible.playbook = 'playbook.yml'
  end

  # Application server 1.
  config.vm.define 'app1' do |app|
    app.vm.hostname = 'orc-app1.test'
    app.vm.network :private_network, ip: '192.168.60.4'
  end
  # Application server 2.
  config.vm.define 'app2' do |app|
    app.vm.hostname = 'orc-app2.test'
    app.vm.network :private_network, ip: '192.168.60.5'
  end
  # Database server.
  config.vm.define 'db' do |db|
    db.vm.hostname = 'orc-db.test'
    db.vm.network :private_network, ip: '192.168.60.6'
  end
end
