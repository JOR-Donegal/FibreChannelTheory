# FC-2
## Switching and Flow Control
FC-2 is the data transfer layer and is responsible for data transfer and flow control. It establishes a range of service classes to support application requirements.

End devices exchange information units. These are communications relating to an upper-level protocol like SCSI.
To send information units, end devices are assigned an exchange for each communication which must occur, and these exchanges happen sequentially.

A sequence is a collection of frames. One sequence is transferred after another in an exchange and the sequence is not complete until every one of its frames has been delivered. A sequence might (for example) be a file write to a SAN, or a database update and if a frame is missed, the whole sequence is repeated.        

<figure>
<img src = "https://jor-donegal.github.io/FibreChannelTheory/images/fig12.jpg">
<figcaption>Fig 12. Flow Control.</figcaption>
</figure>

FC-2 guarantees that frames are delivered in the correct sequence and the frames themselves are very simple compared to Ethernet or TCP/IP. After the SOF there is a frame header with a destination and source address, a sequence ID, the number of frames in the sequence and the exchange ID. There is a data field with a payload of up to 2112 bytes and finally a CRC followed by an EOF. This is very efficient compared to Ethernet or TCP/IP with 98% of bits accounting for data.  

Flow control exists and can be achieved between communicating ports or end-to-end.

There are six service classes. 

- Class 1 is a little bit like ATM; it is connection oriented and sets up a definite link before transmitting frames. 
- Class 2 is a little bit like TCP, with end-to-end flow and link control. Each frame received is acknowledged. 
- Class 3 is a bit like UDP, with no acknowledgements. 

The final three classes are not currently implemented and typically only class 2 and 3 are used.