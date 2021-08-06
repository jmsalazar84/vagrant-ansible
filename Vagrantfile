# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/8"
  config.vbguest.installer_options = { allow_kernel_upgrade: true }
  
  config.vm.define "machine-01" do |machine|
    machine.vm.hostname = "machine-01"
    machine.vm.network "private_network", ip: "192.168.10.10"
  end
  
  config.vm.define "machine-02" do |machine|
    machine.vm.hostname = "machine-02"
    machine.vm.network "private_network", ip: "192.168.10.11"

    machine.vm.provision :ansible do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.limit = "all"
      ansible.playbook = "playbook.yml"
      # ansible.ask_vault_pass = true
      ansible.vault_password_file = ".vault_pass"
      ansible.verbose = 'v' 
    end
  end
end
