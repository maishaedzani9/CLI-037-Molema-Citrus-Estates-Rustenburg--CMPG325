# Phase 2 — Testing Evidence

This directory contains screenshots captured during implementation, verification, testing, and troubleshooting of the Molema Citrus Estates network in Cisco Packet Tracer.

## Evidence checklist

The final evidence set should include screenshots demonstrating:

- Complete Packet Tracer topology
- VLAN SVI status verification (`show ip interface brief`)
- 802.1Q trunk verification (`show interfaces trunk`)
- Admin VLAN DHCP address assignment
- Packhouse VLAN DHCP address assignment
- Voice VLAN DHCP address assignment
- Guest VLAN DHCP address assignment
- Admin/default-gateway and router connectivity tests
- Guest VLAN 50 isolation tests against protected internal VLANs
- Voice VLAN 40 isolation tests against protected internal VLANs
- `GUEST_ISOLATION` ACL match counters
- `VOICE_ISOLATION` ACL match counters
- Relevant troubleshooting evidence retained from implementation

Both successful tests and intentionally failed pings are valid evidence where the expected result is traffic blocking by an ACL.

## Naming

Keep screenshot filenames descriptive and consistent with the Milestone 2 report. Existing evidence filenames may be retained when they already clearly identify the test performed.
