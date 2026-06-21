# Static Routing Between Two Remote Networks 🌐

This lab demonstrates how to connect two different remote networks using two Cisco 2911 routers in Cisco Packet Tracer. 

## 🛠️ Configuration & Key Learnings
* **Interface Setup:** Configured LAN and WAN ports with proper IPv4 addressing.
* **Static Route:** Manually configured routing paths using the `ip route` command to ensure packet flow between `192.168.1.0/24` and `192.168.2.0/24`.
* **Troubleshooting:** Successfully diagnosed and resolved common entry-level issues like **Duplicate IP Addresses** (`%IP-4-DUPADDR`) and **Invalid Next Hop** errors in the Router CLI.

## 📐 Network IP Plan
* **Network A:** `192.168.1.0/24` (Gateway: `192.168.1.1`)
* **Network B:** `192.168.2.0/24` (Gateway: `192.168.2.1`)
* **WAN Link (Between Routers):** `10.0.0.0/8`
