# Network layers

Uses packets. 
End points: host computers
Routers hande the delivery of the trafic
Allows to send a pcaket from one specific host to another.
(Metaphor: letter system)

Functions:
- routs pakets of data accross a subnet
  - applies to point-to-point
  - does not concern broadcas
- manages congestion in the subnet
  - packets can take different routes
- transfers packets accross different types of interconnected networks
  - data link layer technologies may vary

Services:
- Services offered to transport layer independent of the network technology
  - not always possible
- Provide a uniform addressing scheme
- Shield transport layer from underlying network characterstics
  - not always possible

Classes of service:
- Connectionless (Datagram)
  - unreliable of data from ent-to-end
  - use higher solve problems
  - similar to postal service
- Connection-oriented (Virtual Circuit)
  - reliable delivery oof data from end-to-end
  - provides error correction an flow control
  - similar to telephone service

## Store and forard
- packet fully stored before being forwarded
- delay due to storage

## Datagram subnet technology
- Every packetneeds to carry full source and destination addresses
  - don't need to remeber anything
- Often called a best effort service
  - higher protocol layers deal wth data loss
  - robust, packets are rerouted when links fail
  - congestion difficult to control
- Can run over both Connectionless and Connection oriented services
  - connectionless data link layer is most likely

## Virtual Circuit subnet technology

- Routers need to maintain path state information
  - route decided when a VC is established
  - congetion can be aleviated
  - quality of srvice garantied
  - if path fails, communication lost
- Packets don't need to carry full dest (or ource) address
  - a VC number is allocated when VS is established
- Usually runs over a connection oriented data link layer
- expects:
  - sequences
  - flow control
  - error detection
- Will often provide individually for each virtual circuit:
  - sequencnig
  - flow control
- Enables congestion control for each VC

Each router keeps source and channel mapped to dest and channel number.
Channel number may vary. Ex: A: (B1), B: (A1, C2), C: (B2) ...

### Route calculation

- *Static or Non-Adapting*
  - paths pre-caculated
  - not based on current topology or network load
  - paths are fixed
- *Dynamic or Adaptive*
  - paths caculated periodicly
  - calculation based on network metrics
    - bandwidth
    - delay

- Source based
  - path calculated at the source
  - packets carry entire route
  - path cannot change (unless recalculated)
- Distributed
  - every router in the network calculates forward paths
  - paths can change as packets go from router to another



