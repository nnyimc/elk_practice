# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
  config.vm.define "elastic" do |subconfig|
    subconfig.vm.box = "ubuntu/xenial64"
    subconfig.vm.hostname = "elastic"
    subconfig.vbguest.installer_options = {allow_kernel_upgrade: true}
    subconfig.vm.network "private_network", ip: "192.168.33.100"
    subconfig.vm.synced_folder ".", "/vagrant", type: "rsync", rsync__exclude: ".git/"
    subconfig.vm.provider "virtualbox" do |vb|
      vb.memory = "8000"
    end
  end

  config.vm.define "logstash" do |subconfig|
    subconfig.vm.box = "ubuntu/xenial64"
    subconfig.vbguest.installer_options = {allow_kernel_upgrade: true}
    subconfig.vm.hostname = "logstash"
    subconfig.vm.network "private_network", ip: "192.168.33.200"
    subconfig.vm.synced_folder ".", "/vagrant", type: "rsync", rsync__exclude: ".git/"
    subconfig.vm.provider "virtualbox" do |vb|
      vb.memory = 6000
    end
  end
  
  config.vm.define "kibana" do |subconfig|
    subconfig.vm.box = "ubuntu/xenial64"
    subconfig.vbguest.installer_options = {allow_kernel_upgrade: true}
    subconfig.vm.hostname = "kibana"
    subconfig.vm.network "private_network", ip: "192.168.33.233"
    subconfig.vm.synced_folder ".", "/vagrant", type: "rsync", rsync__exclude: ".git/"
    subconfig.vm.provider "virtualbox" do |vb|
      vb.cpus = 2
      vb.memory = 6000
    end
  end

end
