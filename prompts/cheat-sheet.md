
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
