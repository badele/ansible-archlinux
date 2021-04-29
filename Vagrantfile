# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "badele/ansiblearch"
  config.vm.synced_folder ".", "/vagrant", type: "rsync", rsync__exclude: ".git/"
  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = true
    # Videoram
    vb.customize ["modifyvm", :id, "--vram", "128"]
  end

  config.vm.provision "ansible_local" do |ansible|

    # Verbose ansible output
    ansible.verbose = "v"

    # set host for ansible scope (only use this host, it use --limit ansible option)
    config.vm.define "vagrant"

    ansible.galaxy_role_file = "ansible/galaxy_requirements.yml"
    ansible.galaxy_roles_path = "ansible/.galaxy"

    ansible.inventory_path = "/vagrant/ansible/inventory/hosts.yml"
    ansible.playbook = "/vagrant/ansible/dev-i3.yml"
  end
end
