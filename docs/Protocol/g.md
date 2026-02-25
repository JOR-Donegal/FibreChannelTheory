# Protocol Stack

To understand the terminology and configuration and to troubleshoot equipment, it is necessary to have at least some understanding of the fibre channel protocol stack. It is completely different to the seven-layer model from the OSI that we use when teaching conventional networking. 

Most complex architectures are written as a protocol stack. This allows us to interact at the most appropriate level whilst maintaining all the other levels unchanged.

Fibre Channel was written as a fully integrated communications stack, it does not need to use IP, Ethernet, or any other conventional networking technology. However, for ease of support in operating systems and applications, it may be easiest to present the upper layers of applications as other standard protocols; this is performed by FC layer 4.

Layers FC-0 to FC-3 implement the fibre channel transmission technology and the fundamental communication techniques.

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig10.jpg">
<figcaption>Fig 10. Protocol Stack.</figcaption>
</figure>

SCSI was a channel architecture; all devices were access through a specific channel, the SCSI bus. Channels have a single connection daisy-chaining all devices. All devices must be known, and they must share a common protocol, typically the SCSI command and response protocol.

In a network architecture, any device can connect to any device.

Most fibre channel is a combination of both architectures; it implements the SCSI protocol over the Fibre Channel network. Beware, there are proprietary versions which use other top-level protocols, for example, IBM’s FICON.