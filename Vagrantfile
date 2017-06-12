# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/xenial64"
    config.vm.boot_timeout = 120
    config.vm.hostname = "jenkins"
    
    config.vm.provider "virtualbox" do |vb|
        vb.memory = 2048
        vb.cpus = 2
        vb.name = "jenkins"
    end        
end