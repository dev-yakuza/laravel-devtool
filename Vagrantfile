# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-16.04"

  config.vm.provider :virtualbox do |vb|
    vb.name = "laravel-devtool"
  end
  config.vm.network "forwarded_port", guest: 80, host: 80
  config.vm.network "forwarded_port", guest: 8080, host: 8080

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install software-properties-common
    sudo apt-add-repository --yes --update ppa:ansible/ansible
    sudo apt-get install ansible --yes
    sudo ansible-playbook /vagrant/ansible/playbook.yml
  SHELL

  config.trigger.after :up do |trigger|
    trigger.name = "trigger Docker after Vagrant Up"
    trigger.run_remote = {inline: "sudo ansible-playbook /vagrant/ansible/playbook.yml --tags 'docker'"}
  end

  config.vm.synced_folder ".", "/vagrant"
end
