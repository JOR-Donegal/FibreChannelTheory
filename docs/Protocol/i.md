# FC-1
8b/10b encoding is used at FC-1. Earlier technologies like Ethernet used Manchester Encoding, which was very inefficient.

8b/10b encoding uses ten bit symbols to represent any  eight bit data pattern, and ensures that no more than five ones/zeros in a row can exist in a symbol, allowing both sides of a conversation to maintain timing and synchronization. Thus, a data rate of 100 MB/s requires a raw bit rate of around 1Gb/s.

Symbols not used to represent data can be maintained for control and administration of the link.

FC-1 uses two types of transmission word. A data word is a sequence of four bytes (forty bits in 8b/10b) between a _start of file delimiter_ (SOF) and an _end or file delimiter_ (EOF). Ordered sets are also contained between a SOF and EOF but are delimited by a special character with a unique bit sequence (K28.5). This allows an incoming bit stream to be divided into forty-bit words.

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig11.jpg">
<figcaption>Fig 11. Frame.</figcaption>
</figure>