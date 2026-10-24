# PortMaster — Network Subsystem Specification (Member 1)

## 1. Network Overview
This network represents the operational communication infrastructure for the PortMaster Intelligent Maritime Logistics platform. It provides secure, segmented connectivity between field operations (Terminals, Yard, Warehouses), the Port Control Tower, and central backend servers.

## 2. VLAN & Subnet Allocation Plan
- **VLAN 10 (Terminal Operations):** `192.168.10.0/24` — Gateway: `192.168.10.1`
- **VLAN 20 (Yard Operations):** `192.168.20.0/24` — Gateway: `192.168.20.1`
- **VLAN 30 (Warehouse Operations):** `192.168.30.0/24` — Gateway: `192.168.30.1`
- **VLAN 40 (Control Room):** `192.168.40.0/24` — Gateway: `192.168.40.1`
- **VLAN 50 (Server Farm / App Host):** `192.168.50.0/24` — Gateway: `192.168.50.1`
- **VLAN 99 (Management / Native):** `192.168.99.0/24` — Gateway: `192.168.99.1`

## 3. Hardware Architecture
- **Core Router:** Cisco 2911 (Inter-VLAN Routing via 802.1Q sub-interfaces, DHCP Server)
- **Core Switch:** Cisco Catalyst 2960-24TT (Central trunk aggregator)
- **Access Switches:** 5x Cisco Catalyst 2960-24TT (Edge access layer for operational zones)
- **End-points:** Field PCs, Crane/Weighbridge terminals, Server host