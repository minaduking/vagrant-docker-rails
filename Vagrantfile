# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define :docker do |node|
    node.vm.box = "xenial64"
    node.vm.network "private_network", ip: "192.168.200.10"
    node.vm.synced_folder "./projects", "/var/projects", owner: 'root', group: 'root'
    node.vm.provision :ansible_local do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.install = true
      ansible.verbose = true
      ansible.limit = "all"
    end
  end
end
