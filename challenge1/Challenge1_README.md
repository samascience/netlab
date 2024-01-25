# Network Lab Challenge 1  
In this scenario you have a pair of routers you administer (r1 & r2) that uplink two each other and to an ISP provider.

You have to solve for Ping not reachable between server1/2 and h3/4 and between server1 and server2

You can access all of the devices in the topology but access to the ISP Devices are not required

In order to pass the challenge your solution need to pass the ``netlab validate`` test 

The initial validation will fail all 4 ping tests 
server1 -> h3
server1 -> h4

server2 -> h3
server2 -> h4

server1 -> server2

You need to identify two issues and resolve them
Resolution should be a Pull Request to this repo with the changes you made to the topology.yaml or any other files needed 
You can troubleshoot by connecting to the devices and making changes to the configuration
Run time changes can be test with the ``netlab validate`` command

![img.png](img.png)

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

## Restart the Lab / Apply Changes
```bash
netplan restart
```

### Connect to the devices
```bash
netlab connect <device name>
vtysh 
You can issue commands from the cli via  
netlab connect <device name> --<show ommand>
```

### Validate the fix 
```bash
netlab validate
```
 
Successful Validation should look like this 
```bash
root@netlab/bgplab# netlab validate
[wait]    Waiting for BGP to stabilize

[ping1]   Server1 Ping to H3 [ node(s): server1 ]
[PASS]    Validation succeeded on server1
[PASS]    Test succeeded

[ping2]   Server2 Ping to H4 [ node(s): server2 ]
[PASS]    Validation succeeded on server2
[PASS]    Test succeeded

[ping3]   Server1 Ping to Server2 [ node(s): server1 ]
[PASS]    Validation succeeded on server1
[PASS]    Test succeeded

[ping4]   Server1 Ping to H4 [ node(s): server1 ]
[PASS]    Validation succeeded on server1
[PASS]    Test succeeded

[ping5]   Server2 Ping to H3 [ node(s): server2 ]
[PASS]    Validation succeeded on server2
[PASS]    Test succeeded

[SUCCESS] Tests passed: 5


