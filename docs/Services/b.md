# Summary

In a conventional network, Ethernet provides the transport on the local LAN. IP provides the transport between networks. For any effective use of the network, infrastructural services are required. On a conventional network, these minimal services include DNS, DHCP, NTP, SYSLOG, AAA. All these services are very much decoupled from the network, and could be provided by appliances, Linux servers, or in most enterprise networks provided via Active Directory.

When multiple switches are connected via inter-switch links (ISL), a principal switch is automatically elected, and a fabric is formed. It is a little bit like the election that occurs in stacked ethernet switches. The principal switch maintains time for the fabric and manages domain ID assignments.

In fibre channel the services are provided from the fibre channel fabric. A well-known address is reserved, three-byte address, unique for each service. A range of information and services is maintained by FC switches to facilitate the management of the network. Well defined addresses exist for each such service. This will be dealt with later in these notes.