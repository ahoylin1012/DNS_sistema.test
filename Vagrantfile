# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
# Configuración del DNS
  config.vm.box = "debian/bookworm64"
  config.vm.hostname = "tierra.sistema.test"
  config.vm.network = "private_network", ip:"192.168.57.103"

  #Instalar en el servidor maestro copn Bind9
  config.vm.provision "shell", inline: <<-SHELL
  apt-get update
  apt-get install -y bind9 bind9utils bind9-doc
              


end
