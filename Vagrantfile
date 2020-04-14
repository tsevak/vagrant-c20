# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # General Vagrant VM configuration.
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provider :virtualbox do |v|
    v.memory = 1024
    v.cpus = 2
    v.linked_clone = true
  end

# Master node
  config.vm.define "master" do |master|
    master.vm.hostname = "master.local"
    master.vm.network "public_network",bridge: "en9: Targus USB3.0 DV2K Dock w Power", ip: "192.168.178.100"
  end

# Node 1
  config.vm.define "node1" do |node1|
    node1.vm.hostname = "node1.local"
    node1.vm.network "public_network",bridge: "en9: Targus USB3.0 DV2K Dock w Power", ip: "192.168.178.101"
  end

# Node 2 
  config.vm.define "node2" do |node2|
    node2.vm.hostname = "node2.local"
    node2.vm.network "public_network",bridge: "en9: Targus USB3.0 DV2K Dock w Power", ip: "192.168.178.102"
  end
    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansi-1.yml"
      ansible.compatibility_mode = "2.0"
    end    
end 

