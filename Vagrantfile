# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  
  config.vm.box = "ubuntu/trusty64"
  #config.vm.network "forwarded_port", guest: 5000, host: 5000
  config.vm.synced_folder "~/ansible-code", "/etc/ansible"

$script = <<SCRIPT

sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get install vim -y
sudo apt-get install curl -y
sudo apt-get install unzip -y
sudo apt-get install software-properties-common -y
sudo apt-get install ansible -y
sudo apt-get update

SCRIPT

  config.vm.provision "shell", inline: $script, privileged: false

end
