# Final Technical Report — Figure and Evidence Checklist

**Project:** CMPG 325 — Molema Citrus Estates (Rustenburg), CLI-037  
**Purpose:** Use this checklist to complete `CMPG325_Final_Report_With_All_Selected_Evidence.docx` before uploading the final DOCX/PDF.

**Important:** The current draft contains `[INSERT SCREENSHOT: ...]` placeholders in the main report. Evidence files existing in GitHub does not mean the images are embedded in the Word report. Replace each placeholder with the matching image and remove the draft's revision note about missing figures only after all required figures are inserted and checked.

## Main report figures

| Figure | Required image file | Caption to use | Priority | Status |
|---|---|---|---|---|
| 1 | `MOLEMA CITRUS (RUSTENBURG) – PHASE 1 physical topology .drawio (1).png` (repository root) | **Figure 1: Phase 1 physical topology (design)** | Required | File present; embed in report |
| 2 | `Molema Citrus Estates (Rustenburg) — Logical Topology _ VLAN Design.jpg` (repository root) | **Figure 2: Phase 1 logical topology and VLAN design** | Required | File present; embed in report |
| 3 | A new screenshot of the complete final Packet Tracer topology | **Figure 3: Completed Molema Citrus Estates Packet Tracer topology** | Required | **MISSING from Screenshots folder**; capture from the saved final .pkt |
| 4 | `Phase2/Screenshots/01_Server0_Static_IP.png.png` | **Figure 4: Server0 static IP configuration** | Required | File present; embed in report |
| 5 | `Phase2/Screenshots/VLAN SVI Status Verification All VLAN Interfaces UpUp.png` | **Figure 5: SVI verification: all five VLAN interfaces up/up** | Required | File present; embed in report |
| 6 | `Phase2/Screenshots/Packhouse IP Phone Port Configuration – Data VLAN 30 and Voice VLAN 40.png` | **Figure 6: Packhouse IP phone port configuration: data VLAN 30 and voice VLAN 40** | Required | File present; embed in report |
| 7 | `Phase2/Screenshots/CoreSwitch Trunk VLAN Verification.png` | **Figure 7: CoreSwitch trunk VLAN verification (show interfaces trunk)** | Required | File present; embed in report |
| 8 | `Phase2/Screenshots/DHCP_PC0_VLAN20_SUCCESS.png.png` | **Figure 8: Administration VLAN 20 DHCP assignment on PC0** | Required | File present; embed in report |
| 9 | `Phase2/Screenshots/Packhouse VLAN 30 – Successful DHCP Address.png` | **Figure 9: Packhouse VLAN 30 successful DHCP address assignment** | Required | File present; embed in report |
| 10 | `Phase2/Screenshots/DHCP Verification for Voice VLAN 40 – IP Phones Successfully Assigned.png` | **Figure 10: Voice VLAN 40 DHCP assignment to IP phones** | Required | File present; embed in report |
| 11 | `Phase2/Screenshots/Voice VLAN DHCP Verification with VOICE_ISOLATION ACL Active.png` | **Figure 11: Voice VLAN 40 DHCP verification with VOICE_ISOLATION ACL active** | Required | File present; embed in report |
| 12 | `Phase2/Screenshots/Guest VLAN 50 – Successful DHCP Address Assignment.png` | **Figure 12: Guest VLAN 50 successful DHCP address assignment** | Required | File present; embed in report |
| 13 | `Phase2/Screenshots/Admin VLAN 20 – Router0 Connectivity PASS.png` | **Figure 13: Administration VLAN 20 to Router0 connectivity test: PASS** | Required | File present; embed in report |
| 14 | `Phase2/Screenshots/ACL Match Counter Verification – Guest and Voice Isolation.png` | **Figure 14: ACL match-counter verification for Guest and Voice isolation (show access-lists)** | Required — assigned feature | File present; embed in report and confirm readable counters |
| 15 | `Phase2/Screenshots/Test1_Admin_Gateway_PASS.png.png` | **Figure 15: Administration client to Administration gateway: PASS** | Required | File present; embed in report |
| 16 | `Phase2/Screenshots/Test2_Admin_to_Packhouse_PASS.png.png` | **Figure 16: Administration to Packhouse permitted inter-VLAN test: PASS** | Required | File present; embed in report |
| 17 | `Phase2/Screenshots/Voice VLAN 40 Gateway Connectivity Test – Successful.png` | **Figure 17: Voice VLAN 40 gateway connectivity test: successful** | Required | File present; embed in report |
| 18 | `Phase2/Screenshots/Voice VLAN 40 ACL Isolation Verification – Admin and Packhouse Networks Blocked.png` | **Figure 18: Voice VLAN 40 isolation: Administration and Packhouse networks blocked as intended** | Required — assigned feature | File present; embed in report |
| 19 | `Phase2/Screenshots/Voice VLAN 40 Isolation Test – Guest VLAN 50 Blocked.png` | **Figure 19: Voice VLAN 40 isolation test: Guest VLAN 50 blocked** | Required — assigned feature | File present; embed in report |
| 20 | `Phase2/Screenshots/Voice VLAN 40 Isolation Test – Management VLAN 10 Blocked.png` | **Figure 20: Voice VLAN 40 isolation test: Management VLAN 10 blocked** | Required — assigned feature | File present; embed in report |
| 21 | `Phase2/Screenshots/Guest VLAN 50 Isolation – Internal VLAN Access Blocked.png` | **Figure 21: Guest VLAN 50 internal VLAN isolation test: access blocked as intended** | Required — assigned feature | File present; embed in report |

## Supplementary screenshots

These can remain in the evidence folder and may be referenced in the appendices if they add value. Do not replace a required main figure with a supplementary image unless the screenshot clearly proves the same test.

- `Guest VLAN 50 → Admin VLAN – Access Denied.png`
- `Guest VLAN 50 → Packhouse VLAN 30 – Access Blocked.png`
- `Guest VLAN 50 → Voice VLAN 40 – Access Blocked.png`
- `Guest VLAN 50 → Management VLAN 10 – Access Blocked.png`
- `Router_to_PC0_VLAN20_SUCCESS.png.png`
- `Test3_Admin_to_Router_PASS.png.png`
- `Voice VLAN 40 DHCP Address Assignment Verification.png`

## Management versus Guest caption checks

- Management VLAN 10 is `192.168.26.112/29`, gateway `192.168.26.113`; the management endpoint is `192.168.26.114/29`.
- Guest VLAN 50 is `192.168.26.96/28`, gateway `192.168.26.97`; `192.168.26.100/28` or `192.168.26.101/28` with gateway `192.168.26.97` is Guest evidence.
- If a screenshot shows `192.168.26.100/28` and gateway `192.168.26.97`, caption it as **Guest VLAN 50**, even if the ping destination is a Management address.
- Do not claim that a failed ping means the endpoint itself is Management; distinguish the source endpoint from the destination being tested.

## Wildcard-mask checks

Before exporting the final report, open the actual `Molema_Citrus_Phase2.pkt` in Packet Tracer and run:

```text
enable
show access-lists GUEST_ISOLATION
show access-lists VOICE_ISOLATION
```

Confirm that both Management destination rules use `192.168.26.112 0.0.0.7`. Save the Packet Tracer file after confirming the configuration. The text record alone does not prove the binary project has the same current configuration.

## Final report release checklist

- [ ] All 21 main-report figures are embedded; no `[INSERT SCREENSHOT: ...]` placeholders remain.
- [ ] Figure numbers are sequential and captions match the correct images.
- [ ] ACL counter screenshot is legible and displays actual counters.
- [ ] Guest/Management labels are checked against visible IP address and gateway.
- [ ] Both ACL Management wildcards have been verified inside the saved `.pkt`.
- [ ] Draft revision notes and unresolved placeholder warnings are removed only after their issues are actually fixed.
- [ ] Export final PDF and save the editable DOCX.
- [ ] Upload final report to `Phase2/` and update the root README.
