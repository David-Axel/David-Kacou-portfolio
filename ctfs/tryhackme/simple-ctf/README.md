# Simple CTF — TryHackMe

## Overview
Simple CTF is a TryHackMe Capture The Flag (CTF) challenge focused on service
enumeration, web application exploitation, SQL injection, and Linux privilege
escalation.

The objective was to enumerate exposed services, identify a vulnerable content
management system, exploit an SQL injection vulnerability to obtain credentials,
and escalate privileges to gain root access.

---

## Objectives
- Enumerate running services and open ports
- Identify vulnerable web technologies
- Exploit an SQL injection vulnerability
- Gain authenticated access via recovered credentials
- Escalate privileges to root

---

## Tools Used
- Nmap
- Gobuster
- Web browser
- Linux command-line utilities
- Exploit Database (research)

---

## Methodology (High Level)

### 1. Network & Service Enumeration
Initial reconnaissance was performed to identify open ports and running services.
The target system exposed multiple services, including:
- FTP (21)
- HTTP (80)
- SSH (non-standard port)

Service version detection helped guide further enumeration and exploitation.

---

### 2. Web Enumeration & CMS Identification
The web application hosted on port 80 was enumerated to discover hidden directories.
This process revealed a page indicating the use of **CMS Made Simple**.

Inspection of the CMS version confirmed it was an outdated release.

---

### 3. Vulnerability Identification
Research into CMS Made Simple revealed a known **SQL injection vulnerability**
affecting versions below a specific release.

This vulnerability was publicly documented under **CVE-2019-9053**, providing
a reliable exploitation path.

---

### 4. Exploitation & Credential Recovery
The SQL injection vulnerability was exploited to extract authentication data from
the backend database.

Recovered credentials were successfully reused to authenticate to the system via
SSH, providing user-level access.

---

### 5. Privilege Escalation
Once authenticated, privilege enumeration was conducted to identify potential
escalation vectors.

Misconfigured sudo permissions allowed execution of a permitted binary, which was
leveraged to escalate privileges and obtain root access.

---

## Key Vulnerabilities Identified
- Outdated CMS with known SQL injection vulnerability (CVE-2019-9053)
- Insecure credential storage enabling extraction via SQLi
- Misconfigured sudo permissions enabling privilege escalation

---

## Skills Demonstrated
- Network and service enumeration
- Web directory discovery
- CMS vulnerability research
- SQL injection exploitation
- Credential reuse
- Linux privilege escalation
- End-to-end penetration testing methodology

---

## Lessons Learned
This challenge reinforced the importance of:
- Identifying outdated software during enumeration
- Understanding the impact of SQL injection vulnerabilities
- Avoiding credential reuse across services
- Properly auditing sudo permissions on Linux systems

---

## Hardening Recommendations
- Keep CMS platforms and plugins fully up to date
- Use parameterized queries to prevent SQL injection
- Secure and hash credentials using strong algorithms
- Restrict sudo permissions to only essential commands
- Monitor authentication attempts and unusual database queries

---

## Notes
This write-up focuses on methodology and learning outcomes.
Flags, credentials, and sensitive details are intentionally omitted.
All activities were performed in a controlled lab environment for educational purposes only.
