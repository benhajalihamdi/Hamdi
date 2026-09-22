---
tags:
Date /Time: "{date} {time}"
title:
draft: true
---
- two computer are connected using ethernet crossover cable
- to check ip configuration of a pc in a CLI use the command ipconfig
- ipconfig /all gives also the physical configurations like the MAC addresse

# USING HUBS

Hub aka Network Hub, hub works in the physical layer of the OSI model 
it is used to set up LAN 
obv it has multiple ports
hub uses Star topoly meaning a central nodes connecting to other nodes
if one packet arrives at one port of the hub it is copied to all other remaining ports

to connects computer to hub we use ethernet straight through cable

its cheaper and works for small network, however hubs doesnt have memory, issues wiith broadcast

# USING SWITCHES

- a switch is a netwok device 
- hubs have no memory but switches has memory, it stores mac address in its memory
- a switch is a layer 2  device to set up a LAN

a switch stores a mac address, a table having two columns one for mac address and the second corresponding to the port number 

a switch just forwards the packet to the exact destination, it can also do broadcastign and multi casting like hubs

half and full duplex mode?

# USING ROUTERS

a router is a layer 3 devicie

router connects two networks LANS or WANS or LANS and ICPs

it has also a memory that stores the routing memory, 
FULL duplex?

we need interfaces to connect one 

# DHCP

we have two types of IPs static and dynamics,
dynamic ip addresses are given to machines that are connected to the network using DHCP, 

problems that i had, 
routers tend to block broadcasting to minimize congesion and dhcp uses a type of broadcasting, i had to configure the router to let the dhcp request pass from one network to the other where the dhcp server is 