IP Addressing Plan

This folder contains the IP addressing plan for the Mammonto Building Projects (Taung) network.

The client-assigned addressing block is 10.32.0.0/16. A /24 subnet is proposed for each main logical network in the initial design.

The proposed addressing structure is:

- VLAN 10 — 10.32.10.0/24 — Administration
- VLAN 20 — 10.32.20.0/24 — Project / Technical
- VLAN 30 — 10.32.30.0/24 — Finance / Support
- VLAN 40 — 10.32.40.0/24 — Staff Wireless
- VLAN 99 — 10.32.99.0/24 — Infrastructure Management

The default gateway for each VLAN is the first usable address in the subnet. End-user devices can receive addresses through DHCP during implementation, while selected infrastructure devices can use static addresses. The Project/Technical subnet provides sufficient capacity for the requested eight additional staff members without requiring a change to the subnet.
