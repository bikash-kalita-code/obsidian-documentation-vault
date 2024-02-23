OSI Model - Open Systems Interconnection Model

### Why do we need a communication model?
- [[Dictionary#^2fe824 | Agnostic]] applications
	- Without a standard model, your application must have knowledge of the underlying network medium
	- Image if you have to author different version of your apps so that it works on Wi-Fi vs ethernet vs LTE vs fibre
- Network Equipment Management
	- Without a standard model, upgrading network equipments becomes difficult
- [[Dictionary#^eaf843 | Decoupled]] Innovation
	- Innovations can be done in each layer separately without affecting the rest of the models

## What is the OSI Model?
7 layers each describing a specific networking component
- Layer 7 - Application - HTTP/FTP/gRPC
- Layer 6 - Presentation - Encoding, Serialization
- Layer 5 - Session - Connection Establishment, TLS
- Layer 4 - Transport - UDP/TCP
- Layer 3 - Network - IP
- Layer 2 - Data Link - Frames, Mac address Ethernet
- Layer 1 - Physical - Electric signals, fibre or radio waves

We send frames in Layer 2, packets in Layer 3, segment in Layer 4.

### The OSI Layers - an Example (Sender)
Example sending a POST request to an HTTPS webpage
- Layer 7 - Application
	- POST request with JSON data to HTTPS server
- Layer 6 - Presentation
	- Serialize JSON to flat byte strings
- Layer 5 - Session
	- Request to establish TCP connection / TLS
- Layer 4 - Transport
	- Sends SYN request target port 443
- Layer 3 - Network
	- SYN is placed an IP packet(s) and adds the source/destination IPs
- Layer 2 - Data Link
	- Each packet goes into a single frame and adds the source/destination MAC addresses
- Layer 1 - Physical
	- Each frame becomes string of bits which converted into either a radio signal (Wi-Fi), electric signal (ethernet), or light(fibre) 
### The OSI Layers - an Example (Receiver)
Receiver computer receives the POST request the other way around
- Layer 1 - Physical
	- Radio, electric or light is received and converted into digital bits
- Layer 2 - Data Link
	- The bits from layer 1 is assembled into frames
- Layer 3 - Network
	- The frames from Layer 2 are assembled into IP packet
- Layer 4 - Transport
	- The IP packets from Layer 3 are assembled into TCP segments
	- Deals with Congestion control/flow control/retransmission in case of TCP
	- If Segment is SYN we don't need to go further into more layers as we are still processing the connection request 
- Layer 5 - Session
	- The connection session is established or identified
	- We only arrive this layer when necessary (three way handshake is done)
- Layer 6 - Presentation
	- Deserialize flat byte strings back to JSON for the app to consume
- Layer 7 - Application
	- Application understands the JSON POST request and your express json or apache request receive event is triggered 

### The shortcomings of the OSI Model
- OSI Model has too many layers which can be hard to comprehend
- Hard to argue about which layer does what
- Simpler to deal with Layers 5-6-7 as just one layer, application
- TCP/IP Model does just that
- Physical layer is not officially covered in the model
### TCP/IP Model
- Much simpler than OSI just 4 layers
- Application (Layer 5,6 and 7)
- Transport (Layer 4)
- Internet (Layer 3)
- Data Link (Layer 2)
- Physical layer is not officially covered in the model