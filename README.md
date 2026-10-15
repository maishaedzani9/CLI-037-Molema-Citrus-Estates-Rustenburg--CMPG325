# CMPG 325 — Molema Citrus Estates (Rustenburg)

> **Computer Networks | CLI-037 | Project CMPG325-2026-037**

This repository documents the design and Cisco Packet Tracer implementation of a segmented network for Molema Citrus Estates in Rustenburg. It includes the Phase 1 design material and the Phase 2 implementation, device configuration records, testing evidence and final technical report.

## Project status

- **Phase 1 — Network design:** design material included
- **Phase 2 — Implementation and testing:** implementation and evidence included
- **Internet reachability:** not claimed; the submitted Packet Tracer topology does not include a simulated ISP/Cloud path

## Network overview

The implementation uses a multilayer core switch for inter-VLAN routing, 802.1Q trunks, DHCP pools for end-user VLANs, and extended ACLs to isolate Guest and Voice traffic from protected internal networks.

### Logical VLAN and addressing plan

| VLAN | Name | Network / Prefix | Subnet mask | Default gateway |
|---:|---|---|---|---|
| 10 | Management | 192.168.26.112/29 | 255.255.255.248 | 192.168.26.113 |
| 20 | Administration | 192.168.26.32/27 | 255.255.255.224 | 192.168.26.33 |
| 30 | Packhouse | 192.168.26.0/27 | 255.255.255.224 | 192.168.26.1 |
| 40 | Voice | 192.168.26.64/27 | 255.255.255.224 | 192.168.26.65 |
| 50 | Guest | 192.168.26.96/28 | 255.255.255.240 | 192.168.26.97 |

The core-to-router point-to-point link uses 192.168.26.120/30, with 192.168.26.122 on the core switch and 192.168.26.121 on Router0.

## Key features

- Layer 3 inter-VLAN routing on the core multilayer switch
- VLAN segmentation for Management, Administration, Packhouse, Voice and Guest
- 802.1Q trunk links between network devices
- DHCP for Administration, Packhouse, Voice and Guest VLANs
- Extended ACLs named `GUEST_ISOLATION` and `VOICE_ISOLATION`
- Verification of VLAN/SVI status, trunking, DHCP assignment, connectivity, ACL blocking and ACL match counters

## Network design material

- [Client requirements](Client_Requirements.md)
- [Phase 1 design document](Phase1_Design_Document.pdf)
- [IP addressing plan](IP_Addressing_Plan.xlsx)
- [Logical VLAN design image](Molema%20Citrus%20Estates%20(Rustenburg)%20%E2%80%94%20Logical%20Topology%20_%20VLAN%20Design.jpg)
- [Physical topology image](MOLEMA%20CITRUS%20(RUSTENBURG)%20%E2%80%93%20PHASE%201%20physical%20topology%20.drawio%20(1).png)

## Phase 2 deliverables

| Deliverable | Location |
|---|---|
| Phase 2 overview and instructions | [Phase2/README.md](Phase2/README.md) |
| Final implementation report | [Milestone 2 PDF report](Phase2/CMPG325_Milestone2_Molema_Citrus_Estates_FINAL.pdf) |
| Cisco Packet Tracer project | [Molema_Citrus_Phase2.pkt](Phase2/PacketTracer/Molema_Citrus_Phase2.pkt) |
| Device configuration records | [Phase2/Configs](Phase2/Configs/) |
| Testing screenshots | [Phase2/Screenshots](Phase2/Screenshots/) |

## Reproducing the implementation and tests

1. Install and open Cisco Packet Tracer.
2. Open `Phase2/PacketTracer/Molema_Citrus_Phase2.pkt`.
3. Inspect the core switch and router configurations alongside the text records in `Phase2/Configs/`.
4. Verify VLAN/SVI status, trunk operation and DHCP address assignment.
5. Run the permitted connectivity tests and the Guest/Voice isolation tests described in the report.
6. Compare the results with the evidence in `Phase2/Screenshots/`, including ACL match-counter verification.

A failed ping is an expected result when the ACL is correctly blocking prohibited traffic. Evaluate those tests against their expected outcomes rather than treating every failed ping as a network fault.

## Security and scope notes

The submitted topology demonstrates the internal network and its connection to Router0. It does not simulate an ISP/Cloud path, so public Internet connectivity has not been established by the submitted evidence. The text configuration records should be read alongside the Packet Tracer project and report; the live project is the reference for checking the final active configuration.

## Technologies and concepts

**Cisco Packet Tracer · Cisco IOS configuration · IPv4 subnetting · VLANs · 802.1Q trunking · Layer 3 switching · DHCP · Static routing · Extended ACLs · Network verification**

---

**Module:** CMPG 325 — Computer Networks  
**Client:** Molema Citrus Estates (Rustenburg)  
**Client ID:** CLI-037
