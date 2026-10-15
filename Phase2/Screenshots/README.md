# Phase 2 — Testing Evidence

This directory contains screenshots captured during implementation and verification of the Molema Citrus Estates network in Cisco Packet Tracer.

## Evidence index

| Test area | Evidence to look for |
|---|---|
| VLAN/SVI status | Core switch SVI status verification |
| Trunking | Core switch trunk VLAN verification |
| DHCP | Address assignment for Administration, Packhouse, Voice and Guest clients |
| Connectivity | Gateway, Router0 and Administration-to-Packhouse tests |
| Guest isolation | VLAN 50 access-block tests against protected internal VLANs |
| Voice isolation | VLAN 40 access-block tests against protected internal VLANs |
| ACL verification | Guest and Voice ACL match-counter screenshot |
| Voice ports | Access/data VLAN and voice VLAN port configuration |

## Interpreting results

A successful ping is expected for permitted paths. A failed ping is expected when an ACL correctly blocks prohibited traffic. Review each screenshot against the intended policy and the corresponding test described in the Milestone 2 report.

## File naming

Existing filenames are retained to preserve links and match the submitted evidence. For future additions, use short descriptive names that identify the VLAN, test and expected result. Avoid double extensions such as `.png.png` when naming new files.
