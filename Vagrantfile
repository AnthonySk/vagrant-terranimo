# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "hashicorp-education/ubuntu-24-04"
  config.vm.box_version = "0.1.0"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  config.vm.synced_folder "C:/Users/User/workspace/learn-vagrant/shared-folder", "/home/vagrant/shared-folder", 
	  type: "virtualbox", 
	  create: true, 
	  owner: "vagrant", 
	  group: "vagrant", 
	  mount_options: ["dmode=775", "fmode=664"]

   # Forward ports for Terramino (8081 for frontend, 8080 for backend)
   config.vm.network "forwarded_port", guest: 8080, host: 8080
   config.vm.network "forwarded_port", guest: 8081, host: 8081


  # Install Docker and dependencies
  config.vm.provision "shell", name: "install-dependencies", path: "install-dependencies.sh"

  # Start Terramino (can be rerun with vagrant provision --provision-with start-terramino)
  config.vm.provision "shell", name: "start-terramino", inline: <<-SHELL
    cd /home/vagrant/terramino-go
    docker compose up -d
  SHELL

  # Restart Terramino (can be rerun with vagrant provision --provision-with restart-terramino)
  # For quick changes that doesn't require rebuilding (e.g. frontend changes)
  config.vm.provision "shell", name: "restart-terramino", run: "never", inline: <<-SHELL
    docker compose restart
  SHELL

  # Reload Terramino (can be rerun with vagrant provision --provision-with reload-terramino)
  # For changes that require rebuilding (e.g. backend changes)
  config.vm.provision "shell", name: "reload-terramino", run: "never", inline: <<-SHELL
    /usr/local/bin/reload-terramino
  SHELL
 
end
