---
title: Network Layer
date: 2025-03-26 12:00:00 -0400
categories: [Notes]
tags:  []
---

### Introduction

The Network Layer is the third layer of the OSI model, and is the Internet layer of the TCP/IP model. It’s responsible for the **routing** (choosing a path) and **forwarding** (taking the path) of packets (or datagrams) through *routers*. As with any other layer, it provides services to the layer above it, and receives service from the layer below. In this case, the Network Layer powers the Transport Layer, and relies on the Data Link layer.

The Network Layer has two core responsibilities. Each individual router is responsible for taking incoming packets and sending them out on the proper outgoing link. This is referred to as the *data plane* in routers and has to do with the actual doing of the forwarding. As for deciding where to forward the packet to, that is the responsibility of all routers collectively and is apart of the *control plane*, which use routing algorithms and protocols to determine efficient paths. This is also called Software Defined Networking (SDN).

### Routers

Routers contain a forwarding table which maps IP ranges to outgoing links or interfaces using longest prefix matching. When a datagram reaches a router, it examines the destination IP and indexes this forwarding table to figure this out. Routing algorithms can either be centralized or decentralized. In a centralized algorithm, a single server is responsible for figuring out the best routes and uploading this to each router. In decentralized algorithms, each router runs the algorithm. 

### Services Provided

The Network Layer is often referred to as a best-effort service because it does not guarantee that packets will be sent in order, on time, without loss, nor with a bandwidth guarantee. There are other network architectures (asides from the Internet), such as ATM (Asynchronous Transfer Mode) which *do* provide some sets of service guarantees. ATM is an older model which lost its advantage as Ethernet became faster.

The Network Layer can also provide connection-oriented services to the transport layer. This is known as a virtual-circuit network (as opposed to a connectionless datagram network), and is achieved with the help of all routers via signaling messages for setup, flow, and teardown. This is a different kind of connection than TCP because every router along the path maintains some state in order to supply this circuit. In TCP, only the end hosts are aware of a sustained connection. However, a network layer can support only ONE of these service models! The Internet as we know it is obviously a datagram network, which means virtual circuits are not supported (after all, the point of IP is to route packets without context). Other independent networks can, and do, follow other network architectures, such as ATM. I won’t go into virtual-circuits in this post.



### Common Protocols

1. NAT (Not a protocol but I’m adding it here)
2. IP & IPSec
3. ICMP
4. Routing protocols, like RIP & OSPF

There are many more networking protocols, many outdated or proprietary. 

### Points of confusion

Here are a few things I learned while researching the Network Layer in depth:
1. Routers are specific to the Network layer as they are the only devices which use IP to route. Switches operate on Layer 2, and Hubs operate on Layer 1, and use different protocols to forward the packets they receive. Switches, for example, operate on MAC addresses.
2. A packet switch is anything that takes a packet from an incoming link and forwards it on an outgoing link based on a packet header. Therefore, both routers and switches are packet switches which operate on different layers.
3. Hubs are not packet switches because they do not forward based on header information. They are primitive devices which do not make forwarding decisions, but just repeat signals.
4. Packet switches, for the most part, do not have transport or application layers.
5. In my networking class, I had learned about circuit switching, multiplexing, and connection-oriented virtual circuits on the network layer. I had forgotten about them, and now I realize that they are used in *different networking infrastructures*. I’d be interested to read “An Introduction to ATM Networks”, Perros in the future.
6. Some call ARP a layer 2.5 protocol… sort of? There are a couple of conflicting ideas but I think most point to it being layer 2 by the argument that ARP does not route at all, which makes sense.



### Sources
1. Computer Networking A Top-Down Approach by Kurose & Ross, chapter 4
2. A lil bit of wikipedia…
