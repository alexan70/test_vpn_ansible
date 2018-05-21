# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.provision 'install-deps', type: 'shell', inline: 'apt-get update -qq && apt-get install libnss-myhostname python openvpn easy-rsa -y'
  config.vm.network "private_network", ip: "192.168.50.1"
  config.vm.network "forwarded_port", guest: 22, host: 9022
  config.vm.provision 'ansible' do |ansible|
     ansible.playbook = 'tasks/main.yml'
     ansible.raw_arguments = ["--diff", "-v"]
  end

end
