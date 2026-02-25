# Topologies

Three different topologies are standardized.
- Fabric (FC-SW)
- Arbitrated Loop (FC-AL)
- Point to point (FC-PtP)

## FC-SW
A fabric topology includes one or more fibre channel switches and allows any devices to communicate simultaneously, both ways.
Connections are crossed so that RX on one side connects to TX on the other. 
One of the oldest companies in this business is called Brocade…which is a fabric.

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig2.jpg">
<figcaption>Fig 2. Simple fabric.</figcaption>
</figure>

Switches can be linked together, and we call these _inter-switch links_ or ISLs. 
These use completely different protocols from host port connections.
Very large switches for enterprise use are called directors.
Even a small deployment will normally have redundant paths and components and will be designed without a single point of failure, for high availability.

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig3.jpg">
<figcaption>Fig 3. Redundant fabric.</figcaption>
</figure>

## FC-AL
In an arbitrated loop, a unidirectional ring is constructed which allows any two devices to communicate with each other 
one way at a time. 
The output channel of one device is connected to the input channel of the next device in the loop.
In some cases, a FC hub may be used as a concentrator to simplify wiring. Hubs have some of the same advantages 
as the network devices of the same name. 
For example, they can bridge a defective device, leaving the rest of the loop still functional.

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig4.jpg">
<figcaption>Fig 4. Arbitrated loop.</figcaption>
</figure>

As with network devices, we can have unmanaged, managed and switched hubs. 
A switched hub is almost a switch and can connect devices at wire speed, duplex. 
However, they do not support many of the features typical in a switch, such as zoning.
The average throughput per server is the line speed divided by the number of nodes. 
For example, on a 2GFC system with 8 nodes, 200MB/s divided by 8 gives an average bandwidth per node of 25MB/s. Up to 126 nodes are supported.
Two types of arbitrated loop exist. A private loop closes on itself as shown in the diagram and each device has an L port. A public loop connects to a fabric via at least one switch and end devices must have an NL port supporting both fabric and arbitrated loop.

## FC-PtP
A point-to-point topology allows bi-directional communications to occur between two devices. 
Connections are crossed so that RX on one side connects to TX on the other.

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig5.jpg">
<figcaption>Fig 5. Point to Point.</figcaption>
</figure>