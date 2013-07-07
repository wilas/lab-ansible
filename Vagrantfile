# -*- mode: ruby -*-
# vi: set ft=ruby :

# Docs: 
# machine settings: http://docs.vagrantup.com/v2/vagrantfile/machine_settings.html
# provider configruation: http://docs.vagrantup.com/v2/providers/configuration.html

Vagrant.configure("2") do |config|

  config.vm.define :skel do |node_config|
    vm_name= "skel"
    node_config.vm.box = "SL6"
    node_config.vm.hostname = "#{vm_name}.farm"

    node_config.vm.provider :virtualbox do |vb|
        vb.name = "#{vm_name}"
        vb.customize ["modifyvm", :id, "--memory", "512"]
    end

    node_config.vm.network :private_network, ip: "77.77.77.31"
    node_config.vm.synced_folder ".", "/vagrant"

    node_config.vm.provision :ansible do |ansible|
        # Ansible playbook
        ansible.playbook = "playbook.yaml"
        # Inventory file
        ansible.inventory_file = "ansible_inventory"
        # Show me more
        ansible.verbose = true
    end
  end
end
