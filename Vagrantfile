Vagrant.configure("2") do |config|

    config.vm.box = "ubuntu/jammy64"
    config.vm.hostname = "webServer1"
    
    config.vm.network "private_network", type: "dhcp"

    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512" 
      vb.cpus = 1      
    end
  
    config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y apache2
    sudo systemctl enable apache2
    sudo systemctl start apache2
  SHELL

  config.vm.synced_folder "src", "/var/www/html"
end