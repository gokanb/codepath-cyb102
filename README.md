# CodePath CYB102 — Intermediate Cybersecurity

> My complete blue-team / SOC analyst portfolio from CodePath's 10-week Intermediate Cybersecurity course — every weekly lab and project, plus a group capstone, with real tool output and screenshots.

![CodePath](https://img.shields.io/badge/CodePath-CYB102-0b7285) ![Focus](https://img.shields.io/badge/focus-Blue%20Team%20%2F%20SOC-1f3864) ![SIEM](https://img.shields.io/badge/SIEM-Splunk-ff8c00) ![Framework](https://img.shields.io/badge/IR-NIST%20SP%20800--61-005073) ![MITRE](https://img.shields.io/badge/mapped-MITRE%20ATT%26CK-d9534f) ![License](https://img.shields.io/badge/License-MIT-lightgrey)

## About

This repository documents everything I built in **CodePath's CYB102: Intermediate Cybersecurity** — a 10-week, instructor-led course focused on **blue-team defense and Security Operations Center (SOC) work**. Each week paired a **guided lab** (learning a tool hands-on) with an **individual project** (applying it to a real scenario), and the course ended with a **group capstone**.

Everything here runs the same loop a real SOC analyst runs every day: **detect → analyze → respond → document**.

## The full curriculum — every lab & project

Each week: a **Lab** (guided, parts 0–2) built the skill; the **Project** (part 3) applied it to a scenario I had to solve myself.

| Wk | Lab (guided) | Project (applied) | Tools |
|----|-------------|-------------------|-------|
| 1 | *It Wasn't Me* — trace a rogue user: PCAP → DHCP → security logs | **[Network Forensics](projects/01-network-forensics-wireshark/)** — trace a BEC phishing attacker to their IP | Wireshark, DHCP/SMTP |
| 2 | *Oops!…I Audit Again* — host intrusion detection with the Linux Audit daemon | **[Host Intrusion Detection](projects/02-host-intrusion-detection-auditd/)** — match each attack to the file it tampered | `auditd`, `ausearch`, Vim |
| 3 | *That's Snort of a Lot of Rules* — write Snort NIDS detection rules | **[Directory Traversal Attack](projects/03-directory-traversal-attack/)** — exploit a path-traversal flaw, then detect it with Snort | Snort, Bash, Node.js |
| 4 | *Career presentation week* | — | — |
| 5 | *Monkey in the Middle* — HTTPS interception with mitmproxy | **[DoS Mitigation](projects/04-dos-mitigation-nginx/)** — defeat a Slowloris attack with nginx, proven in packets | nginx, Slowloris, Netdata, mitmproxy, Wireshark |
| 6 | *Splunkin' Around* — Splunk SIEM fundamentals (SPL) | **[Splunk SIEM CTF](projects/05-splunk-siem-ctf/)** — 15 challenges incl. tracing a malware upload to its source | Splunk (SPL) |
| 7 | *Cat-a-logging Incidents* — run a case in the Catalyst IR platform | **[Incident Response](projects/06-incident-response-catalyst/)** — document a malware case + NIST analysis of SolarWinds/SUNBURST | Catalyst, VirusTotal, MITRE ATT&CK, NIST |
| 8 | *Splunking for Threats* — ingest a threat-intel feed into Splunk | **[Threat Hunting](projects/07-threat-hunting-splunk/)** — hunt SolarWinds Orion C2 beacons, build an IOC dashboard | Splunk, VirusTotal, threat-intel feeds |
| 9–10 | *Guided Threat Hunt* → Demo Day | **[Capstone: The Data Dig](capstone-data-dig/)** — full SOC investigation of CICIDS2017 with NIST SP 800-61 + TheHive | TheHive, Splunk, Wireshark, MITRE ATT&CK |
| 0 | — | **[Prework](projects/00-prework-bash-blueteam/)** — Bash challenges + blue-team fundamentals | Bash, Linux |

> Each project folder has its own detailed write-up and screenshots of the real work.

## Highlights

- **🔍 SIEM investigation (Splunk)** — solved a 15-challenge CTF, traced a malware upload (`EvilScript.exe`) across proxy/login/hash logs to its source IP and user, and built correlation searches + dashboards.
- **🚨 Incident response (NIST SP 800-61)** — documented a full malware case in Catalyst and wrote a five-phase NIST analysis of the **SolarWinds/SUNBURST** supply-chain breach, mapped to MITRE ATT&CK.
- **🎯 Threat hunting** — proactively hunted **SolarWinds Orion C2 beacons** in proxy logs, confirmed IOCs on VirusTotal (12/94, 10/94, 9/94 malicious), ran a Log4Shell hunt, and built a monitoring dashboard.
- **🛡️ Detection & defense** — Snort NIDS rules, `auditd` file-integrity monitoring, and nginx DoS mitigation proven at the packet level (3,000 SYN → 3,000 RST).
- **⚔️ Offensive context** — ran directory-traversal and Slowloris attacks myself, so I understand what the defenses are actually stopping.
- **📊 Capstone** — led a 4-person SOC investigation of the CICIDS2017 dataset: 4 documented incident cases in TheHive, full MITRE ATT&CK mapping, triage framework, and remediation plan.

## Skills demonstrated

| Area | Skills |
|------|--------|
| **SIEM & log analysis** | Splunk SPL — searching, correlation, `stats`, `dedup`, dashboards, timeline building |
| **Network forensics** | Wireshark — SMTP/IMF, DHCP, SYN/RST/FIN, protocol filtering, attribution |
| **Incident response** | NIST SP 800-61 lifecycle; Catalyst & TheHive case management; lessons-learned reports |
| **Threat intelligence** | IOC research (VirusTotal), feed ingestion, MITRE ATT&CK mapping |
| **Detection engineering** | Snort NIDS rules, Linux `auditd` HIDS, nginx hardening |
| **Offensive (for defense)** | directory traversal, Slowloris DoS, mitmproxy MITM |
| **Professional** | analyst-grade documentation, triage/severity frameworks, team leadership, technical communication |

## About CodePath CYB102

[CodePath](https://codepath.org/courses/cybersecurity) is a national nonprofit that offers no-cost tech courses. CYB102 is the intermediate course in its Cybersecurity pathway — 10 weeks, instructor-led, covering blue-team operations, SOC tooling, and incident response. Completing it earns a certificate of completion and CodePath alumni status.

## Note on the capstone

The capstone ("The Data Dig") was a **group project (team of 4, Group 14)**. I led the analysis — I built the TheHive case-management environment, created and documented all four incident cases, did the MITRE ATT&CK mapping, and wrote the triage framework and remediation plan. Teammates' names are kept private here out of respect for their privacy.

## Disclaimer

All work was performed in CodePath's provided lab environments, against intentionally vulnerable targets and public research datasets, for **educational purposes only**. Nothing was run against systems I don't own or wasn't authorized to test.

## License

Released under the [MIT License](LICENSE).
