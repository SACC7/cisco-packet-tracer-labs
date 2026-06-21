
# Cisco Packet Tracer: VLAN & Trunking Configuration Lab

This repository contains a Cisco Packet Tracer lab focused on configuring Virtual Local Area Networks (VLANs) and Inter-Switch Trunking using Dot1Q encapsulation.

## Network Topology
- 2 Switches (Cisco 3560 Multilayer Switches)
- End Devices (PCs assigned to different VLANs)

## Objectives Covered
1. Verified initial connectivity between PCs.
2. Configured and assigned switch ports to **VLAN 2**.
3. Enabled **Dot1Q Trunking** between SW1 and SW2 to allow inter-switch VLAN communication.
4. Resolved the Layer 3 switch trunking error using:
   `switchport trunk encapsulation dot1q` followed by `switchport mode trunk`.
5. Successfully tested end-to-end connectivity via Ping.

## How to use this Lab
1. Download the `.pkt` file from this repository.
2. Open it in **Cisco Packet Tracer**.
3. Check the Running-Config of both switches to verify the configurations.
