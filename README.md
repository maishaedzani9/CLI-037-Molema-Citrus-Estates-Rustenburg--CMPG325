# CMPG 325 — Molema Citrus Estates (Rustenburg)

**Client ID:** CLI-037  
**Project ID:** CMPG325-2026-037  
**Module:** CMPG 325 — Computer Networks  
**Organisation:** Molema Citrus Estates (Rustenburg)  
**Project status:** Phase 1 completed; Phase 2 implementation completed and final evidence packaging in progress.

## Project Overview

This repository contains the design, Cisco Packet Tracer implementation, configuration records, testing evidence, and technical documentation for the Molema Citrus Estates network project.

The work is organised into two project phases. Phase 1 contains the approved network design and planning material. Phase 2 contains the implemented Packet Tracer network, device configuration records, and implementation/testing evidence.

## Phase 1 — Network Design

Phase 1 covers the client requirements, topology design, VLAN and VLSM/IP addressing plan, and design justification used as the baseline for implementation.

## Phase 2 — Implementation and Testing

The implemented network includes:

- Layer 3 inter-VLAN routing on the core multilayer switch
- VLAN 10 — Management — gateway `192.168.26.113/29`
- VLAN 20 — Administration — gateway `192.168.26.33/27`
- VLAN 30 — Packhouse — gateway `192.168.26.1/27`
- VLAN 40 — Voice — gateway `192.168.26.65/27`
- VLAN 50 — Guest — gateway `192.168.26.97/28`
- 802.1Q trunking between the core and access switches
- IOS DHCP pools for Admin, Packhouse, Voice and Guest networks
- Router-to-core Layer 3 connectivity
- Extended ACL isolation for Guest VLAN 50 and Voice VLAN 40
- Connectivity, DHCP, trunk, SVI and ACL verification

## Assigned Networking Feature — ACLs

The assigned networking feature was implemented using extended access control lists on the Layer 3 core switch.

`GUEST_ISOLATION` restricts Guest VLAN 50 from reaching protected internal VLANs. `VOICE_ISOLATION` restricts Voice VLAN 40 from reaching protected internal network segments. DHCP traffic is explicitly permitted so end devices can obtain addresses before the isolation rules are applied. Verification was performed using connectivity tests and ACL match counters.

## Repository Navigation

```text
Phase1/                 Phase 1 design and planning deliverables
Phase2/
├── README.md           Phase 2 implementation overview
├── PacketTracer/       Final Cisco Packet Tracer implementation
├── Configs/            Device configuration records
└── Screenshots/        Implementation and testing evidence
```

The final Milestone 2 report and binary evidence files should be stored under `Phase2/` and its relevant subdirectories before submission.

## Testing Evidence

Phase 2 testing covers SVI status, trunk operation, DHCP address assignment, gateway connectivity, router-to-core connectivity, Guest VLAN isolation, Voice VLAN isolation, and ACL match-counter verification. Both successful connectivity and intentionally blocked traffic are retained as evidence of correct policy enforcement.

## Packet Tracer

The final Packet Tracer file is named `Molema_Citrus_Phase2.pkt` and belongs in `Phase2/PacketTracer/`.

## Documentation

The Milestone 2 report documents the implemented topology, VLAN/IP configuration, DHCP, routing and trunking, ACL implementation, testing results, and troubleshooting performed during implementation.

---

**CMPG 325 — Computer Networks**  
**Molema Citrus Estates (Rustenburg) — CLI-037**
