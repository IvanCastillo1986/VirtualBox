# Networking in VirtualBox
VirtualBox hypervisor provides a variety of different emulated hardware networking cards. The default is the "PCNet FAST 3", since it's supported by most major operating systems.
There's also the family of "virtio-net" networking adapters, which is an open-source virtualized networking card. These are not real hardware cards being emulated by the hypervisor. They are created with the purpose of being virtualized, for virtualized environments like Linux. VirtualBox provides support for their drivers. 

## Networking Modes
Each adapter can be configured to operate in 1 of 8 different modes:
* **Not Attached**  -  no connection, even though a NIC is present.
* **NAT**  -  this mode is default. Isolated access to the internet (WAN), but no access to other devices in LAN.
* **NAT Network**  -  devices are connected to a shared virtual router, allowing them to communicate with each other, as long as they are on the same network segment. Also provides internet access to each device. 
* **Bridged Networking**  -  this mode is necessary for simulating a configurable network. You'll be needing this mode for each device in any subnet. Allows devices to communicate to each other across different subnets via a router virtual machine's (VM's) connection (which is also bridged). Under-the-hood, VirtualBox is connecting directly to the host machine's NIC, bypassing the host operating system's network stack. The way it works is VirtualBox uses a "net filter" device driver on your host system, which filters data from the physical network adapter. This allows VirtualBox to intercept data from the physical network and inject data into it, which is like creating a new network interface using software. The host can receive and send data using that interface. 
* **Internal Networking**  -  creates an isolated software-based network which allows VMs to directly communicate with each other, without access to the internet. This provides a great environment for secure testing when you'd like multiple separate VMs to talk to each other, without the risk of contaminating your other VMs that are not involved with the process.
* **Host-only Networking**  -  only provides connectivity between select virtual machines and the host. It's like the "internal networking" mode, with a connection to the host machine. No internet connection.
* **Cloud Networking**  -  connects your VM to a subnet in a remote cloud service.
* **Generic Networking**  -  an advanced mode which shares the same generic network interface. Offers deep control over IP and subnet settings, allowing users to define their own network behavior beyond typical guest/host isolation. Includes two sub-modes:
    * **UDP Tunnel**  -  connects VMs running on different hosts directly over an existing network infrastructure.
    * **Virtual Distributed Ethernet (VDE) networking**  -  connects VMS across different hosts with a VDE switch (vSwitch) on Linux or FreeBSD host. The Oracle packages do not include it, so it requires compiling VirtualBox from source (very advanced). 


For our purposes, we'll be equiping every VM with at least one Network Interface Card (NIC) in Bridged Mode. This will provide access to our Alpine gateway router, which will connect our subnets.

