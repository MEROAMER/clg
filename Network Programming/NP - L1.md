# Lec1

slides from 55-85 are practical example, read them.
## Script intro
computer language, file exe without compiling.
server side: PHP | client side: JS.

- advantages:
	open source(user view/edit src code)
	file ain't compiling(faster to develop-some prototype)
	easy(learn, write, port between os)

- dis adv:
	open source(company's prohibit code avail)
	requires interpreter install

- Tools:
	NetBeans(Java, supports PHP)
	XAMPP(PHP server, <Apache http srv, MYSQL DB, interpreters)

## Intro
- Definitions:
	- Networking: process of connecting 2/more computers (via different communication links) for ==sharing with highest speed==.
	- Network Medium: physical medium(coaxial, copper, finer optical cables || radio spectrum) => transmit data @different rates bit/sec.
	- NIC Card: trans PC's parallel stream -> medium's serial stream.
	- protocols: rules followed in network(speed of trans, size of data file, security, flow control).
	- Proxy: (aka cache server) hides internal network from external world, no direct communication, only thro proxy(safe from exploits).

- Statements
	computers share: info(email, file) + resources(printer, internet)
	sharing as fast as possible => use ==electric cables || wireless radio signals==.
	devices: Hosts, End system, End devices.
	sender break data into Segments, wrap with network info to Packet, reassembled @receiver.
	
	each net requires Specialized HW, SW.
	![[media/15.png]]
	1. Client computers: aka workstations, used t access the shared resources.
	2. Server computers: provide shared resources, runs many specialized resources t ctrl shared resources.
	3. Network interface card(NIC): ==interface== enables computer t communicate over network, MUST HAVE ONE to connect to network.
	4. Communication links: ==physical or wireless media==, MUST HAVE to trans data.
	5. Switches: ==mediator device== connects>2 computers t network, has no. of ports each connect 1 pc.
	6. Routers: ==intermediate device== speaks all language of network, communicates DIFFERENT networks.

	Types of networks:
	1. PAN: few meters between ==wireless== devices.
	2. LAN: small geo size(room, floor, building, campus)
	3. MAN: 1-30 Miles(city).
	4. WAN: large network(parts of state, multiple states, country, world).
	5. ![[media/14.png]]

	Benefits of Networking:
	1. Info sharing: ex(store data in centralized server)
	2. Resources sharing: allow track usage of resources
	3. Application sharing: most common in companies.

	NIC: aka network adapter card NAC || Ethernet card || LAN card
	converts PC's parallel data stream to serial stream for media(medium -wires, wireless- that connects network)

	Proxy: acts as client for server, looks for the page in its cache, if not found, uses its own IP address to request it, forward it to user.

