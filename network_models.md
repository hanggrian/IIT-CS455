# Network models

The internet model sometimes called the TCP/IP protocol suite is composed of
five ordered layers. In developing the model, the designers distilled the
process of transmitting data to the most fundamental elements, identified the
networking functions and collected those functions into discrete groups that
became the layers. Each layer defines a family of functions distinct from those
of other layers.

## Internet layers

Each layers calls upon the services of the layer just below it. Layer 3, for
example, uses the servies provided by layer 2 and provides the services for
layer 4.

Layer | Duties
--- | ---
Application | E-mail, web browsing, file transfer.
Transport | Port addressing, segmentation and reassembly, connection control, flow control, error control.
Network | Logical addressing, routing, internetworking, packetizing, fragmentation, address resolution.
Data link | Framing, physical addressing, flow control, error control, access control.
Physical | Physical characteristics of interfaces and media, representation of bits, data rate, synchronization of bits.

## OSI model

*The Open System Interconnection (OSI)* model was designed by the international
organization for standardization. The OSI model is a theoretical model designed
to show how a protocol stack should be implemented.

Layer | Description
--- | ---
Application | &ndash;
**Presentation** | Translates data to a standard format, manages encryption and data compression.
**Session** | Establishes sessions between communicating applications on the communicating computers (devices).
Transport | &ndash;
Network | &ndash;
Data link | &ndash;
Physical | &ndash;
