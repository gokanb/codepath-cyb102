# CodePath CYB102 — Intermediate Cybersecurity

> Blue-team / SOC analyst coursework: eight hands-on security projects and a group capstone, completed through CodePath's 10-week Intermediate Cybersecurity course.

![CodePath](https://img.shields.io/badge/CodePath-CYB102-0b7285) ![Focus](https://img.shields.io/badge/focus-Blue%20Team%20%2F%20SOC-1f3864) ![Tools](https://img.shields.io/badge/tools-Splunk%20%7C%20Wireshark%20%7C%20Snort-informational) ![License](https://img.shields.io/badge/License-MIT-lightgrey)

## About

This repository documents the work I completed in **CodePath's CYB102: Intermediate Cybersecurity** — a 10-week course focused on **blue-team defense and Security Operations Center (SOC) work**. Each week paired a hands-on lab with an individual project, and the course ended with a group capstone. Every project here includes what I did, the tools I used, what I found, and screenshots of the actual work.

The thread running through all of it: **detect → analyze → respond → document**, the same loop a real SOC analyst runs every day.

## Projects

| # | Project | What I did | Key tools |
|---|---------|-----------|-----------|
| 1 | [Network Forensics](projects/01-network-forensics-wireshark/) | Traced a business email compromise (BEC) phishing attack back to the attacker's IP from packet captures | Wireshark |
| 2 | [Host Intrusion Detection](projects/02-host-intrusion-detection-auditd/) | Wrote audit rules to catch file tampering and matched each attack to the file it changed | Linux `auditd`, `ausearch` |
| 3 | [Directory Traversal Attack](projects/03-directory-traversal-attack/) | Exploited a path-traversal flaw in an FTP server to read off-limits files | Bash, Node.js, Linux |
| 4 | [DoS Mitigation](projects/04-dos-mitigation-nginx/) | Ran a Slowloris attack, then wrote nginx rules that defeated it — proven with traffic graphs and packet analysis | nginx, Slowloris, Netdata, Wireshark |
| 5 | [Splunk SIEM CTF](projects/05-splunk-siem-ctf/) | Solved 15 SPL challenges, including tracing a malware upload to its source IP and user | Splunk (SPL) |
| 6 | [Incident Response](projects/06-incident-response-catalyst/) | Documented a malware case end-to-end and wrote a NIST-framework analysis of the SolarWinds/SUNBURST breach | Catalyst, VirusTotal, MITRE ATT&CK, NIST |
| 7 | [Threat Hunting](projects/07-threat-hunting-splunk/) | Hunted SolarWinds Orion C2 beacons in proxy logs, confirmed IOCs on VirusTotal, and built a monitoring dashboard | Splunk, VirusTotal, threat-intel feeds |
| — | [Capstone: The Data Dig](capstone-data-dig/) | Full SOC investigation of the CICIDS2017 dataset using the NIST SP 800-61 playbook and TheHive case management | TheHive, Splunk, Wireshark, MITRE ATT&CK |
| 0 | [Prework](projects/00-prework-bash-blueteam/) | Bash scripting challenges + blue-team fundamentals | Bash, Linux |

## Skills demonstrated

- **SIEM & log analysis** — Splunk SPL: searching, correlation, `stats`, dashboards, CTF-style investigation
- **Network forensics** — packet capture analysis in Wireshark; SMTP/IMF, SYN/RST, and protocol filtering
- **Incident response** — the full NIST SP 800-61 lifecycle; case management in Catalyst and TheHive
- **Threat intelligence** — IOC research with VirusTotal; mapping attacks to the MITRE ATT&CK framework
- **Detection & defense** — Snort rules, Linux `auditd` file-integrity monitoring, nginx DoS mitigation
- **Offensive context** — directory traversal and Slowloris attacks, run to understand how to defend against them
- **Documentation** — writing clear, defensible analyst reports (the part that actually matters in a SOC)

## About CodePath CYB102

[CodePath](https://codepath.org/courses/cybersecurity) is a national nonprofit offering no-cost tech courses. CYB102 is the intermediate course in its Cybersecurity pathway — a 10-week, instructor-led program covering blue-team operations, SOC tooling, and incident response. Students who complete it earn a certificate of completion and CodePath alumni status.

## Note on the capstone

The capstone ("The Data Dig") was a **group project (team of 4, Group 14)**. I led the analysis: I built the TheHive case-management environment, created and documented all four incident cases, did the MITRE ATT&CK mapping, and wrote the triage framework and remediation plan. Teammates' names are kept private here out of respect for their privacy.

## Disclaimer

All work was performed in CodePath's provided lab environments against intentionally vulnerable targets and public research datasets, for **educational purposes**. Nothing here was run against systems I don't own or wasn't authorized to test.

## License

Released under the [MIT License](LICENSE).
