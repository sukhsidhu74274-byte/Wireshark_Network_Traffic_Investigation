# Network Traffic Investigation Report

**Project:** Project #1 — Wireshark Network Traffic Investigation  
**Analyst Role:** Junior SOC Analyst  
**Platform:** Windows 10  
**Tool:** Wireshark

## 1. Investigation Summary
Inspected DNS and TCP traffic to practice network-level security triage. The investigation included filtering a selected DNS domain, counting observed queries and responses, reviewing packet timing, and inspecting TCP flags.

## 2. Evidence Reviewed
- Selected DNS domain: `beacons.gcp.gvt2.com`
- Observed local IP: `10.235.176.7`
- Observed DNS resolver: `10.235.176.130`
- Additional remote IP examined: `35.215.235.162`
- Selected-domain query and response counts: 9 each, as recorded during analysis

## 3. Analysis
The selected DNS traffic appeared at multiple points in the capture. The observed intervals were not consistently periodic. TCP packets displayed SYN and SYN-ACK flags, but the exact stream pairing and connection direction were not fully verified.

Neither a domain name nor an isolated TCP flag is sufficient to determine malicious intent.

## 4. Assessment
**Final preliminary verdict: Inconclusive.**

No malicious activity was confirmed by the evidence examined. This does not establish that all observed traffic was benign; additional evidence would be required for a stronger conclusion.

## 5. Recommended Follow-up
1. Capture a fresh, authorized sample of network traffic.
2. Save it locally in PCAPNG format.
3. Follow the relevant TCP stream and verify source/destination ports.
4. Correlate network findings with endpoint logs.
5. Document the evidence and update the verdict only when supported.

## 6. Learning Outcome
Practiced packet filtering, DNS analysis, TCP flag inspection, and cautious evidence-based reporting.
