BOX_IMAGE = "bento/ubuntu-16.04"
NODE_COUNT = 1

Vagrant.configure("2") do |config|
  config.vm.define "prod" do |subconfig|
    subconfig.vm.box = BOX_IMAGE
    subconfig.vm.hostname = "prod"
    subconfig.vm.network :private_network, ip: "10.0.0.10"
  end
  
  (1..NODE_COUNT).each do |i|
    config.vm.define "node#{i}" do |subconfig|
      subconfig.vm.box = BOX_IMAGE
      subconfig.vm.hostname = "dev#{i}"
      subconfig.vm.network :private_network, ip: "10.0.0.#{i + 10}"
    end
  end
end
