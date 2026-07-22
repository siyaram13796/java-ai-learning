
prompts/cheat-sheet.md
# AI Prompt Cheat Sheet — Java Developer
Reusable prompts for daily work. Copy, paste code, review AI output before applying.
---
## 1. Explain (onboarding)
```text
Explain this Java method like I'm onboarding: risks, edge cases, and how to test it.
Use when: New codebase, legacy code, handoff, before changing something risky.

2. Refactor (readability)
Refactor for readability without changing behavior. Keep Java 17 style.
Use when: Method is hard to read but works. Always review diff before commit.

3. Tests (JUnit 5)
Generate JUnit 5 tests: happy path, nulls, boundaries.
Use when: Adding coverage, documenting behavior, before refactor.

4. Security / quality review
Find possible NPE, race conditions, and security issues in this code.
Use when: Before PR, production bugs, batch/concurrent code.

5. Debug
This method throws [exception]. Here is the stack trace: [paste]. What are the most likely causes and how do I verify each?
6. Documentation
Write a short JavaDoc and a plain-English summary for this class. Include preconditions and side effects.
7. API / contract
What is the implicit contract of this method (inputs, return values, errors)? List what callers must handle.
8. Performance
Review this code for unnecessary DB calls, parsing in loops, and thread-safety issues. Suggest minimal fixes only.
9. PR description
Summarize this change for a GitLab MR: what changed, why, risks, and test plan. Use conventional commit style.
10. Interview prep

What interview questions could an interviewer ask about this code? Give brief model answers.






















Give me Day [N] practice schedule for my 90-day Java AI roadmap.

Context:
- Audience: Java developer (~5 years), learning AI with Spring + Ollama
- Project: demoAI at D:\demo1\demoAI
- Port: 8180
- Completed so far: Day 1 to Day [N-1]
- Yesterday I finished: [short summary, e.g. ticket classifier /classify]
- Today I want focus: [choose one]
  A) Work-code AI prompts (explain/refactor/security/tests)
  B) demoAI feature practice (classifier/RAG/memory/etc.)
  C) Concepts + interview questions only

Please include:
1. Time-boxed schedule (total ~2 hours)
2. Exact practice steps
3. What NOT to do today
4. Success checklist
5. GitHub files to create/update (with paste-ready content)
6. 3–5 practice questions with blank answers for my notes
