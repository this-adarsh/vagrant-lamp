# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    config.vm.box = "v0rtex/xenial64"

    # Mount shared folder using NFS
    config.vm.synced_folder "public", "/var/www/html"

    # Do some network configuration
    config.vm.network "private_network", ip: "192.168.11.11"

    # Assign a quarter of host memory and all available CPU's to VM
    # Depending on host OS this has to be done differently.
    config.vm.provider :virtualbox do |vb|

        vb.customize ["modifyvm", :id, "--memory", 2048]
        vb.customize ["modifyvm", :id, "--cpus", 4]
    end

    config.vm.provision :shell, :path => "bootstrap.sh"

end