# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.define "docker-host" do |c|
    c.vm.box = "ubuntu/xenial64"
    c.vbguest.installer_options = { allow_kernel_upgrade: true }
    c.vm.box_check_update = false
    c.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
    c.vm.network "private_network", ip: "192.168.33.10"
    c.vm.synced_folder "./data", "/vagrant_data"
    c.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = "2"
    end
    c.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get remove --purge -y docker docker-engine docker.io containerd runc
      apt-get install -y apt-transport-https ca-certificates curl gnupg-agent software-properties-common
      curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -
      add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
      apt-get update
      apt-get install -y docker-ce docker-ce-cli containerd.io
      usermod -aG docker vagrant
    SHELL
  end
end
