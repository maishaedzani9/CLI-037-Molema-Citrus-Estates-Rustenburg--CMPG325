# Client Requirements — Molema Citrus Estates (Rustenburg)

Project ID: CMPG325-2026-037 | Client ID: CLI-037 | Industry: Agriculture

Full analysis is in `Phase1_Design_Document.docx`, Sections 2–5. Summary below.

## Confirmed requirements (from the client brief)

- Assigned addressing block: 192.168.26.0/24, to be used with VLSM.
- Design constraint: VoIP traffic must be separated from data traffic.
- Assigned networking challenge: ACLs (traffic filtering policy), Intermediate difficulty.
- Change request CR14: after-hours cleaning/security contractors require limited wireless access.
- Use Cisco Packet Tracer for implementation and simulation.
- Document design decisions and evidence in GitHub.

## Reasonable design assumptions

- Estate operations split into Administration/Office and Packhouse/Operations functions, plus a
  small IT/management function.
- Approximate host counts (used only to size subnets): Administration ≈ 20, Packhouse/Operations ≈
  30, VoIP handsets ≈ 15, Guest/contractor Wi-Fi ≈ 10 concurrent, Management ≈ 5.
- Single physical site, single ISP connection.
- Guest/contractor wireless should be Internet-only, isolated from all internal VLANs.

## Missing information (requires confirmation)

- Exact department names, headcounts, and organisational structure.
- Physical building layout / number of structures / inter-building distances.
- Whether any redundancy or dynamic routing is expected beyond what the brief states.
- Exact ACL rule set beyond "traffic filtering policy" (to be finalised before Phase 2).

See the full design document for the functional/non-functional requirements tables, constraints,
and design-objective mapping.
