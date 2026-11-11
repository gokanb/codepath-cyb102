# Project 2 — Host Intrusion Detection with Linux auditd

**Course:** CodePath CYB102 · Week 2 · **Tools:** Linux `auditd`, `ausearch`, Vim

## The scenario

In real incident response the first question is: *"what changed on this system, and when?"* The Linux Audit daemon (`auditd`) answers that by watching files and recording exactly which process touched them. My job: write audit rules to monitor a set of protected files, then run three attack scripts that silently modified them — and use the logs to prove **which attack changed which file**.

## What I did

1. Wrote `auditd` write-watch rules (with filter keys) on the files in `/protected_files` so any modification would be logged.
2. Ran the three attack scripts (`attack-a`, `attack-b`, `attack-c`) against the protected directory.
3. Used `ausearch` filtered by key to pull each change event out of `/var/log` and attribute it to the process that made it.

## What I found

| Attack | File it changed |
|--------|-----------------|
| attack-a | `cloudia.txt` |
| attack-b | `oakley.txt` |
| attack-b | `squeaky.txt` |
| attack-c | `precipitation.csv` |

> attack-b modified **two** files — exactly the kind of detail a file-integrity log surfaces that you'd never catch by eye.

## Why it matters

Host-based detection catches what network monitoring can't — changes that happen on the machine itself. A file-level audit trail is the backbone of post-incident forensics and breach attribution.

## Skills

Linux `auditd` rules · file-integrity monitoring · `ausearch` log filtering · breach attribution · blue-team host defense
