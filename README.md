# CMPG 325 — Molema Citrus Estates (Rustenburg)

**Client ID:** CLI-037  
**Project ID:** CMPG325-2026-037  
**Module:** CMPG 325 — Computer Networks  
**Organisation:** Molema Citrus Estates (Rustenburg)  
**Project Status:** Phase 1 Design ✅ Complete | Phase 2 Implementation & Testing ✅ Complete

## Project Overview

This repository contains the complete design, Cisco Packet Tracer implementation, configuration records, testing evidence, and technical documentation for the Molema Citrus Estates network project.

The project is organised into two phases. **Phase 1** contains the network requirements, design, topology and addressing plan. **Phase 2** contains the implemented Packet Tracer network, configuration evidence, testing screenshots and final Milestone 2 report.

## Phase 1 — Network Design ✅

Phase 1 provides the approved baseline used for implementation, including client requirements, physical and logical topology design, VLAN/VLSM addressing and design justification.

## Phase 2 — Implementation & Testing ✅

The implemented network includes:

- Layer 3 inter-VLAN routing on the core multilayer switch
- VLAN 10 — Management — gateway `192.168.26.113/29`
- VLAN 20 — Administration — gateway `192.168.26.33/27`
- VLAN 30 — Packhouse — gateway `192.168.26.1/27`
- VLAN 40 — Voice — gateway `192.168.26.65/27`
- VLAN 50 — Guest — gateway `192.168.26.97/28`
- 802.1Q trunking between the core and access switches
- IOS DHCP pools for Administration, Packhouse, Voice and Guest networks
- Router-to-core Layer 3 connectivity
- Extended ACL isolation for Guest VLAN 50 and Voice VLAN 40
- Connectivity, DHCP, trunk, SVI and ACL verification

## Assigned Networking Feature — ACLs

The assigned networking feature was implemented using extended access control lists on the Layer 3 core switch.

`GUEST_ISOLATION` restricts Guest VLAN 50 from reaching protected internal VLANs. `VOICE_ISOLATION` restricts Voice VLAN 40 from reaching protected internal network segments. DHCP traffic is explicitly permitted so end devices can obtain addresses before isolation rules are applied. Verification evidence includes intentionally blocked connectivity tests and ACL match counters.

## Repository Navigation

```text
Phase1/                         Phase 1 design and planning deliverables
Phase2/
├── README.md                   Phase 2 implementation overview
├── CMPG325_Milestone2_Molema_Citrus_Estates_FINAL.pdf
│                               Final Milestone 2 implementation report
├── PacketTracer/
│   └── Molema_Citrus_Phase2.pkt
│                               Final working Cisco Packet Tracer file
├── Configs/
│   └── CoreSwitch_Config.txt   Verified core multilayer-switch configuration
└── Screenshots/                Implementation, verification and testing evidence
```

## Testing Evidence

The Phase 2 evidence set documents:

- Complete Packet Tracer topology
- VLAN SVI status verification
- 802.1Q trunk verification
- DHCP address assignment
- Gateway connectivity
- Router-to-core connectivity
- Administration-to-Packhouse connectivity
- Guest VLAN internal isolation
- Voice VLAN isolation
- ACL match-counter verification

Both successful connectivity and intentionally blocked traffic are retained as evidence that the implemented network and ACL security policies operate as designed.

## Packet Tracer Submission

The final Cisco Packet Tracer implementation is available at:

`Phase2/PacketTracer/Molema_Citrus_Phase2.pkt`

## Configuration Evidence

The verified core multilayer-switch configuration is available at:

`Phase2/Configs/CoreSwitch_Config.txt`

This configuration documents the principal Layer 3 implementation, including VLAN interfaces, routing-related configuration, DHCP services and ACL policy configuration used in the final network.

## Milestone 2 Report

The final implementation and testing report is available at:

`Phase2/CMPG325_Milestone2_Molema_Citrus_Estates_FINAL.pdf`

The report documents the implemented topology, VLAN/IP configuration, DHCP, routing and trunking, ACL implementation, testing results and troubleshooting performed during Phase 2.

---

**CMPG 325 — Computer Networks**  
**Molema Citrus Estates (Rustenburg) — CLI-037**