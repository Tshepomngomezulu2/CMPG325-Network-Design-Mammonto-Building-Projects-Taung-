# Cisco IOS Network Device Configurations

This directory contains the raw, production-ready Cisco IOS command-line interface (CLI) configuration scripts for all infrastructure devices in the Mammonto Building enterprise network architecture.

---

## 📁 Configuration Files Index

| File Name | Device Model | Network Layer | Primary Functions & Services Configured |
| :--- | :--- | :--- | :--- |
| **[`Router-ISR4331.cfg`](./Router-ISR4331.cfg)** | Cisco ISR4331 | Core / Gateway | Physical trunk activation, 802.1Q subinterfaces, Inter-VLAN default gateways, IPv4 DHCP excluded address ranges, dynamic DHCP service pools. |
| **[`Core-Switch-01.cfg`](./Core-Switch-01.cfg)** | Cisco Catalyst 2960 / 3560 | Distribution | Global VLAN database definitions, 802.1Q trunking to Router (`Gi0/1`) and Access Switch (`Gi0/2`), access port assignment for Management Server (`Fa0/3` on VLAN 99), Spanning-Tree PortFast. |
| **[`Switch-Access.cfg`](./Switch-Access.cfg)** | Cisco Catalyst 2960 | Access | Global VLAN database mirroring, 802.1Q uplink trunking (`Gi0/1`), edge access port assignments (`Fa0/1–3` for Project, `Fa0/4–5` for Finance, `Fa0/6` for Staff Wi-Fi AP), Spanning-Tree PortFast. |

---

## ⚙️ Summary of Executed Commands

### 1. Router Architecture (`Router-ISR4331.cfg`)
* **Subinterface Gateways:**
  * `Gi0/0/0.10` $\rightarrow$ `10.32.10.1/24` (VLAN 10: ADMIN)
  * `Gi0/0/0.20` $\rightarrow$ `10.32.20.1/24` (VLAN 20: PROJECT)
  * `Gi0/0/0.30` $\rightarrow$ `10.32.30.1/24` (VLAN 30: FINANCE)
  * `Gi0/0/0.40` $\rightarrow$ `10.32.40.1/24` (VLAN 40: STAFF-WIFI)
  * `Gi0/0/0.99` $\rightarrow$ `10.32.99.1/24` (VLAN 99: MANAGEMENT)
* **DHCP Pools:** `ADMIN_POOL`, `PROJECT_POOL`, `FINANCE_POOL`, and `STAFF_WIFI_POOL` configured with excluded address ranges `.1–.10` to reserve static IP blocks for infrastructure gateways and servers.

### 2. Core Distribution Switching (`Core-Switch-01.cfg`)
* **VLAN Database:** VLANs `10`, `20`, `30`, `40`, and `99` created and named.
* **Trunk Connections:**
  * `Gi0/1` $\rightarrow$ Encapsulation dot1q, mode trunk allowed VLANs `10,20,30,40,99` (connected to `Router-ISR4331 Gi0/0/0`).
  * `Gi0/2` $\rightarrow$ Encapsulation dot1q, mode trunk allowed VLANs `10,20,30,40,99` (connected to `Switch-Access Gi0/1`).
* **Management Port:** `Fa0/3` set to `switchport mode access`, assigned to `vlan 99`, with `spanning-tree portfast` enabled for `Management-Server-01`.

### 3. Access Switching (`Switch-Access.cfg`)
* **VLAN Database:** VLANs `10`, `20`, `30`, `40`, and `99` mirrored from core.
* **Uplink:** `Gi0/1` configured as an 802.1Q trunk back to `Core-Switch-01`.
* **Access Interfaces:**
  * `range Fa0/1 - 3` $\rightarrow$ Assigned to `vlan 20` (`PROJECT`) with `spanning-tree portfast`.
  * `range Fa0/4 - 5` $\rightarrow$ Assigned to `vlan 30` (`FINANCE`) with `spanning-tree portfast`.
  * `Fa0/6` $\rightarrow$ Assigned to `vlan 40` (`STAFF-WIFI`) for Access Point `AP01` with `spanning-tree portfast`.

---

## 🚀 Deployment Instructions

To deploy or restore these configurations onto physical hardware or Cisco Packet Tracer devices:

1. Connect to the target device via Console cable or Terminal Emulation.
2. Enter privileged EXEC mode (`enable`) followed by global configuration mode (`configure terminal`).
3. Copy the script content directly from the corresponding `.cfg` file and paste it into the CLI prompt.
4. Execute `write memory` or `copy running-config startup-config` to save parameters to NVRAM.
