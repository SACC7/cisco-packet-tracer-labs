# OSPF Dynamic Routing Configuration in Cisco Packet Tracer

This repository contains a Cisco Packet Tracer lab demonstrating the configuration and verification of **OSPF (Open Shortest Path First)** dynamic routing protocol across multiple routers.

---

## 📌 Topology Overview

The network topology consists of 3 Cisco 2911 Routers and 2 End devices (PCs) arranged in a linear topology. All interfaces are configured under OSPF Area 0 (Backbone Area) to enable end-to-end communication.

* **Network Details:**
  * **PC0 Network:** `192.168.1.0/24`
  * **R1 - R2 Link:** `10.1.1.0/30`
  * **R2 - R3 Link:** `10.1.2.0/30`
  * **PC1 Network:** `192.168.2.0/24`

---

## 🛠️ Configuration Steps

### 1. Router R1 Configuration
* Configured interfaces `g0/2` (LAN) and `g0/1` (WAN).
* Enabled OSPF Process 1 and advertised connected networks using Wildcard Masks.

```router-ospf
Router(config)# interface g0/2
Router(config-if)# ip address 192.168.1.254 255.255.255.0
Router(config-if)# no shutdown

Router(config)# interface g0/1
Router(config-if)# ip address 10.1.1.1 255.255.255.252
Router(config-if)# no shutdown

Router(config)# router ospf 1
Router(config-router)# network 192.168.1.0 0.0.0.255 area 0
Router(config-router)# network 10.1.1.0 0.0.0.3 area 0
Router(config)# interface g0/0
Router(config-if)# ip address 10.1.2.1 255.255.255.252
Router(config-if)# no shutdown

Router(config)# router ospf 2
Router(config-router)# network 10.1.1.0 0.0.0.3 area 0
Router(config-router)# network 10.1.2.0 0.0.0.3 area 0
Router(config)# interface g0/2
Router(config-if)# ip address 192.168.2.254 255.255.255.0
Router(config-if)# no shutdown

Router(config)# interface g0/0
Router(config-if)# ip address 10.1.2.2 255.255.255.252
Router(config-if)# no shutdown

Router(config)# router ospf 3
Router(config-router)# network 192.168.2.0 0.0.0.255 area 0
Router(config-router)# network 10.1.2.0 0.0.0.3 area 0
