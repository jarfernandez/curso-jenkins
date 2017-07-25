# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    # Usa la misma key para cada maquina
    config.ssh.insert_key = false
    
    config.vm.define "jenkins" do |jk|
        jk.vm.box = "ubuntu/trusty64"
        jk.vm.boot_timeout = 120
        jk.vm.hostname = "jenkins"
    
        jk.vm.provider "virtualbox" do |vb|
            vb.memory = 2048
            vb.cpus = 2
            vb.name = "jenkins"
        end
        
        jk.vm.network "private_network", ip: "192.168.50.10"
        jk.vm.network "forwarded_port", host: 8080, guest:8080, autocorrect: true
        
        jk.vm.provision "ansible" do |ansible|
            ansible.playbook = "provision/install.yml"
            ansible.host_key_checking = false
            ansible.sudo = true
            ansible.tags = ['common', 'oracle-java8', 'jenkins']
        end
    end

    config.vm.define "tomcat" do |tc|
        tc.vm.box = "ubuntu/trusty64"
        tc.vm.boot_timeout = 120
        tc.vm.hostname = "tomcat"
    
        tc.vm.provider "virtualbox" do |vb|
            vb.memory = 1024
            vb.cpus = 1
            vb.name = "tomcat"
        end
    
        tc.vm.network "private_network", ip: "192.168.50.20"
        tc.vm.network "forwarded_port", host: 8090, guest:8080, autocorrect: true
    end
end