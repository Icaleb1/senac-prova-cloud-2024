Vagrant.configure("2") do |config|
  config.vm.box = "debian/bookworm64"
  config.vm.provider :virtualbox do |vb|
      vb.name = "caleb"
  end
  config.vm.hostname = "fernandes"
  
  config.vm.network "public_network"
  
  config.vm.synced_folder "./dados/", "/home/vagrant/dados" #, type: "virtualbox"
  
  config.vm.provision "shell", inline: <<-SHELL
    apt update
    apt install -y net-tools
    apt install -y vim
    apt install -y nmap
    apt install -y docker docker.io docker-compose
    sudo usermod -aG docker vagrant
    apt upgrade -y
    sudo reboot
  SHELL
end