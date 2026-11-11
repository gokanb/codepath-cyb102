# Project 1 — Network Forensics: Catching a Phishing Attacker

**Course:** CodePath CYB102 · Week 1 · **Tools:** Wireshark

## The scenario

A business email compromise (BEC) — the kind of scam that cost companies $26B between 2016–2019. Someone inside the network was sending phishing emails trying to trigger a fraudulent wire transfer. I was handed a set of `.pcap` packet captures and had to figure out **who the attacker was**, using nothing but the network traffic.

## What I did

1. Opened each `.pcap` in Wireshark and applied the display filter `smtp` to find which captures actually contained email traffic — ruling out the ones that didn't.
2. On the captures with email traffic, switched to `smtp && imf` to reconstruct the email headers (From, To, Subject) and MIME content.
3. Inspected the `MAIL FROM` fields and the SMTP `DATA` section, which exposed the reconstructed email headers and an attachment, and traced the phishing activity back to a single internal host.

## What I found

| Finding | Value |
|---------|-------|
| Malicious actor's IP | **10.10.1.4** |
| Method | Phishing emails sent over SMTP, headers + attachment visible in the `DATA` section |

## Why it matters

This is the foundation of network forensics: packet captures let you inspect activity that email clients hide from the user, and the ability to read raw SMTP traffic is how analysts attribute an attack to a specific host — even when the display name and sender are spoofed.

## Skills

Wireshark display filters (`smtp`, `imf`) · SMTP/email protocol analysis · packet-level attribution · network forensics
