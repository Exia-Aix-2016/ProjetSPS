Vagrant.configure("2") do |config|

  config.vm.box = "generic/debian9"

  # Generate ssh keys
  config.vm.provision "shell", 
    inline: 'ssh-keygen -q -t rsa -N "" -f ~/.ssh/id_rsa', 
    privileged: false

  # Sync playbooks folder accross vm and host
  config.vm.synced_folder "./playbooks/", "/home/vagrant/playbooks"

end
