Vagrant.configure("2") do |config|
    config.vm.define "master" do |subconfig|
      subconfig.vm.box = "centos/8"
      subconfig.vm.hostname = "master"
      subconfig.vm.network :private_network, ip: "10.0.0.11"
    end
  
    config.vm.define "lin" do |subconfig|
      subconfig.vm.box = "centos/8"
      subconfig.vm.hostname = "lin"
      subconfig.vm.network :private_network, ip: "10.0.0.12"
    end
  
    config.vm.define "dc" do |subconfig|
      subconfig.vm.box = "mwrock/Windows2016"
      subconfig.vm.hostname = "dc"
      subconfig.vm.network :private_network, ip: "10.0.0.13"
    end

    config.vm.define "win" do |subconfig|
      subconfig.vm.box = "mwrock/Windows2016"
      subconfig.vm.hostname = "win"
      subconfig.vm.network :private_network, ip: "10.0.0.14"
    end
end