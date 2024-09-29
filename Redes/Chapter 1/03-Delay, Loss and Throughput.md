> [!WARNING] Delay
> A packet starts in a host, passes through a series of routers, and ends its journey in another host. 
> As a packet travels from one node to the subsequent node along this path, the packet suffers from several types of delays at each node along the path.

## Types of Delay


> [!IMPORTANT] Processing Delay
> The time required to examine the packet's header and determine where to direct the packet. It can include other factors, such as the time needed to check for bit-level errors in the packet that occurred in transmitting the packet's bits from the upstream node to router A.


> [!IMPORTANT] Queuing Delay
> At the Queue, the packet experiences a queuing delay as it waits to be transmitted onto the link. The length of the queuing delay of a specific packet will depend on the number of earlier-arriving packets that are queued and waiting for transmission onto the link.


> [!IMPORTANT] Transmission Delay
> Our packet can be transmitted only after all the packets that have arrived before it have been transmitted.

$$t_{delay} = L/R$$


> [!IMPORTANT] Propagation Delay
> The amount of time required for the router to push out the packet. It's a function of the packet's length and the transmission rate of the link, but has nothing to do with the distance between the two routers.
> Is the time it takes a bit to propagate from one router to the next.

---


> [!IMPORTANT] Throughput
> The rate(in bits/sec) at which host B is receiving a file.

