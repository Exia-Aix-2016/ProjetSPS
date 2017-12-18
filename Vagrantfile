Vagrant.configure("2") do |config|

  config.vm.box = "generic/debian9"
  config.vm.hostname = "SysAdmin"

  # Sync playbooks folder accross vm and host
  config.vm.synced_folder "playbooks/", "/home/vagrant/playbooks"

  # Sync vms folder accross vm and host
  config.vm.synced_folder "vms/", "/home/vagrant/vms", create: true

  # Generate ssh keys
  config.vm.provision "shell", 
    inline: 'ssh-keygen -q -t rsa -N "" -f ~/.ssh/id_rsa -C ""', 
    privileged: false

  # Copy ssh public key
  config.vm.provision "shell", 
    inline: 'cp ~/.ssh/id_rsa.pub ~/vms/admin_rsa.pub', 
    privileged: false

  # Install ansible
  config.vm.provision "shell", inline: <<-SHELL
    sudo echo deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main >> /etc/apt/sources.list
    sudo apt-get update -y
    sudo apt-get install ansible -y --allow-unauthenticated
  SHELL

end
