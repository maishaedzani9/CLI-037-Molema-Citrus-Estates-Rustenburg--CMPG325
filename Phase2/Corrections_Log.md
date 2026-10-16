# Corrections Log — CMPG 325 Final Submission

**Project:** Molema Citrus Estates (Rustenburg)  
**Client ID:** CLI-037  
**Updated:** 16 October 2026

## 1. Management subnet wildcard mask

The Management VLAN is VLAN 10, network `192.168.26.112/29`, subnet mask `255.255.255.248`, gateway `192.168.26.113`, with the known management endpoint `192.168.26.114/29`.

The correct wildcard mask for the Management destination subnet is `0.0.0.7`. The earlier `0.0.0.15` wildcard is broader than the /29 and can match addresses outside the Management subnet, including addresses in the point-to-point router link range.

The repository's text record `Phase2/Configs/CoreSwitch_Config.txt` currently records the Management destination as `192.168.26.112 0.0.0.7` in both `GUEST_ISOLATION` and `VOICE_ISOLATION`.

**Verification limitation:** The Packet Tracer `.pkt` is a binary file and has not been opened/inspected as part of this log update. Therefore, this log does not claim that the saved `.pkt` has been verified to contain the corrected wildcard. Before final submission, open the `.pkt`, run `show access-lists GUEST_ISOLATION` and `show access-lists VOICE_ISOLATION`, confirm both Management destination rules use `0.0.0.7`, save the file, and capture fresh evidence if the output differs.

## 2. Management versus Guest endpoint labels

Use the following addressing references when checking report text, captions and screenshots:

- **Management VLAN 10:** `192.168.26.112/29`; gateway `192.168.26.113`; known endpoint `192.168.26.114/29`.
- **Guest VLAN 50:** `192.168.26.96/28`; gateway `192.168.26.97`; example endpoint `192.168.26.100/28` or DHCP client `192.168.26.101/28`.

Any screenshot showing `192.168.26.100/28` with gateway `192.168.26.97` must be labelled **Guest VLAN 50**, not Management. Do not relabel it as Management merely because the ping target is a Management address.

## 3. Evidence and report handling

- Retain the existing screenshots under `Phase2/Screenshots/`.
- In the final report, every figure caption must agree with the visible endpoint IP, subnet mask, default gateway and tested destination.
- ACL counter evidence must show the actual `show access-lists` output and relevant match counters.
- Do not describe Internet reachability as successful: the submitted topology does not include a simulated ISP/Cloud path.
- The existing `Phase2/CMPG325_Milestone2_Molema_Citrus_Estates_FINAL.pdf` is present. The separate 31-page `CMPG325_Final_Report_With_All_Selected_Evidence.docx` draft is not currently in the GitHub repository and must be finalised and uploaded if it is the required final technical report.

## 4. Final verification checklist

- [ ] Open the saved `.pkt` and verify the Management wildcard in both ACLs.
- [ ] Save the verified `.pkt` and upload the latest version.
- [ ] Check every report figure and caption against the actual screenshot.
- [ ] Embed the actual images for every required figure; remove all `[INSERT SCREENSHOT: ...]` placeholders.
- [ ] Check that ACL counter screenshots are present and readable.
- [ ] Upload the final technical report (PDF and/or DOCX as required).
- [ ] Add the recorded 15–20 minute inset video or a working share link.
