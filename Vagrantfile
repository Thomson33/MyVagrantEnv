# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "debian/buster64"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  config.vm.box_check_update = false
  
  config.vm.provider "virtualbox" do |vb|
     # Customize the amount of memory on the VM:
     vb.memory = "1024"
  end

  config.vm.hostname = "myenv"
  
  config.vm.synced_folder ".", "/vagrant", type: "rsync"
  
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  
  config.vm.network "private_network", ip: "192.168.10.10" 

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
	# Install standarts and requires packages
    apt-get install curl wget vim nano ncdu net-tools apt-transport-https ca-certificates gnupg2 software-properties-common -y
	# Install Ansible
	echo "deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main" >> /etc/apt/sources.list
	apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 93C4A3FD7BB9C367
    apt-get update
    apt-get install ansible -y
	# Install Docker
	curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
	apt-key fingerprint 0EBFCD88
	add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"
	apt-get update
	apt-get install docker-ce docker-ce-cli containerd.io -y
	# SSH keys
	ssh-keygen -b 4096 -t rsa -f /vagrant/my_key -q -P ""
	mv /vagrant/my_key.pub /vagrant/authorized_keys
	chown vagrant:vagrant /vagrant/my_key
  SHELL
end
