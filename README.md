# Project #1: Wireshark Network Traffic Investigation

## Overview
A hands-on network traffic analysis project using Wireshark on a Windows laptop. The investigation focused on DNS queries, DNS responses, packet timing, TCP flags, and preliminary security assessment.

## Objectives
- Inspect DNS traffic and query-response behavior.
- Use Wireshark display filters to isolate relevant packets.
- Examine TCP SYN and SYN-ACK flags.
- Record observations and distinguish suspicious indicators from confirmed threats.
- Document findings using an evidence-based approach.

## Tools
- Wireshark
- Windows 10
- DNS and TCP display filters

## Investigation Filters
```text
dns
dns.qry.name == "beacons.gcp.gvt2.com"
dns.qry.name == "beacons.gcp.gvt2.com" && dns.flags.response == 0
dns.qry.name == "beacons.gcp.gvt2.com" && dns.qry.type == 1 && dns.flags.response == 0
ip.addr == 10.235.176.7 && tcp
```

## Key Observations
- Approximately 2,348 packets were visible during the capture.
- The DNS display filter showed approximately 106 packets at the time of observation.
- Nine queries and nine responses were counted for the selected domain filter.
- Query timestamps were observed at approximately 9.525 seconds and 127.403 seconds into the capture.
- TCP packets involving the local host and remote IP 35.215.235.162 were examined.
- SYN and SYN-ACK flags were observed, but the complete TCP stream was not verified.

These figures are observations recorded during the exercise, not independently revalidated from a saved packet capture.

## Preliminary Assessment
**Verdict: Inconclusive — no confirmed malicious activity based on the evidence examined.**

The observations alone do not prove malware, command-and-control communication, or a successful attack. Further validation of the TCP stream, connection direction, DNS context, and endpoint telemetry would be required.

## Evidence
See the `screenshots/` directory for selected investigation screenshots.

## Limitations
- The original packet capture was not confirmed to have been saved.
- TCP stream pairing and connection direction require further verification.
- Domain and IP reputation were not independently validated as part of this exercise.

## Skills Practiced
- Wireshark display filters
- DNS query and response analysis
- TCP flag interpretation
- Packet timing analysis
- Evidence-based SOC triage
- Technical documentation

## Disclaimer
This project is for educational purposes and is based on traffic observed on my own device. It does not claim to identify or confirm a real cyberattack.