---
tags:
Date /Time: "{date} {time}"
title:
draft: true
---
# INTRO

*a protocol* is set of rules defining how data should be communicated between devices over a network.

*a standard* is an agreed-upon specification that describes how a protocol or technology should work (generally the most effective ones are the vendor-neutral standards)

they are created by a independent standard organization IEE(Ethernet: 802.3, WiFi: 802.11) and IETF (TCP,IP, UDP, HTTP, DNS...etc)

![[Screenshot 2026-09-22 142601.png|373]]
each layer uses the services of the layer below and provides services to the layer above
a groupe of protocols that serves in the same is called a stack of protocols
the model is a description not a law, each textbook can have a different interpretation of the model.
# The layers
Application layer  includes protocols for communication between application processes, create and interpret the data. 

-  each process has a an associate port number that is being handled by the transport layer 

transfer layer: provides end-to-end communication between application processes using port numbers 

each machine has an *ip address* the internet provides end-toend communication between hosts across networks using IP addresses and routers.

the network layer provides *hop-hop delivery* within a local network using *MAC addresses*

the physical layer sends bits as electrical optical or radio signals over the physical medium.

![[Screenshot 2026-09-23 192526.png|518]]

## Physical layer:
 as it stated above it sends and receives bits as electrical, optical or radio signals over the medium
 it also defines cables, physical connectors, signal levels and link speed.(UTP cables multimode fiber optic cables)

(in some models the physical layer and LAN layer orn network layer are the same)
## Network layer:
it provides hop-to-hop delivery of message of the LAN,
- A hop is one step along the path between two devices (from router to router or to host)
- uses *MAC (Media Access Control) addresses* to identify interfaces.
	- PC send MAC addresses to the router's interface which the router sends to a different router interface... until it reach the destination.
- key protocols: Ethernet and WiFi
## Internet Layer:
- End-to-end  because it cares about getting the information *to the* destination, so it focusses on getting from the source to the destination without worrying about the hops in the middle.
- it uses IP addresses to identify hosts in the network
- routers mainly operate at this level to forward the message until it gets to the IP destination host
- main protocols: IP, ICMP
## Transport Layer:
also provides end-to-end communication between application processes (also called process-to-process, services-to-services)

- uses port numbers to identify each processes on each host (processes like web server or file sever)
- this layer mainly runs on the communicating hosts like the server or client, the routers doesn't care what is about the process (they're exception
- protocols UDP(User Datagram Protocol) and TCP (Transmission Control Protocol)
## Application layer

(layer 7 cuw of the OSI model)
- defines how application processes format send and interpret data
- protocols at this layer define message formats and rules for specific tasks such as
	- Browsing the web (HTTP/HTTPS)
	- Transferring files(FTP, TFTP)
	- Sending/receiving emails (SMTP,POP3,IMAP)
- routers and switches typically dont care about this layer (too high level)
- 

# Encapsulation and decapsulation & PDU

### Encapsulation & Protocol data units
1- the application layer prepare the data
	the "message" moves *down the stack*, each layer encapsulâtes the data with a *header* including the info needed for that layer (source-destination..etc...)
2- the transport layer encapsulates and adds its *header*
	- the combinaison is called a **segment (using TCP) or datagram(using UDP)**
3- the internet layer encapsulates and adds its *header*
	-  the combinaison is called a **packet**
4- the network layer encapsulates and adds a *header* and a *trailer*
	- the combinaisons is called **frame**
 (the trailer is used by the receiving device to check for *transmission errors*)
 5- the physical layer transmits the data as a stream of bits
![[Screenshot 2026-09-23 195323 1.png]]
-> we always find frames passing through the wire,

there is alternative names for these "Combination of headers and data" which describes it at each stage called PDU
- segment/datagram is layer 4 PDU *L4PDU* 
- a packet is layer 3 PDU *L3PDU*
- a frame is layer 2 PDU *L2PDU

the content of each PDU is called a *Payload*, basically removing the added header or trailer that layer has added give us the payload,  
- segment/datagram/L4PDU payload is the data
- packet/L3PDU payload is the segment/datagram..etc.
### Decapsulation

1- the destination host receives the message as a stream of bits (layer 1) 
2- the devices examines the the layer 2 header and trailer and then removes them (checks for transmission errors)
3- decapsulation of layer 3 header
4- decapsulation of layer 4 header
5- the data is then given for the application layer and if needed generates a response
![[Screenshot 2026-09-23 195311.png]]
### Adjacent layer interaction:
we said each layer provides a service to the layer above it and it is serviced by the layer below it which is *adjacent layer interaction*.
- layer 4 *provides service* to layer 5 by delivering data to the correct application using port numbers
- layer 4 *is serviced by* layer 3 since its delivering segment/datagrams to the correct destination using IP addresses
- ...etc
-> each layer relies on the layer below it.

there is also *same layer interaction* when each layer communicates with the same layer on other devices (app sends to app ..etc)

- a segment is addressed to the layer 4 port number  of the process in the destination host
- a packet is addressed to the layer 3 Ip address of the destination host
- a frame is a ddressed to the layer 2 MAC addresse
- signals are sent to the physical ports (RJ-45 ports per example or SFP transceivers)

this gives a flexibility to change or improve protocols in a layer without touching the rest as long as it keeps to its "duties"

