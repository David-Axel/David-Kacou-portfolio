# Man-in-the-Middle Attack — ARP Poisoning

## Overview
This lab demonstrates a Man-in-the-Middle (MITM) attack using ARP poisoning to
intercept network traffic between a target system and a router.

The objective was to observe how unencrypted communication can be captured and
why secure protocols are essential.

---

## Objectives
- Perform ARP poisoning in a local network
- Intercept traffic between a victim and gateway
- Analyze captured packets
- Compare HTTP vs HTTPS security implications

---

## Tools Used
- Ettercap
- Wireshark
- arp
- Linux networking utilities

---

## Methodology (High Level)

### 1. Network Discovery
The attacker identified the target system and the network gateway to prepare for
traffic interception.

---

### 2. ARP Poisoning
ARP spoofing was performed to associate the attacker’s MAC address with the
router’s IP address in the victim’s ARP table.

This redirected traffic through the attacker’s machine.

---

### 3. Traffic Capture & Analysis
Once positioned as MITM, traffic was captured using Wireshark.
Unencrypted HTTP traffic revealed sensitive information in plain text.

---

## Key Findings
- ARP poisoning enables silent interception of traffic
- HTTP traffic is exposed to attackers on the local network
- HTTPS prevents meaningful content inspection

---

## Defensive Perspective
- Enforce HTTPS across services
- Enable Dynamic ARP Inspection (DAI)
- Monitor ARP traffic for anomalies
- Deploy IDS/IPS where appropriate

---

## Notes
All experiments were performed in a controlled lab environment for educational
purposes only. Sensitive data is intentionally omitted.
