# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define :server1 do |server|
    server.vm.box = 'precise64'
    server.vm.provision :shell, :inline => 'apt-get update'

    server.vm.provision :chef_solo do |chef|
      chef.cookbooks_path = 'chef/cookbooks'
      chef.roles_path = 'chef/roles'
      chef.data_bags_path = 'chef/data_bags'
      chef.add_recipe 'apache2'
      #chef.add_role "web"

      #   # You may also specify custom JSON attributes:
      #   chef.json = { :mysql_password => "foo" }
    end
  end

  config.vm.define :server2 do |server|
    server.vm.box = 'precise64'
  end
end
