# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "server" do |server|
    server.vm.box = "TFDuesing/Fedora-20"
    server.vm.network "private_network", ip: "192.168.20.93"
  end

  config.vm.provision "ansible_local", run: "always" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.groups = {
      "scripts-servers" => ["server"],
    }
    ansible.verbose = true
  end
end
