# Synthesis: Next Steps: On-the-Cusp Risks

The Top 10 is capped at ten by design. Three additional risks were seriously considered but didn't make the final cut. It's still worth tracking for mature programs, consultancies, or tool vendors extending coverage.

## X01:2025 — Lack of Application Resilience

Renamed from 2021's "Denial of Service" (that name described a symptom, not the root cause). Scored almost identically to A10:2025-Mishandling of Exceptional Conditions. **16 CWEs**, avg incidence 4.55%, avg impact 3.49.

- **Core issue:** systems that can't gracefully absorb stress, failure, or edge cases, like leading to outages, but also data corruption or security-control bypass.
- **Key CWEs:** CWE-400 (Uncontrolled Resource Consumption), CWE-409 (data amplification via compressed data), CWE-674 (Uncontrolled Recursion), CWE-835 (Infinite Loop).
- **Prevention highlights:** rate limits/quotas per operation, deny-by-default with rollback on error, async/non-blocking calls with timeouts, circuit breakers/bulkheads/graceful degradation, chaos engineering, proof-of-work challenges that scale with attacker suspicion, session timeouts.
- **Example attacks:** resource exhaustion (memory/disk/CPU/connections), fuzzed inputs breaking business logic, dependency/API takedown cascading into the app itself.

## X02:2025 — Memory Management Failures

Ranked lowest in both the community survey and the data. It is likely due because web apps now dominate over the C/C++-heavy desktop and systems software where this mostly bites. Despite having the **3rd-highest CVE count** of any candidate category. **24 CWEs**, avg impact 4.82 (higher than every ranked Top 10 category).

- **Core issue:** manual memory management mistakes (buffer overflows, use-after-free, uninitialized variables, off-by-one errors, etcetera) concentrated in non-memory-safe languages (C/C++), still common in legacy systems, firmware, and IoT.
- **Prevention highlights:** prefer memory-safe languages (Rust, Go, Java, C#, Python, Swift, Kotlin, JS) for new work; if stuck with unsafe languages, enable ASLR/DEP/SEHOP, use safe string libraries (safer functions like `strncpy` over `strcpy`), fuzz every input, fix all compiler warnings (not just errors), use stack canaries.
- **Example attacks:** classic buffer overflow overwriting the stack pointer; use-after-free in browser DOM handling redirecting execution to attacker data; format-string vulnerabilities from unsanitized input passed straight into logging calls.

## X03:2025 — Inappropriate Trust in AI-Generated Code ("Vibe Coding")

No CWEs or CVEs yet mapped (too new) but flagged because AI-generated code is documented to carry more vulnerabilities than human-written code, and "vibe coding" (committing AI output with minimal human review) is spreading fast.

- **Core issue:** the old risk of copy-pasting unvetted snippets from blogs, amplified, as AI models may be statistically starved of *good* secure examples to draw from.
- **Prevention highlights:** never commit code you don't fully understand: you're accountable for it regardless of who wrote it; review AI code with the same rigor as human code (manual review + SAST); write-then-let-AI-suggest rather than AI-writes-then-you-approve; feed AI a RAG server of your own vetted secure code and standards; consider an MCP server between IDE and AI that enforces your security tooling; avoid vibe coding entirely for complex, business-critical, or long-lived code; watch for **Shadow AI** usage outside sanctioned tools.

## Source
[Next Steps (OWASP Top 10:2025)](https://owasp.org/Top10/2025/X01_2025-Next_Steps/)
