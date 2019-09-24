# -*- mode: ruby -*-

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  config.vm.provider "virtualbox" do |vb|
    config.vm.network "forwarded_port", guest: 80, host: 8080, auto_correct: true
    config.vm.network "forwarded_port", guest: 443, host: 8443, auto_correct: true
    config.vm.network "forwarded_port", guest: 4063, host: 4063, auto_correct: true
    config.vm.network "forwarded_port", guest: 4064, host: 4064, auto_correct: true
  end

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = "2"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.galaxy_role_file = "requirements.yml"
  end
end
