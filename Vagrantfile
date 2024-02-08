# -*- mode: ruby -*-
# vi: set ft=ruby :
# ansible file
# Object: test    vagrant with ansible
# Date:2023/02/08
# Author: Hamid Ftillou
###########################################################
$script =<<-SHELL
  #sudo apt update
  ls -al
SHELL
Vagrant.configure("2") do |config|
  config.vm.define "os" do |os|
    os.vm.box = "ubuntu/bionic64"
    os.vm.hostname = "bionic"
    os.vm.network "private_network", ip: "192.168.56.100"
    
    os.vm.provider "virtualbox" do |vb|
      vb.name = "bionic"
      vb.memory = "1024"
    end #provider
    
    config.vm.provision  "shell", inline: $script
    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "bionic.yml"
    end #provision
  end # define 
  
end # main

