# 🚀 Router-on-a-Stick (Inter-VLAN Routing) Lab

## 📌 Project Overview
Hi! I am a passionate, self-taught networking enthusiast building my core foundations in computer networks. This repository showcases a practical implementation of **Inter-VLAN Routing using the Router-on-a-Stick (RoaS)** methodology, simulated inside Cisco Packet Tracer.

Instead of just memorizing theory, I designed, configured, and troubleshooted this entire network topology from scratch to understand how different broadcast domains (VLANs) communicate securely through a single physical router interface using sub-interfaces.

---

## 🛠️ Network Topology & Architecture
* **Router:** Cisco 2911 (Configured with Sub-interfaces `Gi0/0.10` and `Gi0/0.20`)
* **Switch:** Cisco 2960-24TT (Configured with 802.1Q Trunking & Access Ports)
* **VLAN Segmentation:**
  * **VLAN 10:** Subnet `10.0.0.0/24` | Gateway: `10.0.0.100` (Simulating Dept A)
  * **VLAN 20:** Subnet `192.168.1.0/24` | Gateway: `192.168.1.200` (Simulating Dept B)

---

## 💡 Key Technical Skills Demonstrated
* **VLAN Logic:** Successfully isolated network traffic to optimize broadcast domains.
* **IEEE 802.1Q Trunking:** Configured switchports to tag and carry multi-VLAN traffic over a single uplink.
* **Sub-interface Configuration:** Created virtual interfaces on the router and mapped encapsulation types accurately.
* **Hands-on Cisco IOS CLI:** Comfortable using core commands (`encapsulation dot1Q`, `switchport mode trunk`, `no shutdown`, etc.).

---

## 🔍 Troubleshooting & Problem-Solving (My Learning Curve)
The best part of this lab was the troubleshooting. I faced initial hurdles with **port mismatches (e.g., configuring wrong sub-interface numbers)** and **IP configuration errors**. 
Instead of dropping the lab, I tracked the console errors, analyzed the (`^`) markers in CLI, reset the topology, and methodically re-configured the interfaces step-by-step until I achieved a **100% successful end-to-end ping**.

---

## 📊 Verification & Results
* **`ping 192.168.1.1`** from VLAN 10 successfully routes through the gateway and receives replies.
* *(Check out the uploaded `ping_results` screenshot in the repository to see the successful ICMP output!)*

---
*Connect with me as I share my journey of turning networking concepts into hands-on lab environments!*
