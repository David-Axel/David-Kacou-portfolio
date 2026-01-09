
# Lazy Admin — TryHackMe

## Overview
Lazy Admin is a TryHackMe Capture The Flag (CTF) challenge focused on web enumeration,
content management system (CMS) exploitation, and Linux privilege escalation.

The objective was to identify weaknesses in a misconfigured CMS installation,
gain initial shell access, and escalate privileges to obtain root access on the system.

---

## Objectives
- Enumerate exposed services and web directories
- Identify vulnerabilities in a CMS environment
- Exploit insecure backup and file upload functionality
- Gain user-level access via a reverse shell
- Escalate privileges to root

---

## Tools Used
- Nmap
- Gobuster
- Linux command-line utilities
- Reverse shell payload
- Exploit Database (research)
- Sudo / file permission analysis

---

## Methodology (High Level)

### 1. Network & Service Enumeration
Initial reconnaissance was performed to identify open ports and exposed services.
The system revealed:
- SSH (22)
- HTTP (80)

This indicated a web-based attack surface supported by remote access.

---

### 2. Web Enumeration
The web application did not expose obvious functionality on the landing page.
Directory enumeration was therefore conducted to discover hidden paths.

A `/content` directory was identified, revealing the use of the **SweetRice CMS**.

---

### 3. Vulnerability Identification
Research into SweetRice CMS revealed known vulnerabilities, including:
- Backup disclosure
- Arbitrary file upload

The backup disclosure vulnerability was exploited first, allowing access to
sensitive configuration data, including administrative credentials.

---

### 4. Initial Exploitation
Using the recovered credentials, access to the CMS administrative panel was obtained.
An insecure file upload mechanism was then abused to upload a server-side script,
which was executed to establish a reverse shell connection.

This resulted in user-level access to the target system.

---

### 5. Privilege Escalation
Post-exploitation enumeration revealed a writable script executed with elevated
privileges. By modifying this script to include a reverse shell payload, the script
was leveraged to escalate privileges and obtain root access.

---

## Key Vulnerabilities Identified
- Insecure CMS backup exposure
- Weak access control on sensitive files
- Arbitrary file upload vulnerability
- Misconfigured privilege escalation mechanism

---

## Skills Demonstrated
- Network and web enumeration
- CMS vulnerability research
- Credential reuse and access chaining
- Reverse shell exploitation
- Linux privilege escalation
- Structured penetration testing workflow

---

## Lessons Learned
This challenge highlighted the risks of poor CMS hardening and insecure backups.
It reinforced the importance of:
- Restricting access to backup files
- Securing file upload functionality
- Auditing scripts executed with elevated privileges
- Performing thorough post-exploitation enumeration

---

## Hardening Recommendations
- Remove or protect backup files from public access
- Enforce strict file upload validation and execution controls
- Apply the principle of least privilege to scripts and services
- Regularly update and audit CMS installations
- Monitor administrative access and file modifications

---

## Notes
This write-up focuses on methodology and learning outcomes.
Flags, credentials, and sensitive information are intentionally omitted.
All activities were performed in a controlled lab environment for educational purposes only.
