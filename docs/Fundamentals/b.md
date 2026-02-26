# Port Types
Each port in a fibre channel topology can have a type which determines its function and the protocols it uses. Physically, the ports are all probably identical, however when you define a port type, you define the protocols it supports. Note that some port types are manufacturer dependent and you may not find all these port types on new equipment; you may find port types that I have not mentioned. In every case go back to the manufacturer’s documentation for the equipment you are working with.

| Type    | Description |
| -------- | ------- |
| N-Port | A node port allows for the connection of an end device (server, SAN)|
| F-Port | A fabric port, the port on a switch that an N-node device plugs into |
| L-Port | An arbitrated loop port |
| NL-Port | Can act as an N or L port |
| FL-Port | Allows a fabric to connect to an arbitrated loop |
| E-Port  | Expansion port allows two FC switches to connect |
| G-Port | Generic, a port which configures automatically as any other type |
| B-Port | Allows switches to connect via ATM |
| M-Port | Mirror port |
| U-Port | Universal Port, the base port |