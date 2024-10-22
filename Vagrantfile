# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
# Configuración del DNS
  config.vm.box = "debian/bookworm64"
  config.vm.hostname = "tierra.sistema.test"
  config.vm.network = "private_network", ip:"192.168.57.103", netmask:"24"

  #Instalar en el servidor maestro copn Bind9
  config.vm.provision "shell", inline: <<-SHELL
  apt-get update
  apt-get install -y bind9 bind9utils bind9-doc¡

  #Configurar el DNS mercurio (imaginario)
  #config.vm.define "mercurio" do |mercurio|
  #mercurio.vm.box = "debian/bookworm64"
  #mercurio.vm.hostname = "mercurio.sistema.test"
  #mercurio.vm.network "private_network", ip: "192.168.57.101"

  #Configurar el DNS venus
  config.vm.define "venus" do |venus|
  venus.vm.box = "debian/bookworm64"
  venus.vm.hostname = "venus.sistema.test"
  venus.vm.network "private_network", ip: "192.168.57.102"

  # Configuración DNS tierra
  config.vm.define "tierra" do |tierra|
  tierra.vm.box = "debian/bookworm64" 
  tierra.vm.hostname = "tierra.sistema.test"
  tierra.vm.network "private_network", ip: "192.168.57.103"
  
  # Configuración DNS marte (imaginario)
  #config.vm.define "marte" do |marte|
  #tierra.vm.box = "debian/bookworm64" 
  #tierra.vm.hostname = "marte.sistema.test"
  #tierra.vm.network "private_network", ip: "192.168.57.104"

  
  #Reiniciar el servicio Bind9
  systemctl restart bind9
  SHELL


end
