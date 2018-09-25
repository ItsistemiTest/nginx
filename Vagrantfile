# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  
  config.vm.box = "hashicorp/precise32"
  config.vm.hostname = "web-dev"

  config.vm.provision "shell", path: "provision.sh"

  config.vm.network "private_network", ip: "192.168.56.10"
  config.vm.network "forwarded_port", guest: 80, host:8080, id: "nginx", auto_correct: true

  # disabling default share and defining which folders to share
  config.vm.synced_folder "./", "/vagrant", disabled: true
  # first which file-folder "www", and then absoulte location on host "/vagrant/www"
  config.vm.synced_folder "www", "/vagrant/www"
  config.vm.synced_folder "sites-enabled", "/vagrant/sites-enabled"

end
