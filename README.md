# Simple Network Configuration – Cisco Packet Tracer

A basic Cisco Packet Tracer project demonstrating subnetting, IP address assignment, and connectivity testing across two departments in a small office network.

## 📌 Overview

This project simulates a small company network split into two departments — **Accounts** and **Delivery** — each with their own PCs and a network printer. The main goal was to practice subnetting a given IP block, assign addresses to devices, and verify connectivity between hosts using `ping`.

## 🖧 Topology

- **2 Switches** – one per department
- **1 Router** – connects the two department networks
- **2 PCs per department** (4 PCs total)
- **1 Printer per department** (2 printers total)

```
[PC1]---\
         [Switch - Accounts]---\
[PC2]---/                       \
[Printer]------------------------ [Router] 
                                 /
[PC1]---\                      /
         [Switch - Delivery]---
[PC2]---/
[Printer]
```

## 🌐 IP Addressing Scheme

Base network: **192.168.40.0/24**, subnetted into two /25 networks (one per department):

| Department | Network Address | Usable Host Range | Broadcast Address |
|---|---|---|---|
| Accounts | 192.168.40.0/25 | 192.168.40.1 – 192.168.40.126 | 192.168.40.127 |
| Delivery | 192.168.40.128/25 | 192.168.40.129 – 192.168.40.254 | 192.168.40.255 |

Each device (PCs and printers) was assigned a static IP within its department's usable range, with the subnet mask **255.255.255.128**.

## ⚙️ What Was Configured

1. Subnetted the given base network (192.168.40.0) into two equal subnets for the Accounts and Delivery departments.
2. Assigned static IP addresses, subnet masks, and default gateways to all PCs and printers.
3. Connected each department's devices to its own switch, and both switches to the router.
4. Configured router interfaces with the appropriate gateway IPs for each subnet.
5. Verified end-to-end connectivity using `ping` between devices in the same department and across departments.

## ✅ Testing

- Pinged between PCs within the same department to confirm local connectivity.
- Pinged across departments (Accounts ↔ Delivery) to confirm routing between subnets was working correctly.

## 📂 Files

- `simple_network_configuration_-_cisco_packet_tracer.pkt` – Packet Tracer project file (open with Cisco Packet Tracer)

## 🛠️ Tools Used

- Cisco Packet Tracer

## 🎓 Notes

This project was completed as part of coursework practicing subnetting and basic router/switch configuration fundamentals.
