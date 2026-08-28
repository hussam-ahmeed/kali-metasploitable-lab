# Home Lab – Penetration Testing (Kali Linux & Metasploitable2)

## Overview
A self-hosted penetration testing lab built to practice offensive security fundamentals in a safe, isolated environment.

## Tools Used
- Kali Linux (attacker machine)
- Metasploitable2 (intentionally vulnerable target)
- VMware Workstation
- Nmap (network scanning)
- Netcat (manual exploitation)
- Metasploit Framework (framework-based exploitation)

## Setup
- Both VMs configured on an isolated Host-only virtual network
- No internet exposure to the vulnerable target machine

## Methodology

1. **Reconnaissance:** Performed a service/version scan using Nmap
   `nmap -sV -Pn <target-ip>`
   → Identified multiple open ports and outdated services (FTP, Telnet, misconfigured shell services)

2. **Exploitation #1 – Manual:** Identified an exposed root shell service on port 1524 (bindshell)
   Connected using Netcat and obtained root access on the target machine without authentication

3. **Exploitation #2 – Framework-based:** Identified vsftpd 2.3.4 (port 21), a version with a known backdoor vulnerability (CVE-2011-2523)
   Used Metasploit Framework (`exploit/unix/ftp/vsftpd_234_backdoor`) to gain a Meterpreter session with root privileges

## Key Findings
- Outdated FTP service (vsftpd 2.3.4) with known backdoor vulnerability
- Unencrypted Telnet service exposed
- Misconfigured backdoor shell (port 1524) granting unauthenticated root access
- Demonstrated both manual exploitation (Netcat) and framework-based exploitation (Metasploit Framework)

## Lessons Learned
- Importance of patching outdated services
- Risks of exposing unauthenticated administrative shells
- Practical application of reconnaissance-to-exploitation methodology
- Comparison between manual exploitation techniques and automated framework tools

## Disclaimer
This lab was conducted entirely within an isolated virtual environment for educational purposes only.
