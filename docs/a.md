# Components

A fibre channel SAN has nodes which can be servers or storage. The node port on a server is normally provided by a host-bus adapter or HBA with two paths, one for transmit and one for receive

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig1.jpg">
<figcaption>Fig 1. Server.</figcaption>
</figure>

Every device has an 8-byte World Wide Name (WWN), the fibre channel equivalent to a MAC address. A node has a World-Wide Node Name (WWNN) and a switch port has a _World-Wide Port Name_ (WWPN). A node which will consume storage is called an _initiator_. A node which will provide storage is called a _target_.

Typically, we will have two ports on a _Host Bus Adapter_ (HBA) for redundancy and load balancing. Two separate single port HBA cards would also be an option. Do an Internet search on EMC’s PowerPath software to see the kind of things we can do by having two ports.

We have specific cabling and connectors we can use. Typically, this will be a fibre optic cable, most commonly bright blue in color for modern fibre (OM3, 4, 5). Legacy fibres are bright orange. There are two types of fibre cables we can use.

Multimode fibre is common on LANs and for short inter-connects and is the most common way of interconnecting with Fibre Channel.

Single mode fibre has much more expensive transceivers but is good for links of typically up to 10km. At this point, read the accompanying notes on fibre types and connectors.

We can also connect Fibre Channel over copper cables. This will generally be much cheaper but is good for very short distances only.
We have interconnecting devices such as _directors_, _switches_, and _hubs_. 
- Hubs provide very limited connectivity and scalability but are very cheap. 
- Switches are intelligent, complex, and expensive! Switches normally have a fixed port count and configuration. 
- Directors are modular and can be expanded using line cards or blades. 

High end switches and directors will normally be high availability and have redundant components. When switches are interconnected, they do so with an awareness of each other and in a tightly integrated way. One switch becomes the _principal switch_ of a single integrated entity; we call this a _fabric_ (different references spell principal and principle!!). A switch cannot forward between fabrics, this requires a _fibre channel router_. Each fabric has its own addressing scheme and a router uses FC-NAT to translate between them.

We will generally have management software which presents the entire storage architecture as a single management interface. Typically, the topology will be visible as will the management status of all devices. For anything other than trivial systems, there will be separate, independent, redundant fabrics.

In such a large and scalable environment, there should be some way of restricting access between initiators and targets; the fibre channel equivalent of a VLAN. This is the concept of _zones_, segments of the fabric where devices can communicate with each other. There is a section on zoning later in these notes.