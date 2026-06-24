# 3-Router Dynamic Routing (RIPv2) Lab

This project demonstrates the implementation of **Dynamic Routing using Routing Information Protocol (RIP) Version 2** in a 3-Router Triangle Topology using Cisco Packet Tracer. 

Previously, this same topology was configured using Static Routing. In this lab, static routes were removed and replaced with dynamic routing to automate route discovery.

## 🗺️ Network Topology & IP Scheme

The network connects three major locations in Kerala (Kochi, TVM, and Calicut) in a triangle formation:

- **Router-Kochi (HQ):** LAN `192.168.10.0/24`
- **Router-TVM (Branch 1):** LAN `192.168.20.0/24`
- **Router-Calicut (Branch 2):** LAN `192.168.30.0/24`

### WAN High-speed Links:
- **Kochi to TVM:** `10.10.10.0/30`
- **TVM to Calicut:** `20.20.20.0/30`
- **Calicut to Kochi:** `30.30.30.0/30`

## 🚀 Routing Protocol Configured
- **Protocol:** RIPv2 (Routing Information Protocol Version 2)
- **Features Used:** `no auto-summary` (to support classless routing and prevent route aggregation).

## 🛠️ Verification Commands
To verify that the routers automatically exchanged routing tables via RIP, run the following command on any router:
```text
Router# show ip route
