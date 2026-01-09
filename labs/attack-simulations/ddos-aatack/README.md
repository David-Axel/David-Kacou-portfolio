# DDoS Attack Simulation

## Overview
This lab explores denial-of-service (DoS/DDoS) attack techniques and their impact on
system availability. Two attack types were simulated against a vulnerable target
machine in an isolated lab environment to observe performance degradation and
service disruption.

---

## Objectives
- Simulate network-layer and application-layer DoS attacks
- Observe system and service behavior under attack
- Understand mitigation strategies for different attack layers

---

## Attack Types Simulated
- ICMP Flood (network-layer)
- Slow HTTP attack (application-layer)

---

## Tools Used
- hping3
- slowhttptest
- Netstat
- Linux networking utilities

---

## Methodology (High Level)

### 1. Lab Setup & Verification
Connectivity between attacker and target machines was verified to ensure both
systems were reachable within the isolated network.

---

### 2. ICMP Flood Attack
A high volume of ICMP echo requests was generated to overwhelm the target’s
network stack and CPU resources.

**Observed impact:**
- Severe system slowdown
- Delayed command execution
- Reduced host responsiveness

---

### 3. Slow HTTP Attack
A slow HTTP attack was launched by opening a large number of long-lived HTTP
connections to exhaust the web server’s connection pool.

**Observed impact:**
- Gradual response time degradation
- Eventual web service unavailability

---

## Key Findings
- Network-layer floods can overwhelm host resources with minimal complexity
- Application-layer attacks can cause outages without high bandwidth usage
- Different attack layers require different defensive strategies

---

## Defensive Perspective
- Rate-limit or filter excessive ICMP traffic
- Use reverse proxies with strict connection timeouts
- Implement WAFs and connection-limiting mechanisms
- Monitor for traffic spikes and abnormal connection behavior

---

## Lessons Learned
This lab demonstrated how availability can be disrupted at multiple layers and
highlighted the importance of layered defenses tailored to the attack type.

---

## Notes
All tests were conducted in an isolated lab environment on systems owned by the
tester. This documentation focuses on learning outcomes and mitigation awareness.

