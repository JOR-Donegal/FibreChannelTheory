# Introduction

!!! abstract "Fibre Channel Theory"

Fibre channel was originally conceived as a replacement for existing legacy networking technologies like Ethernet and FDDI and was intended for backbone connections. In the early 1990s IBM had developed a fast and reliable storage interface technology (SSA) and Seagate needed a technology to compete; fibre channel was adapted c. 1994 and rapidly became the market leader. It was one of the first technologies developed for this purpose.

At time of writing, Fibre Channel is standardized by the Technical Committee T11 (T11) of the International Committee for Information Technology Standards (INCITS). You should have previously covered SCSI; fibre channel uses SCSI as its application protocol. The physical topology is normally based on fibre optic cables but there are several choices based on the application; see topologies later in these notes.

Fibre Channel is still used for very high-performance systems; _Fibre Channel Protocol_ (FCP) is ideal for low latency and high throughput applications; it was specifically designed for that. However commercially, the market for the equipment seems to be stagnating. This technology will be around for the rest of my career, but I do not see its penetration increasing. It is expensive and complex, and its complexity is unique to itself as compared to the ubiquity of conventional networking with ethernet and TCP/IP. Fibre Channel over Ethernet (FCoE) does use conventional technology for transport; however, I see very little penetration of this technology. In terms of volume shipments, iSCSI seems to be currently winning this race.

In these notes I will introduce fibre channel concisely not comprehensively. In my experience equipment and functionality differs from manufacturer to manufacturer and each implementation which uses different equipment tends to be a bit unique! The content covered here should be generic and enough to give you a starting point on any real system.

I am not going to cover more complex issues, like fibre channel routing, ALUA/path optimization or MPIO.