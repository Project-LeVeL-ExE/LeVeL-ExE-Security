<div align="center">

# 🛡️ LeVeL-ExE — Manifesto & Technical Appendix

**"Digital Peace, by Design"**

*Security, Trust, and the Restoration of Digital Serenity*

</div>

---

## Part I — The Story: When Security Becomes Personal

> *"LeVeL-ExE was not born from a trend or a marketing idea. It was born from a moment when technology stopped feeling like a tool — and started feeling like a threat."*

---

### 1. Where This Began

About a year ago, the creator of this project experienced a sophisticated cyberattack. Not the kind that shows up as a single alert, a single compromised password, or a single "virus" you remove and forget. This was layered, deliberate, and engineered to undermine both systems and certainty.

The attack unfolded in distinct phases:

**Phase 1 — Network Poisoning & Isolation**

The attacker executed systematic **DNS hijacking** followed by **DNS cache poisoning**, forcing traffic through adversary-controlled exit nodes (Adversary-in-the-Middle). Every attempt to download security tools or access support forums was redirected to malicious mirrors. The result: complete digital isolation.

**Phase 2 — Deep Persistence (Firmware & OS Level)**

Post-exploitation privilege escalation led to the installation of a **rootkit with firmware-level persistence** — tampering with Preboot volumes and system configuration files (`.plist`). The malware survived full OS reinstallation, executing malicious LaunchDaemons on every boot through manipulation of the boot chain.

**Phase 3 — Synthetic Identity & Exfiltration**

Instead of targeting passwords (protected by MFA), the attack cloned the entire digital identity through **session hijacking and token theft** — exfiltrating session cookies and local certificates. The result: complete account access without triggering any two-factor authentication alerts, leading to full identity cloning across cloud and local environments.

### 2. The Lesson Learned

At that point, the damage was not only technical. It became psychological. You start questioning what is real, what is trusted, and what is safe. It is a form of digital trauma — and it is far more common than most people realize, because many victims never even learn what happened.

The attack demonstrated a fundamental truth: **DNS is the first point of failure and the last point of defense.** If you cannot trust name resolution, you cannot trust anything built above it.

From that experience came a simple, urgent intention:

> **Build a DNS-level blocklist that reduces everyday exposure to hostile infrastructure — so that less experienced users don't have to learn security "the hard way."**

### 3. Who This Manifesto Speaks To

This document is written for everyone:

- **If you are not technical**, you should find empathy here — because you deserve safety without having to become a security engineer. You deserve to browse the internet, check your email, and manage your banking without an invisible infrastructure working to compromise, track, or profile you.

- **If you are technical**, you should find method here — because trust is rebuilt through rigor, transparency, and operational discipline. Every claim in this document is backed by a verifiable process.

---

## Part II — Why DNS-Level Protection Matters

### For Everyone

Most users do not study DNS. Many don't even know what DNS is. And yet DNS sits at the most critical junction of every digital interaction: it translates human-readable addresses into machine-readable destinations. Every website, every app connection, every system update begins with a DNS query.

In a world of constant connectivity — work, identity, banking, health, family, communication — being online is no longer optional. In that reality, a **resilient DNS filtering layer** becomes a foundational control: not the only defense, but often the **first meaningful one** that quietly reduces exposure every day.

### For Technical Readers

DNS filtering is a practical, measurable, deployable defense that:

- reduces contact with malicious infrastructure (phishing, malware delivery, C2, botnets) before it reaches the browser or endpoint
- reduces privacy erosion (tracking, profiling, surveillance-style collection) at the network level
- operates transparently across all devices on a network without per-device configuration
- does so **without turning the internet into a censored, curated experience**

LeVeL-ExE uses **network indicators** — domains, FQDNs, URLs, IPs, name servers, certificates — as an intermediate defensive layer that is specific enough to minimize collateral damage and central enough to be applied effectively across DNS, proxy, firewall, and gateway environments.

---

## Part III — Core Values: Protection Without Censorship

### A) We Do NOT Build Censorship

We do not implement:
- geographic censorship
- political censorship
- blocking based on editorial nature of content
- blocking of categories (adult, gambling, etc.) simply because of what they are

**User choice matters. Autonomy matters.** We promote integration, understanding, and progress — not restriction.

### B) We DO Build Risk Reduction

Our philosophy is to block **anything that can plausibly place the user, their device, or their privacy at risk** — based on technical indicators and corroboration, not ideology.

### C) "No Breakage" Is a Design Goal

We aim to block the harmful **without breaking** what people rely on: websites, platforms, apps, login flows, payment systems, OS updates. That requires discipline, granularity, and reversibility.

> *"Security that breaks everyday life is not security — it's a denial of service against the user."*

---

## Part IV — What Makes LeVeL-ExE Different

A "big list" is easy to publish. A **defensible** list is hard to maintain.

### Precision Over Quantity
We prefer narrow, attributable indicators — specific hosts, subdomains, URLs/paths, IP:port combinations — over broad blocks that create collateral damage. We will never block a root domain like `google.com` even though dozens of its subdomains are trackers in our lists.

### Verifiability
Every block must be defensible with a technical rationale (category) and a corroboration signal (observation, correlation, advisory/report, IOC source). If we cannot verify it, we do not include it.

### Reversibility
Indicators change: reassignment, sinkholes, takedowns, remediation. Any entry can be removed or reclassified quickly when context changes. Our methodology is built for correction, not permanence.

### Compatibility
We block what harms users **without breaking the normal web**. Before promoting any entry, we evaluate potential impact on login flows, payment APIs, OS update mechanisms, app stores, and common CDNs.

### Transparency
Weekly change logs document every addition, removal, and reclassification with technical motivation. The entire list is open source and auditable by anyone.

---

## Part V — Threat Scope: What We Block

We block indicators that, with reasonable certainty, represent:

### Malware Infrastructure
- Malware distribution: droppers, payload hosting, exploit delivery
- Loader and second-stage staging
- RAT/infostealer panels and exfiltration endpoints
- Badware hosting: bulletproof panels, exploit kit hosting, payload CDNs

### Command-and-Control (C2) & Botnet Infrastructure
- Active controller endpoints
- Fast-flux/double-flux patterns (where corroborated)
- Proxy/relay layers masking C2 traffic
- DGA-generated domains observed as active (campaign-specific)
- IRC-based C2 infrastructure

### Phishing & Fraud Operations
- Credential harvesting, brand impersonation
- Phishing kit hosting, panels, redirectors
- QR phishing chains, vishing infrastructure
- AiTM-style workflows (when documented)
- Investment scams, romance scam infrastructure, tech support scams
- Typosquatting and combosquatting

### Network Attack Infrastructure
- DNS hijack and cache poisoning infrastructure
- Rootkit C2 and firmware persistence endpoints
- Router/edge compromise endpoints
- Ransomware C2, negotiation infrastructure, leak sites

### Invasive Tracking & Surveillance-Style Collection
- Cross-site tracking, pixels/beacons, attribution endpoints
- Session replay collection endpoints
- Fingerprinting endpoints (canvas/audio/WebGL/font/device graph)
- Tag management and ad-exchange/RTB infrastructure
- Telemetry endpoints exceeding operational necessity (OS, app, AI, Apple, SmartTV)

### Surveillance Infrastructure
- Mercenary spyware clusters: Pegasus (NSO Group), Predator (Intellexa), Hermit (RCS Lab), FinFisher — infection/C2/zero-click delivery infrastructure when publicly documented
- Government surveillance: vendor infrastructure, lawful intercept abuse, military offensive infrastructure (when technically verifiable)
- Data broker infrastructure, stalkerware panels

### Emerging Abuse Patterns
- AI/GenAI offensive infrastructure (FraudGPT, deepfake delivery, AI phishing kits, LLM-as-C2)
- Supply-chain compromise infrastructure (package typosquatting, update hijack, dependency staging)
- MFA bypass infrastructure (AiTM reverse proxies, OTP harvesting panels)
- Java class-loading abuse (JNDI/RMI injection hosts, malicious class servers)

---

## Part VI — What We Do NOT Do (Hard Lines)

To remain usable, defensible, and aligned with user freedom:

- We do **not** perform content filtering, geoblocking, or political blocking
- We do **not** block adult/gambling categories as categories
- We do **not** block root domains of major shared providers/CDNs/PaaS
- We do **not** block legitimate tools unless specific IOCs of abuse exist
- We do **not** turn the list into "deny all"
- We do **not** include entries without technical corroboration
- We do **not** silently modify existing indicators without operator approval

---

## Part VII — Complete Taxonomy

### Category Architecture

The LeVeL-ExE blocklist is organized into four macro-categories, each containing purpose-driven subcategories:

#### TRACKERS & SURVEILLANCE
| Subcategory | Scope |
|---|---|
| Advertising | ad-exchange, ad-network, in-app-ads, retargeting |
| Tracking | analytics-metrics, attribution-affiliate, link-decoration, pixels-beacons, session-replay, tag-management |
| Fingerprinting | behavioral-profiling, device-graph, fingerprint-scripts |
| Telemetry | app-telemetry, crash-reporting, os-telemetry, smart-device-telemetry |
| AI Telemetry | sdk-telemetry, web-collector, model-usage-metrics |
| Apple Telemetry | ads-measurement, diagnostics, in-app-tracking |
| SmartTV Telemetry | acr-collection, ctv-adtech, device-analytics |
| Government Surveillance | data-broker-infra, vendor-infrastructure, military-offensive-infra, lawful-intercept-abuse |
| Surveillance Spyware | infection-infra, mercenary-spyware, zero-click-delivery, forensic-indicators |
| Stalkerware | stalkerware-panels |

#### MALWARE & VIRUS
| Subcategory | Scope |
|---|---|
| Malware | droppers, infostealer, loaders, rat |
| Badware Hoster | bulletproof-panels, exploit-kit-hosting, payload-cdn |
| Malware Distribution | general malware distribution infrastructure |

#### NETWORK ATTACKS
| Subcategory | Scope |
|---|---|
| Botnet | c2-domains, fast-flux, proxy-relay, dga-seeds, irc-c2 |
| DNS Hijack & Rootkit | dns-hijack, dns-cache-poisoning, rootkit-c2, router-compromise, firmware-implant-infra |
| RAT Remote Control | exfil-endpoints, rat-c2 |
| Ransomware C2 | negotiation-infra, staging-download, affiliate-infra, leak-site-infra |
| Threat Intelligence | takedown-artifacts |
| DynDNS Abuse | dynamic-c2 |
| Abuse Infrastructure | abuse-infra, TDS/redirectors |

#### PHISHING & FRAUD
| Subcategory | Scope |
|---|---|
| Phishing | brand-impersonation, credential-harvest, shortener-abuse, qr-phishing, kit-hosting, vishing-infra |
| Social Engineering | investment-scam, romance-scam-infra, tech-support-scam |
| DynDNS Abuse | dynamic-phish |
| Scam & Impersonation | scam-infrastructure, typosquatting-combosquatting |

#### HIGH-EVIDENCE EMERGING CATEGORIES
| Category | Subcategories | Operational Note |
|---|---|---|
| AI/GenAI Abuse | llm-as-c2, fraudgpt-infra, deepfake-delivery, ai-phishing-kit, genai-malware-staging | Do NOT block legitimate AI provider APIs |
| Supply-Chain Compromise | package-typosquatting, update-hijack, dependency-staging, oauth-abuse-infra, build-pipeline-infra | Extremely high FP risk — strong corroboration required |
| MFA Bypass Infra | aitm-proxy, otp-harvest-panel, session-relay, sim-swap-web | Do NOT block legitimate MFA providers |
| Java Class Hijack | jndi-injection-host, malicious-class-server, java-deserial-c2, webstart-abuse | High specificity — CERT/vendor IOC required |

---

## Part VIII — Intelligence Sources & Cross-Validation

We do not treat any single source as truth. Confidence is built through **multi-source corroboration**:

### IOC & Threat Intelligence Portals
abuse.ch (ThreatFox, URLhaus, MalwareBazaar, Feodo Tracker, SSLBL) · Shadowserver Foundation · Spamhaus · MISP/CIRCL · AlienVault OTX · OpenCTI · C2IntelFeeds · C2-Tracker · AbuseIPDB · blocklist.de · Cybercrime Tracker · PhishHunt · VirusTotal · Bert-JanP Open Source Threat Intel Feeds

### CERT/CSIRT & Government Advisories
CISA (including KEV) · NCSC UK · CERT-EU · CERT-FR/ANSSI · CERT.PL · ENISA · CIRCL (Luxembourg) · BSI (Germany)

### Spyware & Surveillance Research
Citizen Lab · Amnesty Tech / Security Lab · Access Now · EFF · Coalition Against Stalkerware

### Phishing & Fraud Datasets
PhishTank · OpenPhish · APWG · Google Safe Browsing · Zscaler ThreatLabz

### Vendor Threat Research (with IOC appendices)
Cisco Talos · Palo Alto Unit 42 · Microsoft MSTIC · Google TAG/GTIG (Mandiant) · CrowdStrike · ESET · Kaspersky · Check Point · Fortinet FortiGuard Labs · Trend Micro · Sophos X-Ops · Proofpoint · IBM X-Force · SentinelOne · Rapid7 · Sekoia.io · Group-IB · Recorded Future (Insikt Group) · SOCRadar

### Privacy & Anti-Tracking Context
WebKit ITP · Mozilla ETP · Princeton CITP · IAB Tech Lab

---

## Part IX — Workflow: From Ingest to Publication

### 1. Ingest
- Candidates collected from advisories, reports (PDF/HTML), IOC portals (API/JSON/STIX), forensic investigations, and verified submissions
- Normalization: lowercase, punycode decode, trailing dot removal, FQDN extraction, URL parsing, non-indicator query parameter stripping

### 2. Technical Validation
- DNS resolution checks (A/AAAA/CNAME/NS behavior)
- Shared-hosting risk assessment — high collateral risk triggers granularity reduction to FQDN/URL
- Corroboration minimum: at least one "strong" source (CERT-tier, vendor report with explicit IOCs) **or** multiple aligned "moderate" signals
- Surveillance/spyware indicators require explicit forensic/STIX/IOC-table evidence

### 3. Classification
- Each indicator mapped to category/subcategory based on technical role
- Ambiguity resolution: choose the most specific category; if not classifiable with confidence, exclude

### 4. Safety & Compatibility Checks
- Do not block major provider root domains
- Evaluate potential breakage: login flows, payments, OS updates, app stores, CDNs
- Higher corroboration thresholds for volatile categories (GenAI abuse, MFA bypass, supply chain, Java class abuse)

### 5. Output, Logging & Lifecycle
- Category-separated outputs + consolidated complete list
- Weekly change log with technical motivation for every change
- Differentiated retention: volatile indicators (fast-flux, DGA) → weekly recheck; stable indicators → monthly recheck
- Six format outputs: Raw, Hosts, AdGuard, NextDNS, Unbound, RPZ
- No deduplication against existing curated list during ingest

---

## Part X — Current Scale

| List | Entries |
|---|---:|
| LeVeL-ExE DNS Blocklist — Complete | 6,662,174 |
| LeVeL-ExE DNS Blocklist — Trackers & Surveillance | 3,160,308 |
| LeVeL-ExE DNS Blocklist — Network Attacks | 1,077,097 |
| LeVeL-ExE DNS Blocklist — Phishing & Fraud | 1,011,341 |
| LeVeL-ExE DNS Blocklist — Malware & Virus | 203,923 |
| LeVeL-ExE DNS Blocklist — IP | 164,673 |
| LeVeL-ExE DNS Whitelist | 112,294 |
| **Total** | **12,391,810** |

Each indicator is subjected to in-depth review with the goal of maximizing effectiveness while minimizing disruption.

---

## Part XI — Promises & Commitments

### What We Claim (Because It Is Measurable)
- We reduce attack surface in a way that is deployable for real users
- We protect privacy without turning protection into censorship
- We maintain compatibility as a core engineering constraint
- We operate with a methodology that allows correction, reclassification, and continuous improvement

### What We Refuse to Promise
We do **not** claim to be a definitive solution. No blocklist can honestly promise that. Threat infrastructure evolves faster than any static defense.

### Our Privacy Commitment
- We collect **zero** user data — no logs, no analytics, no telemetry, no profiling
- If LeVeL-ExE expands into apps or services, any data that needs to be stored will remain **on the user's device** — never on our servers
- We build tools to protect people from surveillance — we refuse to become surveillance ourselves

---

## Part XII — A Final Human Note

Security is often discussed like an abstract technical domain. For real people, it is not abstract.

When your identity is cloned, when systems behave unpredictably, when you realize you've been watched or manipulated — the damage is not only technical. It's personal. It's psychological. It's a violation of trust that extends far beyond any single device or account.

LeVeL-ExE exists to reduce that probability for everyone — especially those who don't have the time or expertise to recognize danger early.

It is built to be a first line of defense and a durable standard of care:

> **Protect users. Protect privacy. Preserve freedom. Avoid breakage. Stay verifiable. Stay reversible.**

The goal is not to "control the internet." The goal is to restore **digital peace**: a future where people can stay connected without constantly feeling at risk, and where trust in digital technology can be rebuilt — step by step, through defensible work.

---

<div align="center">

*LeVeL-ExE — Because the internet should be safe for everyone.*

**Guglielmo Patrucco** · [https://level-exe.com](https://level-exe.com) · [project@level-exe.com](mailto:project@level-exe.com)

Copyright (C) 2026 · GNU General Public License v3.0 or later

</div>
