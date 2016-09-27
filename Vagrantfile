# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "sbeliakou/centos-6.7-x86_64"
  config.vm.network "private_network", ip: "192.168.100.90"
  config.vm.provider "virtualbox" do |host|
	host.name="zabbix-server"
	host.cpus = 2
	host.memory = 2048
  end
  config.vm.hostname = "zabbix-server"
  
#  config.vm.provider "virtualbox" do |vb|
#    vb = config.vm.hostname
#  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = 'ansible/provision.roles.yml'
    ansible.verbose = 'vv'
  end
end
