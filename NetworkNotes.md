# Network Notes 

### Different types of networks 
Order from smallest to largest access 

1. PAN: personal area network (personal level, wireless technolog or wire connection, transfer small files e.g. music and files) 
1. LAN: local area network, group of devices in same building or close proximity, most common is ethernet lan using a switch
1. WLAN: wireless lan, at least two devices that use wireless connection to create a LAN (wifi router) 
1. CAN: Campus area network, joins 2 LANS together within limited area (e.g. university w different departments) 
1. MAN: Metropolitan Area network, connected thru high speed connection like fiber optic network, shared data within city 
1. SAN: storage Area network, high speed network, provides access to a lot of data, uses switches, disk arrays, servers, not affected by network traffic (or bottlenecks) cause theyre not in LAN, theyre cut off 
1. WAN: Wide area network, largest type, country/continent/global, internet is example 

### Differences between Moden and Router 

- Modem brings internet to home/business, maintains connection to internet service provider, computer only reads digital signals, while internet uses only analog signals, moden converts between the two (modulates and demodulates) 
- word Modem = modulator and demodulator 
- Router comes in after modem, diff types of routers but do same thing, routers pass internet connection to all devices, common example is router with multiple switch so you can connect many devices at once, and wireless access point. Technically dont need router bc you can just connect one device to modem. 
- Different types of modens: cable (colaxial cable e.g. television) and DSL (thruu phone line), internet modens are usually a hybrid
- Most routers have integrated switch, you only need switch if you need more wire connections 

### Firewalls 

- prevents unathorised access from private network (safety barrier)
- especially important to large organisation with data servers
- stops harmful activity before
- filters access control point, based on certain rules (admin decides)
- allows or denies permissions
- E.g.  based on IP address, domain name, protocols, programs, ports, key words
- Host-based firewall, firewall that is installed on computer/device, protects that one device only (can come with comp default or can download from third party)
- NEtwork firewall, mix of hardware and software,  protects entire network
- can be stand alone firewall (used for big cooperations), can be integrated within router, or can have cloud firewall

### Differences between a hub, switch and router 

Hub: connects devices to internal network (accepts ethernet) , does not filter and is not considered intelligent, can only know whether device is connected, all devices can see information because hub can not differentiate where to send packet (data is copied to all ports) 
- only physical connection
- uneccessary traffic (wasting badnwidth) and also insecure

Switch - similar to hub but is intelligent, learns physical addresses of devices (mac addresses) and can send packets to intended port 

Switch and hub used to exchange data on own network, can't access any other data because can't read IP addresses

Router - routes and forwards data from one network to another, network checks IP address and if its for its address, then recieved, if else, sends to another. it is the gateway for a network. 

TLDR: Hubs and switches create networks, routers connect networks 

### Network Topologies 

Topologies - layout of how networks communicate with diff devices 

**Wired Topologies**

1. Star Topology

- all devices connected trhu central wiring point (e..g hub or sswitch), all data passsses cen
- PROS: if comp fails or connection fails, then other cmputers not affected. CON: if hub or switch fails, all computers on center point affect (single pint of failure, all nework goes down)

2. Ring Topolgy 

- all devvices connect tot each other thru close ring (each has two neighbours)
- very old and rarely used
- PROS: easy to install and easy to trouble shoot CON: if there is one single cable break, then whole network goes down

3. Bus Topology 

- very old and rarely used
- each computer is connected to device or back bone (colaxial backbone)
- each computer connect to colacial backbone thru BNC connectors (T connectorss)
- PROS: cheap and easy tto implement CON: every cable terminate on both endss, no open connections including ends, if a computer is removed or terminater loose, cable opens and data bounces back, and then data flow disrupted

4. Mesh 

- each computer is connected to other computers
- PROS: high redundancy level CONS: expensive cause of how many cables need (not used for LAN or small networks, e.g. of mesh is internet)

**Wireless Topologies**

5. Infrastructure

- combination of wire and wireless
- similar to star (have physical wires connected to switch, but also have WAN (wireless access point) connected to cable and then devices can connect to WAN, can have multitple WANS)

6. Ad Hoc 

- very simple
- no need of physical infrasstructure
- all devices wirelessly connect to each other without ussing centralised device
- each device responsible for security
- PROS: eeasy and fasst to sshare files without need of wireless network

7. Wireless Mesh

- ssimilar to mesh but exception that they are wirelessly connected
- e.g. modem → switch → multiple Wireless acceess point
- PRO: very redundant

### IP Addresses

- identifier for a device on a network
- consists of two parts: network address and host address
- Two types: IPv 4. and IP v. 6
    - IPv4 is 32 bit written as four numberss seperated by period
    - each number is called an octet or 8 binary bits
    - range from 0-255
    - creates over 4 billion diff addresses
    - computers and networks only understand addresses in binary format
- IP v v6 next generation, diff is alphabetic and 128 hexadecimal address
- 340 undecillion diff ip addresssses

### Traceroute

- command line utilitiy
- shows route data packet takes
- trace route is just a tool to find the route that a packet goess from sender to reciever
- with traceroute, you can find problems like bottle necks or if curious abt paths
- trace route tells more info than ping
- pings final destination and every route on its way + time for each router in mls + ip address of each router + domain name if available
    - but big jumps in time may mean big jump in location e.g. change of continentt
- trying to find consistent round trip times (consistent and slight gradual increase)
- 3 data packets sent so it can isolate issues
- trace route also tells us number of hops to network
- final destination trace route is approx same time as ping
    - ping only displays time of final destination
