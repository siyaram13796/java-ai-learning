# Day 11 — July 24, 2026

## Goal
Cache FAQ embeddings so each request does not re-embed all FAQs.

**Project:** `D:\demo1\demoAI` · Port 8180

---

## Done today
- [ ] Cached FAQ vectors at startup / first use
- [ ] findTopFaqMatches uses cache
- [ ] Compared latency before vs after
- [ ] Confirmed faq-answer + score threshold still work

---

## Latency results

| Run | Before (ms) | After (ms) |
|-----|-------------|------------|
| 1 | | |
| 2 | | |
| 3 | | |

**Observation:**

---

## Practice question answers

### 1. Why is embedding FAQs on every request wasteful?
Answer:



### 2. What do we cache, and what do we still compute per request?
Answer:



### 3. When must we rebuild the FAQ cache?
Answer:



### 4. How does caching relate to a real vector DB (pgvector)?
Answer:



### 5. Does caching change answer quality? Why or why not?
Answer:



---

## Learned today
- 
- 

## Tomorrow (Day 12)
- [ ] Focus A: work-code AI practice on one method
- [ ] OR add simple score in /faq-search response docs + interview prep

## One-line summary
Day 11 complete: cached FAQ embeddings for faster retrieval without changing RAG quality.
