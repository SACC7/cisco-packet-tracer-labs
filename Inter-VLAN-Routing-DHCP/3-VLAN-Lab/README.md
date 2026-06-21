# Inter-VLAN Routing with Dynamic DHCP Configuration

This project demonstrates the implementation of **Inter-VLAN Routing (Router-on-a-Stick)** and dynamic IP addressing using **Cisco IOS DHCP Server** on a Cisco Router. The lab was designed and tested using Cisco Packet Tracer.

## 🛠️ Network Architecture & Design

The network is segmented into three distinct VLANs to ensure security and reduce broadcast domains:

* **VLAN 10 (Department A):** Subnet `10.0.0.0/24` | Gateway: `10.0.0.100`
* **VLAN 20 (Department B):** Subnet `192.168.1.0/24` | Gateway: `192.168.1.200`
* **VLAN 30 (Department C):** Subnet `172.16.1.0/24` | Gateway: `172.16.1.30`

## 🚀 Key Features Implemented

1.  **VLAN Segmentation:** Created and mapped specific ports on the Layer 2 Cisco Switch to VLANs 10, 20, and 30.
2.  **Router-on-a-Stick (ROAS):** Configured a single physical interface (`GigabitEthernet0/0`) on the router into multiple virtual sub-interfaces (`g0/0.10`, `g0/0.20`, `g0/0.30`) using **802.1Q encapsulation**.
3.  **Cisco IOS DHCP Server:** Configured independent DHCP pools for each VLAN to dynamically lease IP addresses, Subnet Masks, and Default Gateways to end devices.
4.  **IP Exclusion:** Excluded critical gateway IP addresses from the DHCP pools to prevent address conflicts.

## 💻 Key Commands Used

### Router Configuration (Sub-Interfaces & DHCP Pools)
```cisco
! Sub-interface for VLAN 30 Example
interface GigabitEthernet0/0.30
 encapsulation dot1Q 30
 ip address 172.16.1.30 255.255.255.0

! DHCP Pool Setup
ip dhcp excluded-address 172.16.1.30
ip dhcp pool VLAN30_Pool
 network 172.16.1.0 255.255.255.0
 default-router 172.16.1.30
