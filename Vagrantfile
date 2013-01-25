# -*- mode: ruby -*-
# vi: set ft=ruby :

$multivm = false
$boxes = ["openfire"]

Vagrant::Config.run do |config|

  config.vm.box = "precise64"

  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  config.vm.customize ["modifyvm", :id, "--memory", 1024]

  config.vm.network :hostonly, "192.168.1.100"

  config.vm.provision :chef_client do |chef|

    chef.chef_server_url = $chefserver
    chef.validation_key_path = "#{$home}/.chef/validation.pem"
    chef.node_name = getNode
    chef.environment = "vagrant"
    chef.add_role "openfire"

  end
  
end
