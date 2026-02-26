# Summary

The following services are available on any fibre channel network.

| Address    | Function | Description | 
| -------- | ------- | ------- |
| 0xFFFFFF | Broadcast address ||
| 0xFFFFFE | Fabric login server | Used during the initial part of the node’s login process |
| 0xFFFFFD | Fabric controller | Manages Registered State Change Notifications (RSCN) which keep name servers updated on all switches |
| 0xFFFFFC | Name server or Directory server | Responsible for name registration and management of node ports |
| 0xFFFFFB | Time server | Since time to the member switches in the fabric from the principal switch |
| 0xFFFFFA | Management server | Manages the fabric. This is the only service which is user configurable. It provides an un-zoned view of the overall fabric configuration. |
| 0xFFFFF9 | QoS server ||
| 0xFFFFF8 | Alias server || 
| 0xFFFFF7 | Key distribution server ||
| 0xFFFFF6 | Clock synchronization server ||
| 0xFFFFF5 | Multicast server ||
