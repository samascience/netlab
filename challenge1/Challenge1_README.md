# Network Lab Challenge 1  
In this scenario you have a pair of routers you administer (r1 & r2) that uplink two each other and to an ISP provider.
Some users are reporting they can not ping google.com 

![img.png](img.png)

You can access all of the devices in the topology but access to the ISP Devices are not required



## Install Netlab 
```bash
./setup.sh
```

## Download the Git Repo
```bash
git pull <>
```

## Bring up the lab
```bash
netplan up
```

## Confirm the lab is up
```bash
netplan status
```

### Connect to the devices
```bash
netlab connect <device name>
vtysh 
You can issue commands from the cli via  
netlab connect <device name> --<show ommand>
```



solution 

ip route 10.0.0.2 255.255.255.255 eth1
ip route 10.0.0.1 255.255.255.255 eth1
