# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "attacker" do |app|
    app.vm.box = "kalilinux/rolling"
    app.vm.hostname = "attacker"
    app.vm.network "private_network", ip: "192.168.56.200"
    app.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.memory = "1024"
    end
    app.vm.provision "shell", inline: <<-SHELL
      echo 'alias cls="clear"' >> .bashrc
      echo 'alias ll="ls -la"' >> .bashrc
    SHELL
    app.vm.provision "shell", run: "always", inline: <<-SHELL
      bash
    SHELL
  end
end
