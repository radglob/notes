# Introduction - 08/27/2014

## TODOS:
* ~~Get the book...~~

## What's the Internet? Nuts and Bolts View
* millions of connected devices, in multiple tiers.
* Hosts are end points in the system.
    * These run applications.
* Communication Links (routers):
    * Links in the system. Wired with fiber, copper, go over radio or satellite.
    * Transmission rate called 'bandwidth'.
* Packet switches forward packets (parcels of data).
    * There are routers and switches. Routers are partially hardware, switches
      are mostly hardware. They tend to be faster because of this.
* Protocols: TCP, IP, HTTP, Skype (goes over port 80), 802.11 (wifi), UDP, FTP,
    HTTP, etc. Most have an option to be secured.
* Internet protocols are defined by RFCs (Request for comments). They are living
    standards.

## What's the Internet? Service View
* You can think of the internet as two parts: infrastructure and services.
* Infrastructure provides services.
* Examples over services: web, VoIP, email, etc.
* These services provide programming interfaces for applications.

## What is a protocol?
* Protocols define format and order of messages sent and received by networking
    entities.
* An example of a human protocol is conversational etiquette. This is similar to
    how TCP works (both machines "say hi", exchange information.
* Three types of connections: simplex (one way, ex. space probes), half-duplex (two way,
    one at at time, ex. tcp), full-duplex (two way, simultaneous, ex. telephone)

## Network Structure:
* Network edge: hosts - clients and servers, servers often in data centers.
* access networks, physical media: wired, wireless communication links.
* network core: interconnected routers, networks of networks.

## Access net: digital subscriber line (DSL)
* Used existing telephone line to central office DSLAM (access multiplexer)
    * data over DSL phone line goes to Internet.
    * voice of DSL phone goes to telephone net.
* &lt; 2.5 Mbps upstream transmission rate (typically &lt; 1 Mbps)
* &lt; 24 Mbps downstream transmission rate (typically &lt; 10 Mbps)

## Accces net: cable network
* HFC: hybrid fiber coax
    * asymmetric up to 30 Mbps

## Enterprise access networks (Ethernet)
* typically used in companies, universities, ec.
* 10 Mbps, 100 Mbps, 1Gbps, 10Gbps transmission rate.
* Today, end systems are typically connected by ethernet.
