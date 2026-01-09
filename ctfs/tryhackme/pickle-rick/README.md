# Pickle Rick — TryHackMe

## Overview
Pickle Rick is a TryHackMe Capture The Flag (CTF) challenge focused on web enumeration,
information discovery, command execution, and Linux privilege escalation.

The objective was to enumerate the target system, uncover hidden information within
the web application, gain command execution, and leverage misconfigured privileges
to obtain full system access.

---

## Objectives
- Enumerate exposed network services
- Discover hidden web content and credentials
- Gain interactive command execution
- Escalate privileges through sudo misconfiguration
- Retrieve all required flags

---

## Tools Used
- Ping
- Nmap
- Gobuster
- Nikto
- Linux command-line utilities
- Netcat
- Sudo

---

## Methodology (High Level)

### 1. Network & Service Enumeration
Initial reconnaissance confirmed host reachability and identified exposed services.
The target system revealed:
- SSH (22)
- HTTP (80)

This indicated a web-based entry point with potential remote access capabilities.

---

### 2. Web Enumeration & Information Discovery
Manual inspection of the web page and its source code revealed hints related to
usernames and potential access paths.

Directory enumeration further uncovered hidden resources such as configuration
files and administrative directories, providing useful information for progression.

---

### 3. Vulnerability Identification
A restricted command execution interface was identified within the web application.
Although limited, this functionality allowed system commands to be executed indirectly,
providing an initial foothold on the target.

---

### 4. Initial Access & Shell Execution
By leveraging the available command execution functionality, a reverse shell payload
was executed, establishing an interactive shell session on the target system.

This enabled exploration of the filesystem and retrieval of user-level flags.

---

### 5. Privilege Escalation
Privilege enumeration revealed that the compromised user had passwordless sudo
permissions. This misconfiguration allowed direct escalation to root privileges.

Once elevated access was obtained, remaining system-level flags were accessed.

---

## Key Vulnerabilities Identified
- Information leakage through web content and source code
- Insecure command execution functionality
- Passwordless sudo configuration allowing privilege escalation

---

## Skills Demonstrated
- Network and web enumeration
- Manual information discovery
- Command execution exploitation
- Reverse shell handling
- Linux privilege escalation
- Logical attack path development

---

## Lessons Learned
This challenge reinforced the importance of:
- Reviewing source code for sensitive information
- Restricting command execution capabilities
- Auditing sudo permissions and privilege assignments
- Combining enumeration with logical reasoning rather than relying solely on tools

---

## Hardening Recommendations
- Remove sensitive information from client-side source code
- Restrict or disable command execution features in web applications
- Enforce least-privilege sudo configurations
- Monitor and log suspicious command execution activity

---

## Notes
This write-up focuses on methodology and learning outcomes.
Flags, credentials, and sensitive details are intentionally omitted.
All activities were performed in a controlled lab environment for educational purposes only.

