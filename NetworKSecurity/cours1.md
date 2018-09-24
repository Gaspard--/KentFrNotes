# Hardware

## LAN

LANs usually have a "star" (ie. non cyclic graph) configuration
Hardware: wifi ad ethernet.

## WAN

WAN (different locations): mesh configuration
point to point links
Hardware: sattelite, optical fiber.
WANs are of meshes of *routers* which connect *hosts*. Subnet designates the *whole group* of routers.

Multiple routes are possible.

# Software

Network softawre is devided in layers.
Layers form a stack, and each layer builds on the layer below to provide services to the layers above.

Protocol: governs the exchange between peers.

Stacks are travels down and back up on the peer.

The collection of layers are called the *protocol stack*.

# Network models

## OSI

Unused by industry because took to long to finalise.
Good model for networks. Used as reference model for explaining other technologies.

7 layers:

7. Applcation

   Applications over network (like remote display / terminal etc.)

6. Presentation

   Originally for binary representation differences.
   Usefull for compression & encryption.

5. Session

   Provides services for session-based applications.
   (file transfer, connection recovery)

4. Transport

   Supports connection oriented service.

--- Subnet ---

3. Network

   Controles operation of subnet

2. Data link

   Makes channel reliable.

1. Physical

   Provides unreliable connectionless service, will not correct corrupt data.

## TCP / IP

Is widely used, orginated fom ARPANET. Poorly defined model.
TCP/IP has only four layers. No exact correspondance with OSI.
No layers corresponding to 5) and 6).

4) Application

   - HTTP, FTP, TELNET, SMTP, DNS, etc.

3) Transport layer

   Two choices:

   - TCP (Transition Control Protocol) : reliable, connection-oriented
   - UDP (User Datagram Protocol) : unreliable, connectionless (no delay for data recovery)

2) Internet Layer

   Protocol: IP.
   - connectionless and unreliable.

1) Host to network layer

   - No standart protocol. Implementations use Wifi / Ethernet.
    -> advantage: no prescribed technology, therefor versatile
    -> downside: can't connect any 2 devices with tcp / ip
