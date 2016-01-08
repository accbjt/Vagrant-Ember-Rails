# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "ember-development"
  config.vm.network "private_network", ip: "192.168.33.22"
  config.vm.network :forwarded_port, guest: 4200, host: 4200, auto_correct: true
  config.vm.network :forwarded_port, guest: 35729, host: 35729, auto_correct: true

  config.vm.synced_folder "./sites", "/home/vagrant/sites"

  config.vm.provision :shell, path: "./vagrant-setup/mysql-setup.sh"
  config.vm.provision :shell, path: "./vagrant-setup/install-rvm.sh", args: "stable", privileged: false
  config.vm.provision :shell, path: "./vagrant-setup/install-ruby.sh", args: "2.2.3 rails haml", privileged: false
  config.vm.provision :shell, path: "./vagrant-setup/install-git.sh", privileged: false

end
