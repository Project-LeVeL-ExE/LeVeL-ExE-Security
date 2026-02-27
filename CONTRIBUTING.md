# Contributing

Thanks for helping improve LeVeL-ExE. Contributions are welcome, but must align with the project philosophy:
- **Precision over quantity**
- **Verifiability**
- **Reversibility**
- **Compatibility / No breakage**
- **No censorship**

## What we accept

- **False positive reports** (legitimate domains blocked)
- **IOC submissions** (malware/phishing/C2/tracker/surveillance infrastructure)
- **Reclassification** requests (category adjustments with evidence)
- **Quality improvements** (dedupe, formatting, consistency)

## Evidence requirements (verifiability)

For each domain/FQDN you propose to add or keep:
- Provide **at least one strong source** (CERT/CSIRT advisory, vendor research with explicit IOCs, forensic report), OR
- Provide **multiple aligned moderate signals** (reputable TI feeds / independent reports)

Submissions without verifiable rationale may be rejected.

## Precision rules (avoid collateral damage)

- Prefer **FQDNs / specific hosts** over broad domains
- Avoid blocking **root domains** of major CDNs, hosting, PaaS, or critical providers unless the root domain is conclusively malicious
- Avoid wildcard patterns unless the target format explicitly supports it and impact is understood

## How to submit

### Option A — Issue (recommended for most users)
Open an issue using the templates:
- False positive
- False negative / IOC submission

### Option B — Pull Request
1. Fork the repo
2. Create a feature branch
3. Apply changes (keep formatting consistent with existing lists)
4. Include evidence in the PR description (links + short rationale)
5. Open the PR

## Data you should include (minimal checklist)

- Domain / FQDN
- Category (and why)
- Evidence links (sources)
- Date observed / last seen (if known)
- Confidence level (low/medium/high)
- Potential breakage notes (if any)

## License for contributions

By submitting a contribution, you agree it is licensed under **GPL-3.0-or-later** (see LICENSE / COPYING) and that you have the right to submit it.
