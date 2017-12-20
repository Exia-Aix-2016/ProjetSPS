# ProjetSPS
Projet Services, Protocoles et Scripts

## Install
Create the vm
```vagrant up```

Then login in the vm and set a static ip in `/etc/network/interfaces`
```
iface eth0 inet static
address 192.168.10.2
netmask 255.255.255.0
gateway 192.168.10.1
```
Restart the vm 
```vagrant reload```
### Deploy
Repeat the first step for each virtual machine in servers folder (don't forget to change the ip).

Login in SysAdmin vm
```vagrant ssh```

Go in the paybook folder ```cd paybooks```

Finaly deploy
```
ansible-playbook playbook.yml -i hosts
```
