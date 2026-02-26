# Fabric Login

The _fabric login server_ assigns a fabric address to each fabric node. The fabric address is a 24-bit address containing 3 x three-byte nodes.

- The domain ID representing each separate switch in the fabric.
- The port area number of the port where the node is attached.
- The arbitrated loop physical address if it exists, or the port ID.

 When storage or host devices are powered on and connected, they must login to the fabric. When a fabric login (FLOGI) occurs, it establishes a session between an N-port and an F-port. The node sends a FLOGI frame with its WWN to the fabric login server on the switch and a 24-bit Fibre Channel ID (FCID) address is assigned. The FCID is constructed from the switch’s domain ID and the switch port the host is plugged into. If the WWN is a little bit like a MAC address, then the FCID could be considered like an IP address. Switches maintain a table with WWPN to FCID mappings and the FCID is used across the fabric for routing.

The N-port registers with the fibre channel name server (FCNS) on the switch, indicating its WWN, port type and FC address. A port login (PLOGI) now occurs between two end nodes to exchange service parameters and logs the device into the name server to register its information and query for other devices that share the same zone. The node is now connected.  Once a node has completed fabric and port login, it can query the name server and identify other nodes to connect to.

A process login (PRLI) can now occur between the application stacks on the two end nodes.
This all sounds mildly complicated compared to conventional networking; but it is not! We have just done the equivalent of all the ethernet, IP, DHCP, DNS, service discovery and AAA required in the fibre channel network. And it all works out of the box without any user intervention, at least on simple networks; sometimes!

All this functionality gives the fabric base information which can be used for more complicated tasks which we will not be covering, like path optimization and MPIO.

When two switches are connected, the login process is a little different. Switches exchange frames to establish the connection which uses an E port. An initialization frame, called the Exchange Link Parameters (ELP) frame is exchanged. This is not a negotiation and if parameters do not match a link does not occur. Once an acknowledgement frame is received the switches transmit Exchange Switch Capabilities (ESC) frames, exchanging routing protocols and agreeing on a common routing protocol. After acknowledgement, an Exchange Fabric Parameters (EFP) frame is transmitted requesting principal switch priority and a domain ID list.

A Registered State Change Notification (RSCN) is a notification frame used to notify all devices of fabric changes.