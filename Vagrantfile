Vagrant.configure("2") do |config|
  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "generic/ubuntu2004"
   config.vm.define  "Jenkins"
   config.vm.hostname = "Jenkins"
   config.vm.network "private_network", ip: "192.168.201.100"

   config.vm.provider "virtualbox" do |vb|
     vb.memory = "4096"
   end
  #
   config.vm.provision "shell", inline: <<-SHELL
     apt-get update
     sudo apt install apt-transport-https ca-certificates curl software-properties-common
     curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
     sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
     sudo apt update
     sudo apt install -y docker-ce git vim
   SHELL
end
