# Synthesis: What are Application Security Risks?

## Core ideas
* risk := function of threat agents, attack vectors, exploitability, likelihood of missing controls, technical impact, and business impact.
* The same vulnerability can be low-risk for one organization and critical for another.
* For example, a CMS bug matters less for a public blog than for a health records system.

## How categories are selected and ranked

- Continues the 2021 methodology: CVE-derived **Exploitability** and **Impact** scores (CVSSv2/v3) from the National Vulnerability Database, mapped to CWEs via OWASP Dependency Check.
- **~175k** CVE-to-CWE records analyzed (up from 125k in 2021); **643** unique CWEs with CVE mappings (up from 241).
- CVSSv4 was *not* used. Its scoring model no longer isolates Exploit/Impact sub-scores the way v2/v3 do.
- Formula: `(Max Incidence Rate % × 1000) + (Max Coverage % × 100) + (Avg Exploit × 10) + (Avg Impact × 20) + (Sum Occurrences / 10000) = Risk Score`
- Scores ranged from **621.60** (Broken Access Control, top) to **271.08** (Memory Management Errors, bottom of the ranked list).
- Open challenge flagged by the team: what counts as "one application" gets blurrier with microservices, complicating incidence-rate math going forward.

## Key data-factor definitions

| Term | Meaning |
|---|---|
| CWEs Mapped | Number of CWEs assigned to the category |
| Incidence Rate | % of tested applications with ≥1 instance of that CWE |
| Weighted Exploit / Impact | Normalized CVSS sub-scores, 10-pt scale |
| Coverage | % of applications actually tested for that CWE (higher = more reliable rate) |
| Total Occurrences | Count of applications found with the mapped CWEs |
| Total CVEs | CVEs in NVD mapped to the category's CWEs |

## Source
[What are Application Security Risks? (OWASP Top 10:2025)](https://owasp.org/Top10/2025/0x02_2025-What_are_Application_Security_Risks/)
