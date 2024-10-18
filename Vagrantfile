# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
# Configuración del DNS
  config.vm.box = "debian/bookworm64"
  config.vm.hostname = "tierra.sistema.test"
  config.vm.network = "private_network", ip:"192.168.57.103"

  #Sincronizamos carpetas.
  config.vm.synced_folder



end
