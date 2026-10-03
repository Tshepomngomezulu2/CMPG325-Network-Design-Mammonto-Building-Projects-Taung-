# Mammonto Building Enterprise Network Infrastructure

An enterprise-grade, multi-departmental network architecture designed, configured, and verified in **Cisco Packet Tracer**. This project implements Layer 2 VLAN segmentation, 802.1Q Inter-VLAN routing (Router-on-a-Stick), centralized Cisco IOS DHCP server pools, secure WPA2-PSK wireless access, and a dedicated management subnet.

---

## 📁 Repository Structure

```text
mammonto-network-infrastructure/
│
├── README.md                                  <-- Main documentation report
├── topology/
│   └── Mammonto_Building_Projects.pkt         <-- Cisco Packet Tracer source file
├── configs/
│   ├── Router-ISR4331.cfg                     <-- Raw Cisco ISR4331 router CLI script
│   ├── Core-Switch-01.cfg                     <-- Raw Core Switch CLI script
│   └── Switch-Access.cfg                      <-- Raw Access Switch CLI script
└── screenshots/
    ├── Access_Switch_VLANs_and_Trunks.png     <-- Layer 2 port mapping & trunking proof
    ├── Core_Switch_VLANs_and_Trunks.png       <-- Core uplink & management link proof
    ├── Router_Subinterfaces_and_DHCP_Bindings.png <-- Subinterface & IP lease proof
    ├── Client_PC_IPConfig_Verification.png    <-- Host dynamic IP lease proof
    ├── Ping_Default_Gateway.png               <-- Gateway reachability proof
    ├── Ping_InterVLAN_Cross_Subnet.png        <-- Inter-VLAN reachability proof
    └── Ping_Management_Server.png             <-- Management server reachability proof# Mammonto Building Enterprise Network Infrastructure

An enterprise-grade, multi-departmental network architecture designed, configured, and verified in **Cisco Packet Tracer**. This project implements Layer 2 VLAN segmentation, 802.1Q Inter-VLAN routing (Router-on-a-Stick), centralized Cisco IOS DHCP server pools, secure WPA2-PSK wireless access, and a dedicated management subnet.

---

## 📁 Repository Structure

```text
mammonto-network-infrastructure/
│
├── README.md                                  <-- Main documentation report
├── topology/
│   └── Mammonto_Building_Projects.pkt         <-- Cisco Packet Tracer source file
├── configs/
│   ├── Router-ISR4331.cfg                     <-- Raw Cisco ISR4331 router CLI script
│   ├── Core-Switch-01.cfg                     <-- Raw Core Switch CLI script
│   └── Switch-Access.cfg                      <-- Raw Access Switch CLI script
└── screenshots/
    ├── Access_Switch_VLANs_and_Trunks.png     <-- Layer 2 port mapping & trunking proof
    ├── Core_Switch_VLANs_and_Trunks.png       <-- Core uplink & management link proof
    ├── Router_Subinterfaces_and_DHCP_Bindings.png <-- Subinterface & IP lease proof
    ├── Client_PC_IPConfig_Verification.png    <-- Host dynamic IP lease proof
    ├── Ping_Default_Gateway.png               <-- Gateway reachability proof
    ├── Ping_InterVLAN_Cross_Subnet.png        <-- Inter-VLAN reachability proof
    └── Ping_Management_Server.png             <-- Management server reachability proof
