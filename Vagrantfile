# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "file:///Users/marcelo.felix/git/packer-templates/ubuntu20/builds/virtualbox-ubuntu20.box"
  #config.vm.box = "marcelofpfelix/ubuntu20"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true

  # virtualization config 
  config.vm.provider :virtualbox do |v|
    v.name = "kamailio"
    v.gui = false
    v.memory = 1024
    v.cpus = 1
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  # server config
  config.vm.define "kamailio" do |server|
    server.vm.hostname = "kamailio"
    server.vm.network "public_network", ip: "192.168.1.240" #, bridge: "en0: Wi-Fi (AirPort)"
  end

  # provisioner config
  config.vm.provision "ansible" do |a|
    a.compatibility_mode = "2.0"
    a.playbook = "main.yml"
    a.become = true
  end
end
