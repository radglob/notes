# Chapter 3 Review - Transport Layer

The transport layer handles the logical communication between processes running
on different hosts. What this means is that, from an application's perspective,
hosts are directly connected.

The protocols at this level are implemented on end systems, but not on network
routers. When sent, the transport layer converts application layer messages into
transport layer packets, called segments. This is done by breaking the message
into smaller chunks and appending a transport layer header to each. On the
receiving side, the network layer extracts the transport layer segment from the
datagram and passes it up to the transport layer.

## Protocols
On the internet, and more generally in TCP/IP networks, there are two protocols
used for transport layer communication. They are UDP (User Datagram Protocol)
and TCP (Transmission Control Protocol). UDP provides unreliable, connectionless
service, while TCP provides reliable, connection-oriented service.

The internet's network-layer protocol is the Internet Protocol, or IP. It
provides logical communication between hosts, and provides best-effort delivery
service. This means that IP makes a "best effort" to deliver segments between
hosts, but makes no guarantees. It does not guarantee segment delivery, orderly
delivery or integrity of segment data. For these reasons, IP is considered an
unreliable service.

The responsibility of UDP and TCP is to extend IP's delivery service between two
end systems. This is called transport-layer multiplexing and demultiplexing.

In contrast, TCP provides reliable data transfer, flow control, sequence
numbers, acknowledgments, timers and more to ensure data is delivered correctly
and in order. It also provides congestion control, ensuring that a single TCP
connection doesn't congest the links and routers between hosts with excessive
traffic.

## Multiplexing and Demultiplexing
Multiplexing is the job of gathering data chunks at the source host from
different sockets, encapsulating each data chunck with header information to
create segments and passing the segments to the network layer.

Demultiplexing is the job of delivering data in a transport-layer segment to the
correct socket for a process.

Segment headers include the source port number and destination port number. Each
port number is a 16-bit number. Ports ranging from 0 to 1023 are well-known port
numbers and are restricted, reserved for specific processes like HTTP, FTP, SSH,
etc.

### Connectionless Multiplexing and Demultiplexing
With socket programming, when a UDP socket is created, the transport layer will
automatically assign a port number in the range 1024:65535 that is not currently
being used by another port. These values are very important for UDP
(de)multiplexing.

### Connection-oriented Multiplexing and Demultiplexing
TCP sockets are identified by a four-tuple (source IP, source port, destination
IP, destination port) as opposed to the two-tuple that defines a UDP socket.

## Connectionless Transport: UDP
UDP adds next to nothing to IP. It takes messages from an application process,
attaches source and destination port numbers, adds two other small fields and
passes the segment to the network layer. There is no handshaking involved, which
is why this is considered connectionless.

Why use UDP? 
* Finer application level control over what data is sent and when: TCP makes a
    lot of assumptions, and will send until acknowledged. Some applications
    require a minimum sending rate and can handle some loss.
* No connection established: TCP requires a three-way handshake, which can
    introduce a delay. This is a tradeoff between speed and reliability.
* No connection state: just as the connection doesn't have to be initiated,
    there is no overhead in ensuring that systems are still connected. As such,
    a server can support many more UDP processes than TCP.
* Small packet header overhead: TCP segments take 20 bytes to encapsulate the
    header, where UDP only takes 8.

Applications that run on UDP:

Service | Application Protocol | Transport Protocol
--------|----------------------|-------------------
Remote file server | NFS | typically UDP
Streaming multimedia | proprietary | UDP or TCP
VoIP | proprietary | UDP or TCP
Network Management | SNMP | typically UDP
Routing protocol | RIP | typically UDP
Name translation | DNS | typically UDP

### UDP Segment Structure
A UDP segment contains a source port number (16 bits), destination port number
(16 bits), a length value, checksum and the data being sent. The checksum is
used for error checking. The 1's complement of all 16-bit words in the segment
is calculated. At the reciever, all words and the checksum are summed. If there
are no errors, the sum will be 1111111111111111. UDP implements error checking
because there is no guarantee that other layers will. Additionally, bit errors
could be introduced during storage. This is called the end-to-end principle,
which states that certain functionality (such as error checking) must be
implemented on an end-to-end basis.

## Section 3.4: Principles of Reliable Data Transfer
This section is being skipped, as the pertinent information is mostly tied up in
FSMs and other diagrams. Go peruse it as needed.
