# Root-Me — TryHackMe

## Overview
Root-Me is a TryHackMe Capture The Flag (CTF) challenge focused on web enumeration,
file upload exploitation, and Linux privilege escalation.  
The objective was to gain initial access to the target system and escalate privileges
to obtain root-level access.

This challenge followed a full penetration testing workflow from reconnaissance to
post-exploitation.

---

## Objectives
- Enumerate open ports and exposed services
- Identify vulnerable web functionality
- Exploit a file upload mechanism to gain a shell
- Escalate privileges to root
- Document methodology and learning outcomes

---

## Tools Used
- Kali Linux
- Nmap
- Gobuster
- Nikto
- Netcat
- Linux command-line utilities
- GTFOBins

---

## Methodology (High Level)

### 1. Network & Service Enumeration
The target machine was scanned to identify open ports and service versions.  
Two main services were discovered:
- SSH (22)
- HTTP (80)

This established the initial attack surface.

---

### 2. Web Enumeration
Directory enumeration was performed to discover hidden paths and functionality.
This revealed directories related to file uploads and administrative panels.

Manual browsing was used to further inspect available features.

---

### 3. Initial Exploitation
A vulnerable file upload mechanism was identified.  
By bypassing file extension filtering, a server-side script was successfully uploaded
and executed, resulting in a reverse shell connection to the attacker machine.

This provided user-level access to the system.

---

### 4. Post-Exploitation & Privilege Escalation
After gaining shell access, the system was enumerated for privilege escalation vectors.
SUID binaries were identified and analysed.

Using known GTFOBins techniques, a misconfigured binary was leveraged to escalate
privileges and obtain root access on the target machine.

---

## Key Vulnerabilities Identified
- Insecure file upload validation (blacklist-based filtering)
- Executable files stored within web-accessible directories
- Misconfigured SUID binaries enabling privilege escalation

---

## Skills Demonstrated
- Network and service enumeration
- Web directory discovery
- File upload exploitation
- Reverse shell handling
- Linux privilege escalation
- Structured penetration testing methodology

---

## Lessons Learned
This challenge reinforced the importance of:
- Thorough enumeration before exploitation
- Understanding how upload filters can be bypassed
- Systematic privilege escalation using SUID binaries
- Applying a clear, step-by-step methodology during assessments

---

## Hardening Recommendations
- Enforce strict whitelist-based file upload validation
- Disable script execution in upload directories
- Remove unnecessary SUID permissions
- Apply the principle of least privilege
- Monitor and log suspicious upload activity

---

## Notes
This write-up focuses on methodology and learning outcomes.
Flags, credentials, and sensitive details are intentionally omitted.
All activities were performed in a controlled lab environment for educational purposes only.

