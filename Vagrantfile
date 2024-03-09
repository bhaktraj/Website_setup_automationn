
Vagrant.configure("2") do |config|

  config.vm.box = "eurolinux-vagrant/centos-stream-9"

   config.vm.network "private_network", ip: "192.168.56.14"
   config.vm.network "public_network"
   config.vm.provider "virtualbox" do |vb|
     vb.memory = "1024"
   end
   config.vm.provision "shell", inline: <<-SHELL
     sudo -i
     yum upgrade
     yum install httpd wget zip unzip -y
     wget https://bootstrapmade.com/content/templatefiles/Gp/Gp.zip
     unzip Gp.zip
     cd Gp/
     cp -r * /var/www/html
     systemctl start httpd
     systemctl enable httpd
   SHELL
end
