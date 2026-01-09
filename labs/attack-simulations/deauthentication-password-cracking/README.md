# Deauthentication Attack & Wi-Fi Password Cracking

## Overview
This lab demonstrates a wireless security assessment involving deauthentication
attacks and WPA/WPA2 password cracking in a controlled environment.

The objective was to understand how attackers capture authentication handshakes
and why weak Wi-Fi passwords pose a serious security risk.

---

## Objectives
- Enable wireless monitor mode
- Capture WPA authentication handshakes
- Perform controlled deauthentication attacks
- Attempt password cracking using a wordlist
- Evaluate defensive countermeasures

---

## Tools Used
- airmon-ng
- airodump-ng
- aireplay-ng
- aircrack-ng
- Wireless USB adapter (monitor mode capable)

---

## Methodology (High Level)

### 1. Wireless Interface Preparation
The wireless adapter was identified and placed into monitor mode to allow packet
capture and injection.

---

### 2. Network Discovery
Nearby wireless networks were scanned to identify the target access point,
including channel, encryption type, and connected clients.

---

### 3. Deauthentication Attack
Deauthentication frames were sent to force connected clients to disconnect and
reconnect, triggering the WPA four-way handshake.

---

### 4. Handshake Capture & Password Cracking
Once the handshake was captured, a wordlist-based attack was performed to test
password strength.

---

## Key Findings
- WPA handshakes can be captured without joining the network
- Weak passwords are vulnerable to dictionary attacks
- Deauthentication attacks exploit management frame weaknesses

---

## Defensive Perspective
- Use strong, non-dictionary Wi-Fi passwords
- Enable WPA2/WPA3 with management frame protection (802.11w)
- Monitor for excessive deauthentication frames
- Limit signal range to reduce attack surface

---

## Lessons Learned
This lab highlighted the importance of wireless hardening and demonstrated how
easily weak Wi-Fi configurations can be compromised.

---

## Notes
All testing was conducted with explicit permission in a controlled lab environment.
Sensitive data and credentials are intentionally omitted.

