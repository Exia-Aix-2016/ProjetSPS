Vagrant.configure("2") do |config|

  config.vm.box = "generic/debian9"

  config.vm.synced_folder "playbooks/", "/home/vagrant/playbooks"

  config.vm.provision "shell", inline: "ssh-keygen -q -t rsa -N "" -f ~/.ssh/id_rsa", privileged: false
 
end
