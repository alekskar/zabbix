Vagrant.configure(2) do |config|
  config.vm.box = "sbeliakou/centos-6.7-x86_64"
  config.vm.network "private_network", ip: "192.168.100.94"
  config.vm.provider "virtualbox" do |host|
	host.name="ldapserver"
	host.cpus = 2
	host.memory = 2048
  end
  config.vm.hostname = "ldapserver"
  
#  config.vm.provider "virtualbox" do |vb|
#    vb = config.vm.hostname
#  end

  config.vm.provision "shell", inline: <<-SHELL
  echo "Provisioning: hosts is ready for provisioning"
  yum install -y openldap-servers openldap-clients
  chown -R ldap:ldap /var/lib/ldap
  yum install -y http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm
  yum install -y phpldapadmin
  SHELL

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = 'ansible/provision.roles.yml'
    ansible.verbose = 'vv'
  end

end
