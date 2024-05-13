<h1 align="center">Wireless Network Simulator 📡</h1>





## Workflow

The project aims to implement a wireless network simulator, with definition of layers: physical, link and network. Using concepts such as hosts, communication protocols, position of devices in an environment, in order to evaluate the performance of the system.

<p align="center">
  <img src=".github/network-layers.png" weight=350 />
</p>

## Layers 

The concept of layers in computer networks defined in some models, for example OSI and TCP/IP, is used to separate tasks into modules with well-defined protocols, increasing system performance and facilitating communication between different platforms.

### Physical 

The physical layer is responsible for sending and receiving packets from one physical interface to others, usin the following methods.
``` python
  receive_pck()
  send_pck()
```
The physical layer has an x and y position, signal range and a list of neighbors. When sending a packet, the physical layer checks the global list of hosts that are within reach.

### Link 

The link layer controls the flow of reception, delimitation and transmission of frames and establishes a communication protocol (Media Access Control) between directly connected systems. This layer has three methods:

``` python
  receive_pck_physical()
  sending_request()
  send_pck_physical() 
```

#### MAC Protocol

The master coordinator used as the MAC protocol stores a list of the packages to be sent and allows the forwarding of only 1 at a time, respecting the order of arrival, to avoid signal collisions.r coordinator use as MAC Protocol is responsible for keeping a list of the packages to be sent, allowing the forwarding of only 1 at a time, respecting the order of arrival, to avoid signal collisions.  

### Network

The network layer determines how packets are routed from origination to destination.

#### DSR Protocol

The Dynamic Source Routing Protocol (DSR) is a routing technique, which the sender determines the complete sequence of host responsible for forwarding the packets to the receiver. Then, each node stores a _routing table_, which contains the routes known to each.

Packages that travel over the network can be classified into three categories:

  - __RREQ:__ Route Request Packet
  - __RREP:__ Route Reply Packet
  - __DATA:__ Data Packet

## Setup

### Creating a host

Create a host by writing ` new_host = host(host_id, x_position, y_position, master, range_ratio) ` into the main.py. The *master* is the entity that decides which host will send data, so you must create only one master. 

### Creating a data package ###

Create a data package for any host by : `host_name.send_message("message content", receiver_host_id)`

## Run 

Go into the file project then open the terminal and write the command bellow :

```
python main.py
```

## Show your support

Give a ⭐️ if this project helped you!


