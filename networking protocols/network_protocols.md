# Network Protocols
There are 7 layers for networks.
1. Application
2. Presentation
3. Session
4. Transport
5. Network
6. Datalink
7. Physical

## Application Layer
In application layer we have 2 types
1. Client server protocol
   - HTTP -> 1 connection gets created from which web pages talk to server
   - FTP -> 2 conncections(control and data) gets created for file transfer
   - SMTP/IMAP -> SMTP is used for sending the email and IMAP is used for read/accessing the mail
   - Web sockets -> messenger kind of application like whatsapp. Here clients do not interact with each other.
2. Peer to peer
   - WebRTC -> All can talk to each other and it is fast, This doesn't need server to get involved.

Client server :
Its one directional client to server, communication

Peer to peer :
It is bidirectional.

## Transport Layer
It has 2 types,
1. TCP/IP -> This has ordering of small packets, acknowledgement and connections maintained. If some packets doesn't get acknowledgement then that packet is resent. 
2. UDP -> Here there is no connection maintained and no acknowledgment sent. If some packet misses then it is not an issue, this is used in live streaming. WebRTC uses this protocol.