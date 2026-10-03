# Network Topology & Cisco Packet Tracer Model

This directory contains the primary simulation file for the Mammonto Building enterprise network architecture built in **Cisco Packet Tracer**.

---

## 📁 Topology Source File

* **File Name:** `Mammonto_Building_Projects.pkt`
* **Platform:** Cisco Packet Tracer (v8.0+ recommended)
* **Status:** Fully configured, saved, and operational (`write memory` executed on all nodes).

---

## 🏗️ Hardware Devices & Topology Layout

The physical and logical layout consists of the following core networking components:

1. **Router (`Router-ISR4331`):**
   * **Role:** Edge router performing 802.1Q Router-on-a-Stick (RoaS) Inter-VLAN routing and dynamic IPv4 address assignment.
   * **Interface:** `GigabitEthernet0/0/0` connected via 802.1Q trunking to `Core-Switch-01`.

2. **Core Switch (`Core-Switch-01`):**
   * **Role:** Central distribution layer switch facilitating uplink trunking to the router, downlink trunking to the access layer, and dedicated management attachment.
   * **Interfaces:**
     * `Gi0/1`: 802.1Q Trunk uplink to `Router-ISR4331` (`Gi0/0/0`).
     * `Gi0/2`: 802.1Q Trunk downlink to `Switch-Access` (`Gi0/1`).
     * `Fa0/3`: Access port assigned to `VLAN 99` (`MANAGEMENT`).

3. **Access Switch (`Switch-Access`):**
   * **Role:** Layer 2 access switch providing departmental port segmentation and fast endpoint convergence via Spanning-Tree PortFast.
   * **Interfaces:**
     * `Gi0/1`: 802.1Q Trunk uplink to `Core-Switch-01` (`Gi0/2`).
     * `Fa0/1 – Fa0/3`: Access ports assigned to `VLAN 20` (`PROJECT`).
     * `Fa0/4 – Fa0/5`: Access ports assigned to `VLAN 30` (`FINANCE`).
     * `Fa0/6`: Access port assigned to `VLAN 40` (`STAFF-WIFI`).

4. **Wireless Access Point (`AP01`):**
   * **Role:** Wireless access point connected to port `Fa0/6` on `Switch-Access`, extending `VLAN 40` (`STAFF-WIFI`) for mobile users.

5. **Management Server (`Management-Server-01`):**
   * **Role:** Statically addressed administrative server on `VLAN 99` attached directly to `Core-Switch-01` port `Fa0/3`.
   * **IP Address:** `10.32.99.10/24` (Gateway: `10.32.99.1`).

---

## 🏷️ VLAN & Subnet Mapping Summary

| VLAN ID | Name | Subnet CIDR | Default Gateway | Connected Physical Endpoints |
| :--- | :--- | :--- | :--- | :--- |
| **`10`** | `ADMIN` | `10.32.10.0/24` | `10.32.10.1` | Reserved for expansion |
| **`20`** | `PROJECT` | `10.32.20.0/24` | `10.32.20.1` | Project Workstations 01–03 (`Switch-Access Fa0/1–3`) |
| **`30`** | `FINANCE` | `10.32.30.0/24` | `10.32.30.1` | Finance Workstations 01–02 (`Switch-Access Fa0/4–5`) |
| **`40`** | `STAFF-WIFI`| `10.32.40.0/24` | `10.32.40.1` | Staff Wireless Access Point `AP01` (`Switch-Access Fa0/6`) |
| **`99`** | `MANAGEMENT`| `10.32.99.0/24` | `10.32.99.1` | Central Management Server (`Core-Switch Fa0/3`) |

---

## 🔍 How to Test & Verify in Packet Tracer

1. **Open File:** Launch `Mammonto_Building_Projects.pkt` in Cisco Packet Tracer.
2. **Verify IP Allocation:** Click on any end-user PC (e.g., Project PC 01), navigate to **Desktop** $\rightarrow$ **IP Configuration**, and toggle from Static to **DHCP** (if needed) to verify dynamic allocation from the router pool.
3. **Run ICMP Connectivity Tests:**
   * Open **Desktop** $\rightarrow$ **Command Prompt** on a client PC.
   * Test local gateway reachability: `ping 10.32.20.1`
   * Test Inter-VLAN reachability to another subnet: `ping 10.32.30.11`
   * Test reachability to the Management Server: `ping 10.32.99.10`
4. **Packet Tracer Simulation Mode:**
   * Switch from **Realtime** to **Simulation Mode** (bottom right corner).
   * Send a Simple PDU (envelope) between cross-VLAN PCs to visualize 802.1Q encapsulation tags moving through the Core Switch to the Router subinterfaces.
