# Publisher — TryHackMe

## Overview
Publisher is a TryHackMe Capture The Flag (CTF) challenge focused on web enumeration,
content management system (CMS) identification, and remote code execution (RCE).

The objective was to identify the underlying CMS, research known vulnerabilities,
exploit a remote code execution flaw, and gain user-level access to the target system.

---

## Objectives
- Enumerate exposed services and web technologies
- Identify the CMS and its version
- Research known vulnerabilities
- Exploit a remote code execution vulnerability
- Obtain initial shell access on the target system

---

## Tools Used
- Ping
- Nmap
- Gobuster
- Metasploit Framework
- Linux command-line utilities

---

## Methodology (High Level)

### 1. Network & Service Enumeration
Initial reconnaissance was performed to confirm host availability and identify
exposed services. The following services were discovered:
- SSH (22)
- HTTP (80)

This indicated a web-based attack surface supported by remote access.

---

### 2. Web Enumeration & CMS Identification
The web application hosted on port 80 was manually inspected. Indicators within
the page content suggested the use of a content management system (CMS).

Directory enumeration was conducted, which revealed a `/spip` directory.
Inspection of this directory confirmed that the website was running **SPIP CMS**.

Further analysis of the source code and page content allowed identification of the
specific CMS version in use.

---

### 3. Vulnerability Research
Once the CMS and version were identified, vulnerability research was conducted
using public exploit databases.

This revealed a known **remote code execution (RCE)** vulnerability affecting the
identified SPIP version, providing a clear exploitation path.

---

### 4. Exploitation & Initial Access
Using the Metasploit Framework, the appropriate SPIP remote code execution module
was selected and configured.

Successful exploitation resulted in execution of arbitrary commands on the target
system and the establishment of a reverse shell, providing user-level access.

---

## Key Vulnerabilities Identified
- Outdated CMS with publicly known vulnerabilities
- Remote code execution through insufficient input handling
- Lack of hardening and patch management

---

## Skills Demonstrated
- Network and web enumeration
- CMS fingerprinting and version identification
- Vulnerability research and validation
- Exploitation using Metasploit
- Reverse shell acquisition
- Structured penetration testing workflow

---

## Lessons Learned
This challenge reinforced the importance of:
- Accurate CMS identification during reconnaissance
- Keeping web applications and CMS platforms up to date
- Understanding how public exploits map to real-world vulnerabilities
- Validating vulnerabilities before exploitation

---

## Hardening Recommendations
- Regularly update and patch CMS installations
- Remove unused CMS components and directories
- Restrict access to administrative and sensitive paths
- Monitor and log suspicious web activity
- Perform routine vulnerability scanning and audits

---

## Notes
This write-up focuses on methodology and learning outcomes.
Flags, credentials, and sensitive details are intentionally omitted.
All activities were performed in a controlled lab environment for educational purposes only.

