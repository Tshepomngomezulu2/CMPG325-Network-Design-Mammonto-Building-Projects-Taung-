# 📄 Mammonto Building Technical Reports & Documentation

This directory contains the official documentation, formal technical reports, and production-ready CLI configuration scripts for Milestone 3.

## 📂 Document Deliverables
* **`Mammonto_Building_Projects_Technical_Report.docx`**: The comprehensive academic report detailing the executive summary, architecture, Layer 2/3 configuration, security hardening, and test logs.
* **`Mammonto_Building_Projects_Additional_Files.docx`**: The supplementary portfolio containing all production Cisco IOS CLI configuration scripts (`.cfg`) and the screenshot asset index.

## ⚙️ Included Production CLI Scripts (`.cfg`)
1. **`Router-ISR4331.cfg`**: Configures physical interface `Gi0/0/0`, 802.1Q subinterfaces (`.10` through `.99`), and native DHCP pools with excluded address ranges.
2. **`Core-Switch-01.cfg`**: Configures VLAN creation, 802.1Q trunk links to the router and access switch, and dedicated Management Server access port mapping (`Fa0/3` on VLAN 99).
3. **`Switch-Access.cfg`**: Configures access ports for Project workstations (`Fa0/1–3`), Finance workstations (`Fa0/4–5`), and the Staff Wi-Fi Access Point (`Fa0/6`), alongside Spanning-Tree PortFast optimization.
