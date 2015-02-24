# Chef Server Vagrantfile

This is a basic Vagrant file to setup an Ubuntu Precise 64 (12.04) vm on a private network so it can talk to another vm running on the same private network. The intent is to create a bare bones vm that can be used for testing a Chef Server and how it interacts with other services, such as Chef Analytics for instance. The Vagrantfile assumes you're using Virtual Box and bumps the memory of the vm to that recommended for a Chef Server.

The Vagrantfile can be modified if you need different values (such as updating the base box, ip, or server hostname for instance).

The base dir with the Vagrantfile will be mapped to /vagrant on the vm. This allows easy access to copy installers on the box. So a Chef Server can be installed by copying the deb to the directory with the Vagrantfile, then ```vagrant ssh``` into the box, ```cd /vagrant``` and run the installer.

To communicate over the private network you will likely need to add the ip/hostname mapping to /etc/hosts on your localhost machine, like so:

192.168.33.10 server.test

server.test is the default hostname setup in the Vagrantfile.

Then once a Chef Server has been setup and running, you can access the  Chef Server from browser by accessing https://server.test

If you want setup another service to talk to the running Chef Server, simply copy the Vagrantfile to another directory, modify the needed values (most likely just the ip and hostname), then startup the vm. Add a new line to your /etc/hosts file with the new vm's ip and hostname and the vm is ready to go. Then just follow the instructions for setting up the server you want to talk to the running Chef Server.

