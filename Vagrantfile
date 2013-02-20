Vagrant::Config.run do |config|
  config.vm.box = "precise32"
  config.vm.box_url = "http://files.vagrantup.com/precise32.box"

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "cookbooks"
    chef.add_recipe("setup")
    chef.json = {
      :mysql => {
        :server_root_password => "root",
        :server_repl_password => "root",
        :server_debian_password => "root"
      }
    }
  end

  config.vm.forward_port(80, 8080)
  config.vm.forward_port(3306, 3306)
end