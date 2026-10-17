# 🌐 Mammonto Building Network Topology (.pkt)

This directory contains the finalized, decorated, and fully verified Cisco Packet Tracer topology file for the **Mammonto Building (Taung)** network infrastructure (Milestone 3).

## 📂 File Deliverable
* **`Mammonto_Building_Projects.pkt`**: The primary Cisco Packet Tracer workspace file containing all routers, switches, servers, access points, and client workstations.

## 🎨 Visual & Architectural Enhancements
To ensure professional clarity and executive evaluation readiness, the workspace has been decorated with:
* **Departmental Subnet Color Blocks:** Soft pastel background shading separating each functional zone.
* **Metadata Title Blocks:** On-canvas header labels detailing the project name, author, class addressing schema, and routing architecture.
* **Port & Trunk Labels:** Explicit interface descriptions and 802.1Q trunking indicators along connection links.

## 📊 Summary of VLANs & Addressing
* **VLAN 10 (ADMIN):** `10.32.10.0/24` (Gateway: `10.32.10.1`)
* **VLAN 20 (PROJECT):** `10.32.20.0/24` (Gateway: `10.32.20.1`) — *Includes +8 expansion growth.*
* **VLAN 30 (FINANCE):** `10.32.30.0/24` (Gateway: `10.32.30.1`)
* **VLAN 40 (STAFF-WIFI):** `10.32.40.0/24` (Gateway: `10.32.40.1`) — *Serviced by Wireless Access Point AP01 (SSID: Staff-WiFi).*
* **VLAN 99 (MANAGEMENT):** `10.32.99.0/24` (Gateway: `10.32.99.1`) — *Dedicated to Management Server (`10.32.99.10`).*
