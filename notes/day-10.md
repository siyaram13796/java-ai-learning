# Day 10 — July 23, 2026

## Goal
Harden FAQ RAG-lite with a **retrieval score threshold** so weak matches don't call the LLM.

**Project:** `D:\demo1\demoAI`  
**Port:** 8180  
**Endpoints:** `/faq-search`, `/faq-answer`

---

## Done today

- [ ] Added `FAQ_MIN_SCORE` (value: _______)
- [ ] `/faq-answer` skips LLM when top score < threshold
- [ ] Tuned threshold using `/faq-search` scores
- [ ] Verified in-scope answers still work
- [ ] Verified nonsense → "I don't know"

---

## Why this matters

```text
Bad retrieval + LLM = confident wrong answers
Score threshold = fail closed when context is weak



Threshold tuning table
Question	Top score	Above threshold?	Final answer
forgot password
refund
app crashes
pizza
hello world
wrong tax
Chosen FAQ_MIN_SCORE: _______

Practice question answers
1. Why can top-3 retrieval still be wrong?
Answer:

2. Why skip the LLM when similarity score is low?
Answer:

3. What happens if the threshold is too high?
Answer:

4. What happens if the threshold is too low?
Answer:

5. Prompt rules vs score threshold — how do they work together?
Answer:

Learned today
Tried / stuck
