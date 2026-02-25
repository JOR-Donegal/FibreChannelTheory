# Protocol Stack

To understand the terminology and configuration and to troubleshoot equipment, it is necessary to have at least some understanding of the fibre channel protocol stack. It is completely different to the seven-layer model from the OSI that we use when teaching conventional networking. It does not include ethernet, IP, UDP/TCP, or any of the other concepts with which you may be familiar.

Most complex architectures are written as a protocol stack. This allows us to interact at the most appropriate level whilst maintaining all the other levels unchanged.

Fibre Channel was written as a fully integrated communications stack, it does not need to use IP, Ethernet, or any other conventional networking technology. However, for ease of support in operating systems and applications, it may be easiest to present the upper layers of applications as other standard protocols; this is performed by FC layer 4.
Layers FC-0 to FC-3 implement the fibre channel transmission technology and the fundamental communication techniques.
