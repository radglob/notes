# Computer Networking - Chapter 1

## 1.1 What is the Internet?

### 1.1.1 Nuts And Bolts.
iThere are fundamentally two parts: hosts (end user systems) and systems
connecting them to each other (communication links, packet switches, etc.)

* **Packets** are packages of information sent from one system to another. The rate
    at which packets are sent is called **transmission speed**.
    * Packet switches come in a variety of forms, but the most common ones today
       are **routers** and **link-layer switches**.

* The main protocols computers use to transfer information are TCP (Transmission
    Control Protocol) and IP (Internet Protocol). They are usually collectively
    known as TCP/IP.
* Internet standards are developed by the Internet Engineering Task Force
    (IETF), whose standard documents are called Requests For Comments (RFCs).

### 1.1.2 Services Description
The internet can be thought of as an infrastructure that provides services and
applications. Examples are email, social networking, instant messaging, etc.

Systems are often accessed through an Application Programming Interface (API),
that specifies how an end system is allowed to access a service.

### 1.1.3 What is a protocol?
A human example of a protocol is conversational etiquette. One person says
hello, the other reciprocates, and then the content of the conversation starts.
In computers, a "greeting" is called a "handshake". This occurs to ensure
connectivity.

## 1.2 The Network Edge (Organization)
At the edge of the system are hosts. These can be either servers or clients. One
layer into the system are access networks - a network that physically connects
an end system to the first router on a path to another end system.

## 1.3 The Network Core
The mesh of packet switches and links that interconnect the Internet's end
systems. Here, most packet switches use store-and-forward transmission at inputs
to links.

end-to-end delay: `d<sub>end-to-end</sub> = N * L/R`

Packet switches have multiple links attached to them. For each link, there is an
output buffer. If an incoming packet needs to go to a certain link, but it is
busy, the packet must wait, causing a **queuing delay**. If the packet times out
during this time, it gets dropped. This is called **packet loss**.

Routers have forwarding tables that map destination addresses to the router's
outbound links.

NOTE: The routing system is analagous to asking for directions instead of using
a map.

There are two fundamental approaches to moving data: circuit switching and
packet switching. Circuits are implemented using either frequency-division
multiplexing (FDM) or time-division multiplexing (TDM). 

Circuit switching is criticized for wasting resources during idle periods and
being expensive to implement. However, packet switching is criticized as being
unsuitable for real-time services due to queuing delays and packet loss.

In general, packet switching tends to be as performant as circuit switching
while allowing more users.

## 1.4 Delay, Loss and Throughput in Packet-Switched Networks
There are different types of delays in packet-switched networks:
* nodal processing delay
* queuing delay
* transmission delay
* propagation delay

Processing delay is the time required to examine a packet's header and determine
its destination in the system.

Queuing delay is the time a packet must wait due to a busy link on a switch.

Transmission delay is the time it takes to push all of the packet's bits to the
link. `L / R`

Propagation delay is the time required to propagate from one router to another.
This is a function of the physical distance between routers and the speed of the
physical medium of the link.

The end-to-end delay of a link is the number of packets multiplied by the sum of
the processing, transmission and propagation delays.

Throughput is another major concern in networks. It is usually measured in two
ways:
* instantaneous throughput
* average throughput

## 1.5 Protocol Layers and their Service Models
Networking architectures can be layered. There are benefits and drawbacks to
this. The protocols of the various layers is called the protocol stack. For the
internet, this includes the application layer, the transport layer, the network
layer, the link layer and the physical layer.

* Application layer: where network applications and application-layer protocols
    reside. Packets from this layer are called messages.
* Transport Layer: transports application layer messages between application
    endpoints. Transport layer packets are called segments.
* Network layer: responsible for moving network-layer packets called datagrams
    from one host to another.
* Link layer: assists the network layer, moving packets to the next node in the
    route. Link layer packets are called frames.
* Physical layer: moves individual bits within the frame from one node to the
    next. Protocols used are link dependent.

The Interanational Organization for Standardization (ISO) proposed a network
model using seven layers, called the Open Systems Interconnection (OSI). In
addition to the Internet's protocol layers, it also included two additional
layers:
* presentation layer: responsible for data compression, encryption and
    description
* session layer: responsible for delimiting and synchronizing data exchange.

In the Internet model, the services provided by both of the aforementioned ayers
are left to the application developer to implement.

In general, lower level protocols encapsulate messages from higher levels. See
the example on page 55 for more clarity.

## 1.6 Networks Under Attack
Numerous attacks can be made on Internet connected devices:
* malware: malicious software that can steal information, install spyware, etc.
    Can be self-replicating.
* botnet: a network of thousands of comprimised and connected devices which
    are used for spam email, DDoS attacks, etc.
* Worms: a specific type of malware that enter a system without explicit user
    interaction.

A broad class of security threats is called denial-of-service attacks (DoS),
which renders a network, host or piece of infrastructure unusable by legitimate
users. Examples include:
* vulnerability attack: sending well-crafted messages to a vulnerable
    application or OS on a targeted system.
* bandwidth flooding: sending a huge volume of packets, so the target's access
    link gets blocked.
* connection flooding: sending a large number of half-open or fully open TCP
    connections at the target host, preventing it from accepting legitimate
    ones.

Other security threats include packet sniffing, IP spoofing, end-point
masquerading, man-in-the-middle attacks and more.

## 1.7 History
Packet switching was developed from 1961 to 1972 by three independent research
groups as an efficient alternative to circuit switching. An important concern
was the bursty nature of traffic: short periods of intense activity followed by
long periods of inactivity. Using queuing theory, it was shown that packet
switching was superior for handling this kind of traffic.

From 1972 to 1980, we see the rise of proprietary networks and internetworking.

From 1980 to 1990, networks became mainstream, with the number of hosts growing
from a few hundred to a hundred thousand. Major increases in network speed were
also seen.

In the 1990's, the Internet exploded, signaling a huge growth in technology due
to a range of newly available services. More and more devices were becoming
internet connected, or being developed with that idea in mind.
