# Introduction to the OWASP Top 10:2025
The OWASP Top 10 is now in its 8th edition since the project began, and the 2025 release marks the first substantial reshuffling of the list in several years. As always, the document exists to give developers, architects, and security teams a shared, prioritized view of the application security risks that matter most right now. It is not an exhaustive taxonomy, but a starting point for where to focus limited time and budget.

## What changed for 2025
1. The headline change is structural: two **brand-new categories** enter the list, and **one long-standing category gets folded** into another.
2. **Server-Side Request Forgery,** which had its own entry in 2021, is now treated as a symptom of the broader access-control problem and has been absorbed into Broken Access Control.
3. On the other end, **Software Supply Chain Failures** expands what used to be "Vulnerable and Outdated Components" into a much wider concern covering build systems, CI/CD pipelines, and distribution infrastructure, not just outdated libraries.
4. **Mishandling of Exceptional Conditions** is an entirely new category, carved out of what used to be lumped in with generic "poor code quality," covering error handling, failing open, and logic that breaks down under unexpected states.
5. **Position-wise, Broken Access Control keeps the #1 spot** it has held since 2021, with essentially every tested application showing at least one related weakness. Security Misconfiguration jumps from #5 to #2, reflecting how much of modern application behavior is now driven by configuration rather than code.
6. **Cryptographic Failures and Injection** each slide two spots (to #4 and #5), and Insecure Design drops from #4 to #6 as the two newly prominent categories overtake it. This is a trend the authors read as a sign that threat modeling and secure-design practices have genuinely improved industry-wide.
7. **Authentication Failures** holds #7 with a name tweak for clarity, Software or Data Integrity Failures holds #8, and Security Logging and Alerting Failures holds #9, again propelled onto the list partly by community vote rather than raw test data.

## Methodology in brief
The ranking process blends two inputs. Eight of the ten categories are selected and ranked using contributed testing data. Organizations donated results covering roughly 2.8 million applications, mapped against 589 Common Weakness Enumerations (CWEs), up from around 400 in 2021. For each CWE, the team combines an incidence rate (what share of tested applications showed the weakness), a coverage figure (how much of the population was actually tested for it), and average exploitability and impact scores pulled from CVSS data in the National Vulnerability Database. The other two category slots come from a community survey, because some serious risks (like insecure design or missing logging) are inherently hard to detect through automated testing and would otherwise be invisible in the data, even though practitioners on the ground know they matter.

Categories in 2025 also contain far more CWEs each than earlier editions did, averaging around 25 per category (capped at 40), because the team chose to group by root cause rather than by symptom wherever practical. That is a deliberate trade-off: broader categories are less precise, but they let the list generalize better across languages and frameworks that don't all share the same specific weaknesses.

## Acknowledgment
*The 2025 edition draws on data donated by more than a dozen organizations*, including Veracode, Contrast Security, Sonar, Semgrep, Bugcrowd, Orca Security, and several anonymous contributors, and was compiled by lead authors Andrew van der Stock, Brian Glas, Neil Smithline, Tanya Janca, and Torsten Gigler.

## Source
[OWASP Top 10:2025 – Introduction](https://owasp.org/Top10/2025/0x00_2025-Introduction/)
