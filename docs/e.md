# Fabric Shortest Path First

There are some advantages to having mesh connections, however most designs only use a single path. From an availability perspective, separate fabrics will give a much better result than a messy mesh.

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig7.jpg">
<figcaption>Fig 9. Mesh.</figcaption>
</figure>

The same logic applies, whether we are using a full mesh or partial mesh. In almost every case only a single path will be used at any one time between initiator and target. A routing protocol, _Fibre Shortest Path First_ (FSPF) ensures this.
FSPF is a link state routing protocol originally created by Brocade and is like OSPF as used in conventional networking. The domain ID which is associated with each unique switch in a fabric, acts as the routing ID of the switch. When you dig into the operation, the principal switch has a database, each switch is a hop and each ISL has a cost based on its bandwidth. The result is a loop-free topology. Routes are unidirectional, and it is possible to have different outbound and return paths.

I have never had to manually tinker with FSPF, it is on by default and automatically calculates the best path between any two switches on the fabric. It dynamically computes the shortest and quickest path to a fabric and identifies alternative paths in the event of a failure of the optimal path. There is an equivalent to ECMP, and in some cases traffic can be distributed over multiple ISL’s.

In previous examples I have shown the optimal design to use separate fabrics. However as with a spanning tree-based conventional network, adding redundant links from switch to switch within a fabric is an appropriate design and will improve availability. Doing this optimally can be complex and in every case, you need to read the manufacturers recommendations. For example, with Cisco equipment, we can bond redundant fibre channel links on ISL’s between switches as a port channel, like the way we do link aggregation on a conventional network. ISL trunking is available between switches and again, configuration is very dependent on a manufacturer’s implementation.

For redundancy, design with two completely separate fabrics, A and B. Mesh within a fabric, but never between fabrics.