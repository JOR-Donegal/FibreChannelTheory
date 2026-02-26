# LUN Masking

In the previous example, we prevented unauthorized hosts from accessing each other. We also explicitly stated which hosts could access the Target/SAN. But the target exposes multiple LUNs, we also need to protect these, so only the appropriate server can access the appropriate LUN.

_LUN masking_ is implemented on the SAN. In the example above, I would create a LUN for CLUST01 and implement LUN masking so that only the WWPNs of the servers in CLUST01 could access it. I would create a second LUN for CLUST02 and set LUN masking appropriate to the WWPNs of the server in CLUST02.

In a production system, zoning and LUN masking should be implemented.