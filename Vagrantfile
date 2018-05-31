# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.synced_folder ".", "/vagrant", type: "nfs", nfs_version: 4, nfs_udp: false, disabled: true

  config.vm.define "server-docker" do |server|
    server.vm.box = "debian/stretch64"
    server.vm.hostname = "server-docker"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "test.yml"
  end

end
