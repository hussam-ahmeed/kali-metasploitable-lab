# Home Lab Penetration Testing

A self-hosted penetration-testing lab built with Kali Linux and Metasploitable2 to practice reconnaissance, service enumeration, vulnerability validation, and responsible security reporting in an isolated environment.

> **Educational use only:** Perform security testing only on systems you own or have explicit permission to assess.

## Lab environment

- Kali Linux — assessment workstation
- Metasploitable2 — intentionally vulnerable target
- VMware Workstation — virtualization
- Host-only networking — prevents the vulnerable target from being exposed to the internet

## Tools

- Nmap for host and service discovery
- Netcat for manual service validation
- Metasploit Framework for controlled exploit verification

## Methodology

1. Confirm that the lab is isolated and identify the target address.
2. Perform service and version discovery with Nmap.
3. Research findings and validate vulnerabilities only inside the lab.
4. Record evidence, impact, and remediation recommendations.
5. Remove test artifacts and document lessons learned.

## Findings documented in this lab

- An outdated `vsftpd 2.3.4` service associated with CVE-2011-2523.
- An unencrypted Telnet service.
- A misconfigured bind shell on port `1524` that permits unauthenticated root access.
- A comparison between manual validation and framework-assisted testing.

The screenshots in this repository are demonstrations from the isolated lab and should not be interpreted as authorization to test third-party systems.

## Repository contents

- `README.md` — lab scope, methodology, and findings
- `nmap-scan-result.png` — example enumeration evidence
- `meterpreter-root-session.png` — example framework-session evidence
- `root-shell-exploit.png` — example manual-validation evidence

## Key lessons

- Patch or remove outdated services.
- Never expose administrative shells without strong authentication.
- Avoid Telnet where encrypted alternatives are available.
- Keep vulnerable practice targets isolated from production and the public internet.
- A professional report should connect each finding to evidence, risk, and remediation.

## Disclaimer

This project was completed in an isolated virtual environment for educational purposes. The author does not endorse unauthorized access, exploitation, or disruption of systems.
