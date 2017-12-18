Vagrant.configure("2") do |config|

  config.vm.box = "generic/debian9"

  # Sync playbooks folder accross vm and host
  config.vm.synced_folder "./playbooks/", "/home/vagrant/playbooks"

  # Sync vms folder accross vm and host
  config.vm.synced_folder "./vms/", "/home/vagrant/vms", create: true

  # Generate ssh keys
  config.vm.provision "shell", 
    inline: 'ssh-keygen -q -t rsa -N "" -f ~/.ssh/id_rsa', 
    privileged: false

  # Copy ssh public key
  config.vm.provision "shell", 
    inline: 'cp ~/.ssh/id_rsa.pub ~/vms/admin_rsa.pub', 
    privileged: false

end
