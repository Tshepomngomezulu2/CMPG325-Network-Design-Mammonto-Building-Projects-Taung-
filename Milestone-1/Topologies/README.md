Physical Topology

This folder contains the physical topology for the Mammonto Building Projects (Taung) network.

The physical topology includes the edge router, main switch, access switch, wireless access points, end-user devices and a shared server or service device where required.

The physical design provides the connection to the outside network, uses the main switch as the central connection point for the internal network, and includes an access switch for additional wired ports. Wireless access points are positioned so that staff devices can connect without requiring new cabling through external walls.

End-user devices are grouped according to their departments, and spare switch capacity is included to support additional users.

Logical Topology

This folder contains the logical topology for the Mammonto Building Projects (Taung) network.

The logical design separates different network functions into VLANs and IP subnets. The proposed VLAN structure consists of:

- VLAN 10 — ADMIN — Administration users and devices
- VLAN 20 — PROJECT — Project / technical staff
- VLAN 30 — FINANCE — Finance / support users
- VLAN 40 — STAFF-WIFI — Staff wireless clients
- VLAN 99 — MANAGEMENT — Management of network infrastructure

The VLAN structure provides logical separation between departments and network functions while using the same physical switching infrastructure. It also provides room for future growth and supports the staff wireless network as a separate logical segment.
