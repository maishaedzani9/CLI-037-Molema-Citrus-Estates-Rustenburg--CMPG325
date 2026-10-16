# Phase 2 — Implementation & Testing

This directory contains the Milestone 2 Cisco Packet Tracer implementation, configuration records, final report and evidence for the Molema Citrus Estates network project.

## Implementation scope

- VLANs and Layer 3 switched virtual interfaces (SVIs)
- 802.1Q trunking
- DHCP for Administration, Packhouse, Voice and Guest VLANs
- Inter-VLAN routing on the multilayer core switch
- Layer 3 connectivity between the core switch and Router0
- Extended ACL isolation for Guest VLAN 50 and Voice VLAN 40
- Connectivity, DHCP, trunk, SVI and ACL verification

## Deliverables

| Item | File or folder |
|---|---|
| Final Milestone 2 report | [CMPG325_Milestone2_Molema_Citrus_Estates_FINAL.pdf](CMPG325_Milestone2_Molema_Citrus_Estates_FINAL.pdf) |
| Working Packet Tracer project | [PacketTracer/Molema_Citrus_Phase2.pkt](PacketTracer/Molema_Citrus_Phase2.pkt) |
| Core switch, router and access-switch records | [Configs/](Configs/) |
| Implementation and testing screenshots | [Screenshots/](Screenshots/) |

## VLAN gateway summary

| VLAN | Purpose | Network | Gateway |
|---:|---|---|---|
| 10 | Management | 192.168.26.112/29 | 192.168.26.113 |
| 20 | Administration | 192.168.26.32/27 | 192.168.26.33 |
| 30 | Packhouse | 192.168.26.0/27 | 192.168.26.1 |
| 40 | Voice | 192.168.26.64/27 | 192.168.26.65 |
| 50 | Guest | 192.168.26.96/28 | 192.168.26.97 |

## Test evidence

The screenshots document:

- VLAN/SVI and 802.1Q trunk status
- DHCP address assignment for the documented client VLANs
- Gateway and router connectivity
- Administration-to-Packhouse connectivity
- Guest VLAN 50 isolation from protected internal networks
- Voice VLAN 40 isolation from protected internal networks
- ACL match-counter verification

Both successful and intentionally blocked traffic tests are retained. A failed ping is a passing outcome when the corresponding ACL is intended to deny that traffic.

## Reproduce the tests

1. Open the `.pkt` file in Cisco Packet Tracer.
2. Check the device configurations against the records in `Configs/`.
3. Verify VLAN/SVI status and trunk operation.
4. Renew or inspect DHCP leases on clients in the configured VLANs.
5. Run the allowed connectivity tests and the Guest/Voice isolation tests.
6. Compare the observed results with the screenshots and final report.

## Scope and limitations

The submitted topology does not include a simulated ISP/Cloud path. Public Internet reachability is therefore not claimed as a successful test. The documented verification focuses on the implemented internal network, core-to-router connectivity, segmentation, DHCP and ACL behaviour.

The Packet Tracer project, configuration records, screenshots and report should be reviewed together. If a configuration record differs from the active running configuration, verify the live project and update the record from the verified output before treating it as final.


## Final evaluation additions

- [Corrections log](Corrections_Log.md) records the Management wildcard-mask issue and endpoint-label checks.
- [Video demonstration instructions](Video_Demonstration/README.md) is the location for the recorded 15–20 minute inset demonstration link.

**Outstanding before final submission:** the video file/link is not yet present; the separate final-report draft must be checked for screenshot placeholders and uploaded if required; and the ACL wildcard must be verified inside the saved Packet Tracer project itself.
