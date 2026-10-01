# CMPG 325 — Molema Citrus Estates (Rustenburg)

**Client ID:** CLI-037  
**Project ID:** CMPG325-2026-037  
**Module:** CMPG 325 — Computer Networks  
**Organisation:** Molema Citrus Estates (Rustenburg)  
**Project Status:** Phase 1 Design ✅ Complete | Phase 2 Implementation & Testing ✅ Complete

## Project Overview

This repository contains the network design, Cisco Packet Tracer implementation, verified device configuration records, testing evidence, and Milestone 2 technical report for the Molema Citrus Estates project.

## Phase 1 — Network Design ✅

The Phase 1 material is retained at the repository root and includes the client requirements, Phase 1 design document, IP addressing plan, physical topology material, logical topology/VLAN design, and design justification.

## Phase 2 — Implementation & Testing ✅

The implemented network includes:

- Layer 3 inter-VLAN routing on the core multilayer switch
- VLAN 10 — Management — gateway `192.168.26.113/29`
- VLAN 20 — Administration — gateway `192.168.26.33/27`
- VLAN 30 — Packhouse — gateway `192.168.26.1/27`
- VLAN 40 — Voice — gateway `192.168.26.65/27`
- VLAN 50 — Guest — gateway `192.168.26.97/28`
- 802.1Q trunking
- IOS DHCP pools for Administration, Packhouse, Voice and Guest networks
- Router-to-core Layer 3 connectivity
- Extended ACL isolation for Guest VLAN 50 and Voice VLAN 40
- Connectivity, DHCP, trunk, SVI and ACL verification

## Assigned Networking Feature — ACLs

The assigned networking feature was implemented using extended access control lists on the Layer 3 core switch.

`GUEST_ISOLATION` restricts Guest VLAN 50 from reaching protected internal VLANs. `VOICE_ISOLATION` restricts Voice VLAN 40 from reaching protected internal network segments. DHCP traffic is explicitly permitted so end devices can obtain addresses before isolation rules are applied. Verification evidence includes intentionally blocked connectivity tests and ACL match counters.

## Repository Navigation

```text
Repository root
├── Client_Requirements.md
├── Phase1_Design_Document.pdf
├── IP_Addressing_Plan.xlsx
├── Phase 1 topology/design files
└── Phase2/
    ├── README.md
    ├── CMPG325_Milestone2_Molema_Citrus_Estates_FINAL.pdf
    ├── PacketTracer/
    │   └── Molema_Citrus_Phase2.pkt
    ├── Configs/
    │   ├── CoreSwitch_Config.txt
    │   ├── Router0_Config.txt
    │   ├── AdminSwitch_Config.txt
    │   └── PackhouseSwitch_Config.txt
    └── Screenshots/
        └── Implementation and testing evidence
```

## Testing Evidence

The Phase 2 evidence set documents VLAN/SVI status, trunk operation, DHCP address assignment, gateway and router connectivity, Administration-to-Packhouse connectivity, Guest VLAN isolation, Voice VLAN isolation, and ACL match-counter verification.

Both successful connectivity and intentionally blocked traffic are retained because a failed ping is the expected result when an ACL correctly blocks prohibited traffic.

## Key Submission Files

- **Packet Tracer:** `Phase2/PacketTracer/Molema_Citrus_Phase2.pkt`
- **Final report:** `Phase2/CMPG325_Milestone2_Molema_Citrus_Estates_FINAL.pdf`
- **Device configurations:** `Phase2/Configs/`
- **Testing evidence:** `Phase2/Screenshots/`

## Scope Note

The implemented Packet Tracer topology verifies the internal network and the Router0 edge connection. No simulated ISP/Cloud path is included in the submitted topology, so public Internet reachability is not presented as a successful test. Internal routing, segmentation, DHCP and ACL behaviour are documented and verified separately.

---

**CMPG 325 — Computer Networks**  
**Molema Citrus Estates (Rustenburg) — CLI-037**