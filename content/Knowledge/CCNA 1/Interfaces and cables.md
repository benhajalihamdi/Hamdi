---
tags:
Date /Time: "{date} {time}"
title:
draft: true
---
## UTP cabbles

RJ-45 CABLES[
![Définition de RJ45 - Qu'est-ce qu'un connecteur RJ45 ?|290](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTCSfpyAA2FDfFL_Xv5aPe_uBYrn8iYBBpT-k7bxrKIwg&s=10)

RJ stands for Registered Jack. The RJ-45 connector is used at the end of a copper connector

### What is an Ethernet?
- Collection of network protocols/standards

### Ethernet Standards
connections between devices in a network has a set speed. which bits/s
Base refers to baseband signaling & T refers to twisted pair (more soon)
The copper used in ethernet standards are UTP cables (unshielded twisted pair)
the lack of shielding makes them vulnerable to EMI (electromagnetic interference)

![[Screenshot 2026-09-22 132232 1.png|420]]

pairs of unshielded cables twisted together (the twists to minimize the magnetic field effect
10BASE-T and 100BASE-T uses 2 pairs of cables
#### Connecting a switch/router or switch/PC
the network card on a machine transmits data on pins 1 and 2 and the switch receives data on pins 1&2. Tx for transmission Rx for receiving.

on a switch pins 3& 6 are used for transmission,
this allows for *Full-Duplex transmission*, no problems of like collision would occur because they are sending and receiving data on different cables

a router has the same transmission and receiving lines as like a  PC in the ethernet standard

this is also a *straight-through cable* because one connects to pin one etc...
![[Screenshot 2026-09-22 133019.png|320]]
#### Connecting router-router
it uses *Crossover cable* because the wires are crossed over each other

![[Screenshot 2026-09-22 133500.png|389]]

![[Screenshot 2026-09-22 133530.png|276]]

-> Most modern networking devices have a feature called *Auto MDI-X* which allows devices to automatically detect which pins their Neighbor is transmitting their data in and adjusts which pins it uses to transmit / receives data on.

in 1000BASE-T and 1GBASE-T the cables are bidirectional which arent just for Rx or Tx also 4&5 are connected and 7&8 are connected (twisted together)


## Fiberoptics
*SFP(small form-factor pluggable) Transceiver* is imported into a router or a switch and than u can connect it  to a fiber optic cable.

![[Screenshot 2026-09-22 134404.png|373]]

in Multimode fiber cables:
- the core is wider than single-mode fiber
- allows multiple angles(modes) of light waves to enter the fiberglass core
- uses LED based transmitters
![[Screenshot 2026-09-22 134541.png|219]]

Single-mode fiber :
- allows longer cables than both UTP(100M) and multimode fiber cable
-  uses laser based SFP transmitters
- light enters at a single angle(mode)
### Standardisation:
![[Screenshot 2026-09-22 134832.png|433]]


## COMPARISON UTP VS FIBER-OPTICS

![[Screenshot 2026-09-22 135059.png|438]]