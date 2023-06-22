# Switching

A stitched network consists of a series of interlined noses called **switches**.
Switches are devices capable of creating temporary connections between two or
more devices lined to the switch.

## Circuit-switched networks

1. Circuit switching takes place at the physical layer.
2. Before starting communication, the stations must make a reservation for the
  resources to be used during the communication. These resources must remain
  dedicated during the entire duration of a phone call until the teardown phase.
3. There is a continuous flow of data sent by the source station and received by
  the destination station.
4. The switches route the data (call) based on their occupied band (TDM) or time
  slot (FDM).

### Three phases

| Phase | Description |
| --- | --- |
| Connection setup | Before the two parties can communicate, a dedicated circuit (combination of channels) needs to be established. The end systems are normally connected through dedicated lines to the switches, so connection setup means creating dedicated channels between the switches. |
| Data transfer (phone converstation) | After the establishment of the dedicated circuit, the two parties can communicate. |
| Connection teardown | When one of the parties needs to disconnect, a signal is sent to each switch to release the resources. |

### Efficiency

Circuit-switched networks are not efficient because resources are allocated for
the entire duration of the connection. **These resources are unavailable for the
other users**.

### Delay

The delay in circuit-switched networks is minimal. The total delay is due to the
time needed to create the connection, transfer data and disconnect the circuit.

In data communication, a message needs to be divided into packets of fixed or
variable size. The size of the packet is determined by the network and the
governing protocol.

In packet switching, there is no resource allocation for a packet. Resources are
allocated on demand. The allocation is done on a first come, first-served basis.
When a switch receives a packet, the packet must wait for processing. **This may
create delay**.

## Datagram networks

### Routing table

In a **datagram network**, each packet is created independently even if a packet
is part of multipacket transmission. The network treats it as it existed alone.
Packets in this approach are referred to as **datagrams**.

The datagram networks are **connectionless networks**, which means that the
packet switch does not keep information about the connection state. There are no
setup or teardown phases. Each packet is treated the same way by a switch
regardless of its source or destination.

Packets are routed to their destinations by applying routing tables. Each switch
has a routing table. The routing tables are dynamic and are updated
periodically. The destination addresses and the corresponding forwarding output
interfaces are required in the tables.

Every packet in a datagram network carries a header that contains the
destination address of the packet. When the switch receives the packet, this
destination address is examined. The routing table is consulted to find the
corresponding interface through which the packet should be forwarded.

### Delay

There may be significant delay in a datagram network. Each packet may wait at a
switch before it is forwarded. Since not all packets in a message travel through
the same switches, the delay is not uniform for the packets of a message.

$$
\begin{array}{rcl}
  TD & = & 3.TT + 3.PD + W_1 + W_2 \\\\
  \sf 3.total\ delay & = & \sf 3.transmission\ time + propagation\ delay + {waiting\ time}_1 + {waiting\ time}_2
\end{array}
$$

### Efficiency

The efficiency of a datagram network is better than that of a circuit-switched
network. Resources are allocated only when there are packets to be transferred.
Resources can be easily shared and de-allocated for packets from other sources.

## Virtual-circuit networks

A **virtual-circuit network** has some characteristics of a circuit-switched
network and a datagram network.

1. As in a **circuit-switched network**, there are setup and teardown phases in
  addition to the data transfer phase.
2. As in a **datagram network**, data are packetized.
3. As in a **circuit-switched network**, all packets follows the same path
  established during the setup phase.
4. A virtual-circuit network is implemented in the data link layer.

### VCI

The identifier that is used for data transfer is called the **virtual-circuit
identifier (VCI)**. A VCI is used by a frame between switches. When a frame
arrives at a switch, it has certain VCI. When is leaves, it has a different VCI.

### Three phases

| Phase | Description |
| --- | --- |
| Setup | &ndash; |
| Data transfer | To transfer a frame from a service to its destination, all switches need to have a table entry for a virtual circuit. The switch holds four pieces of information for each virtual circuit that is already setup:<br><br>- incoming interface & VCI<br>- outgoing interface & VCI<br><br>Each switch changes the VCI and routes the frame.<br><br>$$\sf total\ delay = 3.transmission\ time + 3.propagation\ delay + setup\ delay + teardown\ delay$$ |
| Teardown | &ndash; |
