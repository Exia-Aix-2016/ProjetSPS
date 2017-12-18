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
And add google dns in `/etc/resolv.conf`
```
nameserver 8.8.8.8
```
