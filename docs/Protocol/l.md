# FC-4
## Upper Layer Protocol Mapping

Login, the assignment of addresses and the negotiation of service parameters happens at FC-4. It is at this point that a node can ascertain if it is part of a point-to-point topology or is connected to a fabric. 
Low level addressing in FC is analogous to the MAC address of an Ethernet card and it is based on the allocation of 64-bit names, called World-Wide Names or WWNs. Each company has a 24 bit organizationally unique identifier or OUI included in the WWN. There are two types of WWN.

Every node is assigned a World-Wide Node Name (WWNN) specific to that host. If there is a multi-port HBA, the WWNN is common across all ports.

Every port is assigned a World-Wide Port Name (WWPN), the WWPN is burned into the individual port at manufacture, like a MAC address and it is globally unique.

A node with a dual port HBA will have a single WWNN and two WWPNs. We normally assign an alias to the WWPN to make in human readable and more easy to work with.

In a fabric, each WWPN is assigned a 24-bit port address during fabric login, which are used within FC frames as the source and destination IDs. In arbitrated loop, every WWPN is assigned an 8-bit address.

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig13.jpg">
<figcaption>Fig 13. WW Names Array.</figcaption>
</figure>

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig14.jpg">
<figcaption>Fig 14. WW Names HBA.</figcaption>
</figure>

A fibre channel address is assigned by the switch during the fabric login process; this is analogous to an IP address.

Each switch in a fabric is assigned a unique eight-bit domain ID (DID) by the principal switch in the fabric, of which 239 address are available. Fabric services reserve some of these addresses, we will see these later. This is analogous to the network part of an IP address. Switches must have unique DIDs before they can merge and hold a routing table which allows them to communicate across the fabric.

In a large switch or director, we can have many ports. We can divide these into areas and 8 bits are available for area definition. 8 bits are available to distinguish between ports.

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/eq1.jpg">
<figcaption>Eq 1. Nodes per fabric.</figcaption>
</figure>

FC-4 provides the services which allow upper layer protocols (ULPs) to map services like SCSI into FC.