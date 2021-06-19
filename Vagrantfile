# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|

    config.ssh.insert_key= false
    config.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--memory","256"]
    end

    
    
    
    #  LB for HA
    
    #config.vm.define "master-lb" do |worker|
    #    worker.vm.box="centos/7"
    #    worker.vm.hostname= "master-lb"
    #    worker.vm.network "public_network", ip: "192.168.0.6#{i}" ,bridge: "wlp2s0"
    #    worker.vm.provider "virtualbox" do |v|
    #        v.memory = 1024
    #        v.cpus = 1
    #    end       
    #end
    
    # Master
    (1..1).each do |i|
        config.vm.define "master-#{i}" do |worker|
           worker.vm.box="centos/7"
           worker.vm.hostname= "master-#{i}"
           worker.vm.network "public_network", ip: "192.168.0.8#{i}" ,bridge: "wlp2s0"
           worker.vm.provider "virtualbox" do |v|
              v.memory = 2024
              v.cpus = 2
           end
        end
    end

    #Worker
    (1..2).each do |i|
        config.vm.define "worker-#{i}" do |worker|
           worker.vm.box="centos/7"
           worker.vm.hostname= "worker-#{i}"
           worker.vm.network "public_network", ip: "192.168.0.7#{i}" , bridge: "wlp2s0"
           worker.vm.provider "virtualbox" do |v|
              v.memory = 2048
              v.cpus = 1
           end       
        end
    end  

end
