# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.provision 'install-deps', type: 'shell', inline: 'apt-get update -qq && apt-get install libnss-myhostname python -y'
  config.vm.provision 'ansible' do |ansible|
     ansible.playbook = 'openvpn.yml'
     ansible.raw_arguments = ["--diff"]
  end

end
