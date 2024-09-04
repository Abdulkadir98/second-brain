
**TCP**
It is a reliable connection-oriented protocol, it only runs on end hosts and not on any networking components (routers, switches etc)

TCP Segment
The two most critical fields in the TCP segment is the Sequence number and the Acknowledgment number.

Consider two hosts A and B, B is the client and A is the server
Sequence # - It is the starting byte of the data payload in the TCP segment
Acknowledgment # - It is the number that host A puts in its segment as the sequence number of the next byte it expects host B to send

Another way to say is that if host B receives 79 as the ack # then that means all bytes upto 78 have been received by host A
