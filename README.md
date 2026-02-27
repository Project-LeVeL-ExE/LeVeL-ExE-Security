<div align="center">

# 🛡️ LeVeL-ExE DNS Blocklist

**Digital Peace, by Design.**

Protection without censorship — security without breakage.

[![License: GPLv3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Website](https://img.shields.io/badge/Web-level--exe.com-orange.svg)](https://level-exe.com)

[Website](https://level-exe.com) · [Repository](https://github.com/Project-LeVeL-ExE/LeVeL-ExE-Security.git) · [Report Issue](https://github.com/Project-LeVeL-ExE/LeVeL-ExE-Security/issues)

</div>

---

## What is LeVeL-ExE?

LeVeL-ExE is a **curated DNS blocklist** engineered to reduce your attack surface and protect your privacy at the network level — the first meaningful layer of defense between your devices and hostile infrastructure.

It blocks **malware, phishing, command-and-control servers, invasive trackers, surveillance infrastructure, and fraud networks** — while preserving normal access to the websites, apps, and services you use every day.

> **Our commitment**: we do not censor content, we do not geoblock, we do not filter based on politics or ideology. We block what endangers users — nothing more.

---

## Why DNS-Level Protection Matters

In a world of constant connectivity — work, identity, banking, communication — DNS resolution is the invisible backbone of every online interaction. Every website visit, every app connection, every system update begins with a DNS query.

If that query resolves to a malicious destination, the compromise has already begun.

LeVeL-ExE operates at this critical junction: blocking dangerous domains **before** they ever reach your browser, your device, or your data. It's not a replacement for endpoint security — it's the **first wall** that quietly reduces exposure every single day.

---

## Philosophy & Core Values

### 🎯 Precision Over Quantity
We prefer narrow, attributable indicators — specific hosts, subdomains, FQDNs — over broad blocks that create collateral damage. We will never block `google.com` even though dozens of its subdomains appear in our tracker lists. The goal is surgical intervention, not scorched earth.

### ✅ Verifiability
Every block has a technical rationale. Every entry is corroborated by at least one strong source (CERT advisory, vendor research with IOCs, forensic report) or multiple aligned moderate signals. If we can't verify it, we don't include it.

### 🔄 Reversibility
Threat infrastructure changes — domains get reassigned, sinkholes go active, providers remediate. Any entry can be reclassified or removed when context changes. Our methodology is built for correction, not permanence.

### 🌐 Compatibility ("No Breakage")
Security that breaks everyday life is not security — it's a denial of service against the user. We explicitly avoid blocking root domains of major hosting providers, CDNs, and PaaS platforms. We test for impact on login flows, payment APIs, OS updates, and app stores before promoting any entry.

### 🚫 No Censorship
We do not implement geographic, political, or content-based blocking. We do not block adult sites, gambling platforms, or editorial categories simply because of what they are. **User autonomy matters.**

---

## What We Block

| Category | Subcategories | Entries |
|---|---|---:|
| **Trackers & Surveillance** | Advertising, Tracking, Fingerprinting, Telemetry (General/AI/Apple/SmartTV), Government Surveillance, Spyware, Stalkerware | 3,160,308 |
| **Network Attacks** | Botnet C2, DNS Hijack, Rootkit C2, RAT, Ransomware C2, DynDNS Abuse | 1,077,097 |
| **Phishing & Fraud** | Credential Harvest, Brand Impersonation, Social Engineering, Typosquatting, Scam Infrastructure | 1,011,341 |
| **Malware & Virus** | Droppers, Infostealers, Loaders, Badware Hosters, Exploit Kits | 203,923 |
| **Complete** | All categories combined | 6,662,174 |
| **Whitelist** | Compatibility safeguards — domains explicitly allowed | 112,294 |

**Total entries across all lists: 12,391,810**

---

## What We Do NOT Block

- ❌ Content filtering, geoblocking, or political blocking
- ❌ Adult/gambling categories (unless tied to documented malicious activity)
- ❌ Root domains of major hosting providers, CDNs, or PaaS (AWS, Cloudflare, Vercel, Netlify...)
- ❌ Legitimate remote access tools (RDP, VNC, AnyDesk, TeamViewer) unless specific IOCs of abuse exist
- ❌ Security research platforms (Shodan, Censys) unless specific IOCs of abuse exist
- ❌ Domains without technical corroboration from a verifiable source

---

## What Sets Us Apart

Most blocklists are aggregations — large piles of domains merged from various feeds with minimal validation. LeVeL-ExE is different:

1. **Curated, not just aggregated**: every entry undergoes multi-source corroboration before inclusion.
2. **Category-separated architecture**: you choose what to block. Need only malware and phishing? Import those lists. Want full coverage? Use the complete list. Your network, your rules.
3. **Surveillance-aware**: we actively track and block mercenary spyware infrastructure (Pegasus, Predator, Hermit, FinFisher) and government surveillance endpoints when technically verifiable — something most blocklists ignore entirely.
4. **Emerging threat coverage**: dedicated categories for AI/GenAI abuse infrastructure, supply-chain compromise, MFA bypass infrastructure, and Java class-loading abuse.
5. **Multi-format distribution**: every list is published in 6 formats (Raw, Hosts, AdGuard, NextDNS, Unbound, RPZ) for maximum compatibility.
6. **Operational transparency**: weekly change logs with technical motivation for every addition, removal, and reclassification.
7. **Born from real experience**: this project was created after its founder experienced a sophisticated, layered cyberattack — not from a trend or a marketing idea.

---

## Available Lists & Formats

### Lists

| File | Description |
|---|---|
| `LeVeL-ExE DNS Blocklist - Complete.txt` | All categories combined (6,662,174 entries) |
| `LeVeL-ExE DNS Blocklist - Trackers & Surveillance.txt` | Trackers, advertising, fingerprinting, telemetry, surveillance (3,160,308 entries) |
| `LeVeL-ExE DNS Blocklist - Network Attacks.txt` | Botnet, C2, DNS hijack, rootkit, RAT, ransomware (1,077,097 entries) |
| `LeVeL-ExE DNS Blocklist - Phishing & Fraud.txt` | Phishing, social engineering, scam, typosquatting (1,011,341 entries) |
| `LeVeL-ExE DNS Blocklist - Malware & Virus.txt` | Malware distribution, droppers, infostealers, badware (203,923 entries) |
| `LeVeL-ExE DNS Whitelist.txt` | Compatibility safeguards (112,294 entries) |



### Download URLs (raw)

This ZIP contains the documentation only. The actual blocklist files are distributed via the GitHub repository/website.

**Raw GitHub pattern** (replace `<FILE>` with one of the filenames in the table above):

`https://raw.githubusercontent.com/Project-LeVeL-ExE/LeVeL-ExE-Security/main/<FILE>`

If you publish lists under a different path (e.g. `lists/` or `dist/`), update the pattern accordingly.

### Formats

| Format | Extension | Compatible With |
|---|---|---|
| **Raw** | `.txt` | Pi-hole, NextDNS, custom scripts, any plain-domain importer |
| **Hosts** | `.txt` | System hosts files, Pi-hole, hostfile-based blockers |
| **AdGuard** | `.txt` | AdGuard Home, AdGuard DNS, AdGuard browser extension |
| **NextDNS** | `.txt` | NextDNS custom denylist/allowlist import |
| **Unbound** | `.conf` | Unbound DNS resolver (`local-zone` directives) |
| **RPZ** | `.rpz` | BIND, Unbound RPZ, PowerDNS (Response Policy Zone format) |

---

## Installation & Usage

### Pi-hole

1. Open Pi-hole Admin → **Adlists**
2. Add the raw URL of the desired list from this repository
3. Run `pihole -g` to update gravity

### AdGuard Home

1. Open AdGuard Home → **Filters** → **DNS Blocklists**
2. Click **Add blocklist** → **Add a custom list**
3. Paste the raw URL of the AdGuard-format list

### NextDNS

1. Log in to [NextDNS](https://nextdns.io)
2. Go to **Denylist** → **Add a list**
3. Paste the raw URL of the desired list
4. For the whitelist: add under **Allowlist** instead



### Apple (macOS / iOS / iPadOS)

- **iOS / iPadOS**: prefer a profile-based resolver (e.g. NextDNS or AdGuard DNS) and import the desired *Raw* list URL in the provider dashboard.
- **macOS**: you can either:
  - use the same resolver profile approach, or
  - run a local resolver (e.g. Unbound) and point macOS to it.

If you run **Unbound locally** on macOS:
1. Install Unbound (e.g. via Homebrew)
2. Include the generated `.conf` list as shown in the Unbound section
3. Point macOS DNS to `127.0.0.1` (or to your LAN resolver) via **System Settings → Network → DNS**.
### Unbound

Add to your Unbound configuration:
```
include: "/path/to/LeVeL-ExE-DNS-Blocklist-Complete.conf"
```

### BIND / RPZ

Configure as an RPZ zone in your BIND `named.conf`:
```
response-policy {
    zone "level-exe.rpz" policy nxdomain;
};
```

---

## Intelligence Sources

We do not trust any single source. Confidence is built through **multi-source corroboration** across reputable, diversified channels:

**IOC & Threat Intelligence**: abuse.ch (ThreatFox, URLhaus, MalwareBazaar, Feodo Tracker, SSLBL), Shadowserver Foundation, Spamhaus, MISP/CIRCL, AlienVault OTX, OpenCTI, C2IntelFeeds, C2-Tracker, AbuseIPDB, blocklist.de, Cybercrime Tracker, PhishHunt, VirusTotal.

**CERT/CSIRT Advisories**: CISA (including KEV), NCSC UK, CERT-EU, CERT-FR/ANSSI, CERT.PL, ENISA, CIRCL, BSI.

**Spyware & Surveillance Research**: Citizen Lab, Amnesty Tech/Security Lab, Access Now, EFF, Coalition Against Stalkerware.

**Phishing & Fraud Datasets**: PhishTank, OpenPhish, APWG, Google Safe Browsing.

**Vendor Threat Research**: Cisco Talos, Unit 42, Microsoft MSTIC, Google TAG/GTIG (Mandiant), CrowdStrike, ESET, Kaspersky, Check Point, Fortinet, Trend Micro, Sophos X-Ops, Proofpoint, IBM X-Force, SentinelOne, Rapid7, Sekoia.io, Group-IB, Recorded Future (Insikt Group), SOCRadar.

**Privacy & Anti-Tracking Context**: WebKit ITP, Mozilla ETP, Princeton CITP, IAB Tech Lab.

---

## Transparency & Privacy Commitment

LeVeL-ExE is built on a foundation of radical transparency:

- **Open source** under GNU GPLv3 — every entry is auditable by anyone.
- **Weekly change logs** document every addition, removal, and reclassification with technical motivation.
- **No data collection**: we do not collect, store, or process any user data. We do not log DNS queries. We do not track who uses our lists. Zero telemetry, zero analytics, zero profiling.
- **Future applications**: if and when LeVeL-ExE expands into apps or services, the same commitment applies — any data that needs to be stored will be stored **locally on the user's device**, never on our servers. We will never collect logs, usage patterns, or behavioral data.

We build tools to protect people from surveillance — we refuse to become surveillance ourselves.

---

## Full Manifesto

For the complete story behind LeVeL-ExE — including the personal experience that inspired it, the full technical taxonomy, the detailed workflow, and the complete list of intelligence sources — read our **[Manifesto & Technical Appendix](MANIFESTO.md)**.

---

## Contributing

We welcome contributions from the security community:

- **Report false positives**: if a legitimate domain is being blocked, open an issue
- **Submit IOCs**: if you have technically corroborated indicators that fit our philosophy, submit them via pull request or issue
- **Report false negatives**: if a known malicious domain is missing, let us know

All contributions are reviewed against our methodology before inclusion.

---

## License

This project is licensed under the **GNU General Public License v3.0 or later** — see [LICENSE](LICENSE). The full license text is provided in [COPYING](COPYING). Trademark usage is covered in [TRADEMARK.md](TRADEMARK.md).

Copyright (C) 2026 Guglielmo Patrucco

---

<div align="center">

**LeVeL-ExE** — *Because the internet should be safe for everyone.*

https://level-exe.com · project@level-exe.com

</div>