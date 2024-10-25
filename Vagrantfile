# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Configuración del DNS
  config.vm.box = "debian/bookworm64"
  config.vm.hostname = "tierra.sistema.test"
  config.vm.network "private_network", ip: "192.168.57.103"

  # Instalamos en el servidor maestro con Bind9
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y bind9 bind9utils bind9-doc

    # Copiamos los archivos de configuración del DNS a sus directorios correspondientes
    cp /vagrant/named.conf.options /etc/bind/named.conf.options

    # Reiniciar el servicio Bind9
    systemctl restart bind9
  SHELL

  # Configurar el DNS mercurio (imaginario)
  # config.vm.define "mercurio" do |mercurio|
  #   mercurio.vm.box = "debian/bookworm64"
  #   mercurio.vm.hostname = "mercurio.sistema.test"
  #   mercurio.vm.network "private_network", ip: "192.168.57.101"
  # end

  # Configurar el DNS venus
  config.vm.define "venus" do |venus|
    venus.vm.box = "debian/bookworm64"
    venus.vm.hostname = "venus.sistema.test"
    venus.vm.network "private_network", ip: "192.168.57.102"
  end

  # Configuración DNS tierra
   config.vm.define "tierra" do |tierra|
   tierra.vm.box = "debian/bookworm64"
   tierra.vm.hostname = "tierra.sistema.test"
   tierra.vm.network "private_network", ip: "192.168.57.103"
   end

  # Configuración DNS marte (imaginario)
  # config.vm.define "marte" do |marte|
  #   marte.vm.box = "debian/bookworm64"
  #   marte.vm.hostname = "marte.sistema.test"
  #   marte.vm.network "private_network", ip: "192.168.57.104"
  # end
end

