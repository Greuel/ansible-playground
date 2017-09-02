# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/centos7"
  config.ssh.insert_key = false
  config.vbguest.auto_update = true
  ## if you want more security (need to set up within your own box)
  # config.ssh.username = 'ansible'
  # config.ssh.password = 'ansible'

  # # Use your own box
  # # `vagrant up virtualbox --provider=virtualbox`
  # config.vm.define "virtualbox" do |virtualbox|
  #   virtualbox.vm.hostname = "virtualbox-centos7"
  #   virtualbox.vm.box = "yourbox.box"

    config.vm.provider :virtualbox do |v|
      v.name = "ansible-playground"
      v.gui = true
      v.memory = 1024
      v.cpus = 2
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--ioapic", "on"]
    end

    config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
  end
end
