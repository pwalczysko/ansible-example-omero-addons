# -*- mode: ruby -*-

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  config.vm.define "omero" do |omero|
    omero.vm.provider "virtualbox" do |vb|
      omero.vm.network "forwarded_port", guest: 80, host: 8080, auto_correct: true
      omero.vm.network "forwarded_port", guest: 443, host: 8443, auto_correct: true
      omero.vm.network "forwarded_port", guest: 4063, host: 4063, auto_correct: true
      omero.vm.network "forwarded_port", guest: 4064, host: 4064, auto_correct: true
    end

    omero.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = "2"
    end

    omero.vm.hostname = "omero"
  end

  ## Uncomment this to automatically run Ansible
  ## You can re-run the Ansible provisioner after the VM has started:
  ## vagrant provision
  # config.vm.provision "ansible" do |ansible|
  #   ansible.playbook = "playbook.yml"
  #   ansible.galaxy_role_file = "requirements.yml"
  #   ansible.groups = {
  #     "omero-public" => ["omero"]
  #   }
  # end
end
