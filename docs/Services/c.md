# Zoning

When we take a fibre-channel switch out of the box, we normally expect that it will have no zones defined; this is open zoning and for anything other than trivial cases, this is too simple for us to use. We can allocate servers/hosts/initiators and storage/targets to zones. Zoning allows for the creation of subnetworks within a fibre channel infrastructure. Some discrepancies exist in the terminology and functionality from different manufacturers. Zones can overlap, and a device may be in more than one zone. We can allocate initiators and targets to zones by their WWNs; WWN Zoning. In this case, the zoning can withstand changes in cabling or topology; the correct devices will always remain in the correct zones. The downside is that if we change a part on a server (like an HBA) it will no longer work in its original zone. We can allocate based on port addresses to zones in which case the topology is fixed, but it will work in the event of part changes; Port-Based Zoning. We can also zone hybrids and use both strategies within a zone.

- A Zone Set comprises a list of zones or nodes that can talk to each other.
- A Zone Alias can be created to refer to a group of devices in the fabric. For example, suppose I have a cluster of ESXi servers which all need to see the same backing store. I could give this cluster a Zone Alias on the fibre Channel network and treat the entire group of servers as a single entity.

With _soft zoning_, the fabric name service determines which devices are in which zones. When an initiator server asks about a target/storage, it will only be told about the storage which is in the zones to which it has access. However, the devices in other zones are still accessible if the server knows the port address of the other devices. 

Where a server has a persistent record of the devices on an FC network, soft zoning will not remove the ability to access these devices.

With _hard zoning_, you can only access the devices with which you share a common zone. Typically, we allocate to hard zones based on port addresses; in networking terms this is frame filtering.

We can also have virtual FC networks, where the same physical components are shared in a multi-tenancy. Virtual FC networks are logically separate and the name server of one is not visible to the devices on another. In the example below, I use Ix and Tx as aliases for WWPNs.

- Fabric A will have a zone I1-T1 with the WWPN of node I1 and T1.
- Fabric B will have a zone I2-T2 with the WWPN of node I2 and T2.

If the server ESXi01 becomes part of a cluster CLUST01 and SAN1 provides shared storage, the other hosts HBA’s could be added to the zone. You can also zone from a target on some SAN equipment. If there were a second cluster CLUST02, I would create a second zone, so that the servers could connect to the storage, but not connect to the other cluster. I could then aggregate these zones into a zone set.

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig15.jpg">
<figcaption>Fig 15. Masking.</figcaption>
</figure>



