Vagrant.configure("2") do |config|
    config.vm.define "lin" do |subconfig|
      subconfig.vm.box = "centos/8"
      subconfig.vm.hostname = "lin"
      subconfig.vm.network :private_network, ip: "10.0.0.11"
    end
  
    config.vm.define "win" do |subconfig|
      subconfig.vm.box = "StefanScherer/windows_2019"
      subconfig.vm.hostname = "win"
      subconfig.vm.network :private_network, ip: "10.0.0.12"
    end

end