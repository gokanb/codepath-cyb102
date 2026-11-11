# Project 5 — Splunk SIEM Capture-the-Flag

**Course:** CodePath CYB102 · Week 6 · **Tools:** Splunk (SPL)

## The scenario

A SIEM aggregates logs from every device on a network into one searchable place. This was a **Capture-the-Flag**: 15 challenges where I had to form a hypothesis and prove it with Splunk searches — exactly how a SOC analyst works a real investigation. Part 1 was search practice on a Netflix dataset; Part 2 was a live malware investigation at the fictional "PathCode Inc."

## Part 1 — SPL search fundamentals (Netflix data)

Ten challenges building up SPL skills — filtering, `stats count by`, `sort`, `table`, `dedup`. A few examples:

| Challenge | Search I used | Answer |
|-----------|--------------|--------|
| Movies rated TV-PG | `index=main host=Netflix type="Movie" rating="TV-PG"` | 1,080 |
| Longest TV show by seasons | `... type="TV Show" | sort -num duration | head 1` | Grey's Anatomy, 17 seasons, TV-14 |
| Year with most G-rated movies | `... rating="G" | stats count by release_year | sort -count | head 1` | 2009 |
| Oldest TV show | `... | sort num(release_year) | head 1 | table title release_year` | Pioneers: First Women Filmmakers, 1925 |

## Part 2 — Investigating the malware (the real work)

Traced a malware upload end-to-end across proxy, login, and hash logs:

1. **Found the source IP** that uploaded a file matching a known-bad MD5 hash (`3AADBF7E...CBA4D`) → **192.168.1.10**.
2. **Pulled the attacker's login attempts** — the IP tried multiple usernames and finally uploaded as **ABurke**.
3. **Grabbed the User-Agent** of the successful upload → `Opera/75.0.3969.218`.
4. **Spotted a second uploader** around the same time (EChan, `192.168.1.8`) and compared the two files — **`EvilScript.exe` (malicious)** vs. `Style.css` (legit).

## What I took away

> The **timestamp** is the most important field a log can have. Connecting EChan's upload to ABurke's malware upload — ten minutes apart — is impossible without precise timing. Time is what ties every other field together.

## Skills

Splunk SPL (`stats`, `sort`, `dedup`, `table`, filtering) · SIEM investigation · log correlation · building an attack timeline · hash/IOC pivoting
