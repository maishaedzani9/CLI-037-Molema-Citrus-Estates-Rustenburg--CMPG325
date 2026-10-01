# Phase 2 — Implementation & Testing

This folder contains the completed Milestone 2 implementation and evidence for the Molema Citrus Estates network project.

## Implementation Scope

- Cisco Packet Tracer network implementation
- VLANs and Layer 3 SVIs
- 802.1Q trunking
- DHCP services for Administration, Packhouse, Voice and Guest networks
- Inter-VLAN routing
- Router-to-core Layer 3 connectivity
- Assigned feature: extended ACL traffic isolation for Guest VLAN 50 and Voice VLAN 40
- Connectivity, isolation and troubleshooting verification

## Contents

- `CMPG325_Milestone2_Molema_Citrus_Estates_FINAL.pdf` — final Milestone 2 implementation and testing report
- `PacketTracer/Molema_Citrus_Phase2.pkt` — final working Packet Tracer implementation
- `Configs/` — verified configuration records for CoreSwitch, Router0, AdminSwitch and PackhouseSwitch
- `Screenshots/` — implementation and testing evidence

## Evidence Summary

The evidence set includes DHCP verification, VLAN/SVI verification, trunk verification, router connectivity, Guest VLAN isolation, Voice VLAN isolation and ACL match-counter verification. Intentionally failed pings are retained where blocking is the expected ACL result.

## Scope Note

The submitted Packet Tracer topology does not include a simulated ISP/Cloud path. Public Internet reachability is therefore not claimed as a successful test; the documented evidence focuses on the implemented internal network, edge-router connectivity, segmentation and ACL behaviour.
