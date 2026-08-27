# Home Lab – Penetration Testing (Kali Linux & Metasploitable2)

## Overview
A self-hosted penetration testing lab built to practice offensive security fundamentals in a safe, isolated environment.

## Tools Used
- Kali Linux (attacker machine)
- Metasploitable2 (intentionally vulnerable target)
- VMware Workstation
- Nmap (network scanning)
- Netcat (exploitation)

## Setup
- Both VMs configured on an isolated Host-only virtual network
- No internet exposure to the vulnerable target machine

## Methodology
1. **Reconnaissance:** Performed a service/version scan using Nmap
   `nmap -sV -Pn <target-ip>`
   → Identified multiple open ports and outdated services (FTP, Telnet, misconfigured shell services)

2. **Exploitation:** Identified an exposed root shell service on port 1524
   Connected using Netcat and obtained root access on the target machine without authentication

## Key Findings
- Outdated FTP service (vsftpd 2.3.4) with known backdoor vulnerability
- Unencrypted Telnet service exposed
- Misconfigured backdoor shell granting unauthenticated root access

## Lessons Learned
- Importance of patching outdated services
- Risks of exposing unauthenticated administrative shells
- Practical application of reconnaissance-to-exploitation methodology

## Disclaimer
This lab was conducted entirely within an isolated virtual environment for educational purposes only.
