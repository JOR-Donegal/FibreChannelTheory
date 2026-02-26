# Virtualization

## Virtualization in the fabric

One approach to building a reliable infrastructure is to virtualize the switch. Very simply you _partition_ the switch or director into two or more separate logical devices. You treat them as if they are separate switches/fabrics and do not interconnect with the physical fibre. Although there are still dependencies in hardware, this is a very useful technique.

## Virtualization in the SAN

Physical LUNs are presented to a virtualization layer in the SAN, which then exposes LUNs and block storage to the servers which require it. The virtualization layer of the SAN appears as if it is a host to the storage array. It appears as if it is a SAN to the servers.

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig16.jpg">
<figcaption>Fig 16. Virtualization.</figcaption>
</figure>

Although this may seem overly complex, this can be very useful. For example, when I am moving physical storage for service and maintenance, I need to move LUNs from one SAN to another. I could do this several ways, but the easiest would be to copy the LUN from one SAN to another and then change the backing to the virtual volume.

I could also add storage to a virtual volume very easily by making it available at the backend and merging it at the virtual volume layer.

We can have a virtual SAN. We can set up a fabric as if it were multiple switches, each with its own domain name, name servers, zoning, etc. This has all the same advantages we use virtualization for in other technologies, such as scalability, management, security, etc. Two or more completely different SANs can live on the same physical infrastructure. Virtual SAN technology has different trade names and is implemented slightly differently from manufacturer to manufacturer.

