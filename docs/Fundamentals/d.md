# Redundant Topologies

As noted previously, for high availability all nontrivial systems will be configured with dual redundant fabrics. That does not mean we are restricted from having redundant links within a fabric, it just means that in our planning, we never cross connect between two fabrics. This causes a lack of diversity and potentially introduces single points of failure.

The simplest fabric is two switches connected and this suffices for a simple site. Assume every node has at least a two port HBA, and for high availability, each port connects to a separate fabric. Separate fabrics have absolutely no dependencies or interconnects. If you do erroneously join two fabrics, this should generate an error, a zoning database conflict, and the port should disable.

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig6.jpg">
<figcaption>Fig 6. Simple Fabric.</figcaption>
</figure>

Switches can be connected in a line, with two lines/fabrics.

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig7.jpg">
<figcaption>Fig 7. Two lines.</figcaption>
</figure>

Once sites become more complex. A core-to-edge fabric topology becomes normal, with a director at the centre of the fabric and switches connected back in a star topology. If we do this with a second director, then there is a dual-redundant A and B network with no overlap.

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig8.jpg">
<figcaption>Fig 8. Director x 2.</figcaption>
</figure>

On large installs, the topology looks almost like a leaf-spine in conventional networking. You could locate a director at either end of a row of cabinets, and place two redundant Top of Rack (ToR) fibre channel switches in each cabinet in the row. This is no simple design, you could make it more complex, each of the switches shown in the diagram could connect multiple other switches.