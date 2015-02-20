# Server Test

A basic Vagrant file to setup an ubuntu precise 64 (12.04) vm on a private network
so it can talk to another vm running on the same private network.

Also bumps memory of the vm to recommended for a Chef Server.

Can modify vagrant file to change values.

For network talk to happen, will likely need to add ip mapped to hostname in
/etc/hosts on localhost machine, like so:

192.168.33.10 server.test

To hit in browser, hit https://server.test
