# Synthesis: Establishing a Modern Application Security Program

The Top 10 is an awareness document, not a full program. If a program already exists, benchmark it with **OWASP SAMM** or **DSOMM**.
If starting from zero (or SAMM/DSOMM feels like too much right now), follow the five-step foundation below.

## 5 foundational steps

1. **Risk-based portfolio approach**: Inventory apps/APIs, rate them by business impact and privacy/regulatory exposure, feed results into a CMDB, define assurance levels per tier.
2. **Strong foundation**: Baseline security policies, a reusable set of standard controls, role-targeted security training.
3. **Integrate security into existing processes**: Threat modeling, secure design review, secure coding, code review, pentesting, remediation are added to the SDLC that already exists, not bolted on separately.
4. **AppSec education**: Security champions program, OWASP Juice Shop / WebGoat for hands-on practice, OWASP conferences and local chapters.
5. **Management visibility**: Manage by metrics (defect density, coverage, time-to-fix); mine root causes from testing data to drive systemic fixes, not just point patches.

## Repeatable process, phase by phase

| SDLC phase | Key actions |
|---|---|
| Requirements & resourcing | Define confidentiality/integrity/availability needs with the business; use **ASVS** to set concrete security requirements; budget for security activities explicitly |
| RFP / contracting | Negotiate security requirements and SLAs with vendors/devs; consider the OWASP Secure Software Contract Annex |
| Planning & design | Threat modeling (OWASP Threat Modeling Cheat Sheet), design security in rather than retrofitting it, use OWASP Cheat Sheets / Proactive Controls |
| Secure development | SAMM-guided process, secure coding training, code review, SAST/SCA/secrets/IaC scanners, secure defaults ("paved roads"); notably, OWASP now recommends giving developers a **private AI backed by a RAG server of vetted security docs and an MCP server wired to your security tooling** |
| Continuous testing | Use/abuse test cases, DAST/fuzzing, pentests and load testing for high-assurance systems |
| Rollout | Finalize CMDB and architecture docs before go-live |
| Operations & change mgmt | Patch management, logging/monitoring/alerting, regular hardening and pentests, incident response team, supply-chain hardening, BC/DR planning |
| Retirement | Archive required data, securely wipe the rest, revoke accounts/roles, mark retired in the CMDB |

## Using the Top 10 as a standard (with caveats)

The Top 10 has been used as a de facto industry standard since 2003, but OWASP is explicit that it's a **bare minimum**, not a comprehensive one, so several risks (e.g., Insecure Design, or verifying real logging/incident-response effectiveness) resist automated testing entirely.
For anything beyond baseline awareness (like coding standards, code review checklists, unit/integration testing, secure supply chain) OWASP points to the **Application Security Verification Standard (ASVS)** instead. This is which is designed to be verifiable and is the only standard OWASP considers acceptable for tool vendors to claim compliance against.

## Source

[Establishing a Modern Application Security Program (OWASP Top 10:2025)](https://owasp.org/Top10/2025/0x03_2025-Establishing_a_Modern_Application_Security_Program/)
