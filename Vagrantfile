# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.define "tower" do |c|

    c.vm.provider :libvirt do |libvirt|
      libvirt.memory = 2048
    end

    c.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
    end

    c.vm.box = "centos/7"
    c.vm.hostname = "tower.example.com"
    c.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.limit = "all"
      ansible.playbook = "playbook.yml"
    end

  end

end
