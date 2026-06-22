# 🌐 3-Router Triangular Network Lab (Static Routing)

This repository contains the configuration and topology details for a 3-Router Triangular Network lab built in **Cisco Packet Tracer**. The main goal of this lab is to achieve full connectivity across three distinct local networks using **Static Routing** and optimal IP assignment using `/30` subnets.

---

## 📐 Network Topology

The network is designed in a triangular shape, where each router is connected to two other routers using **Copper Cross-Over** cables. Each router also hosts a local area network (LAN) connected via a switch.

### 🏠 IP Addressing Scheme

#### Local Area Networks (LAN)
* **LAN 0 (Top Router):** `192.168.10.0/24` (Gateway: `192.168.10.1`)
* **LAN 1 (Left Router):** `192.168.20.0/24` (Gateway: `192.168.20.1`)
* **LAN 2 (Right Router):** `192.168.30.0/24` (Gateway: `192.168.30.1`)

#### Wide Area Networks (WAN / Router-to-Router)
* **Router0 ↔ Router1:** `10.0.0.0/30`
* **Router1 ↔ Router2:** `10.0.0.4/30`
* **Router2 ↔ Router0:** `10.0.0.8/30`

---

## 🛠️ Configuration Guide

### 1. Router0 (Top Router)
```text
Router> enable
Router# configure terminal

! LAN Interface
interface GigabitEthernet0/1
 ip address 192.168.10.1 255.255.255.0
 no shutdown
 exit

! WAN to Router1
interface GigabitEthernet0/0
 ip address 10.0.0.1 255.255.255.252
 no shutdown
 exit

! WAN to Router2
interface GigabitEthernet0/2
 ip address 10.0.0.9 255.255.255.252
 no shutdown
 exit

! Static Routing
ip route 192.168.20.0 255.255.255.0 10.0.0.2
ip route 192.168.30.0 255.255.255.0 10.0.0.10
ip route 10.0.0.4 255.255.255.252 10.0.0.2
end
write memory
