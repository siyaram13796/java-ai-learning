# Day 8 — July 22, 2026

## Goal
Start Week 4 skill early: **FAQ search with embeddings** (retrieval only, no LLM answer).

**Project:** `D:\demo1\demoAI`  
**Port:** 8180  
**Endpoints:** `/similarity` (existing), `/faq-search` (new)

---

## Done today

- [ ] Added in-memory FAQ list (10 items)
- [ ] Added `GET /faq-search?question=...`
- [ ] Returns top 3 matches with cosine similarity score
- [ ] Tested 5 questions + 1 nonsense question

---

## Flow learned

```text
question → embed → compare with each FAQ embedding → sort by score → top 3


Test results
User question	Top FAQ match	Score	Correct?
forgot password
payment failed money deducted
app keeps crashing
where is documentation
wrong tax on invoice
pizza (nonsense)
Practice question answers
1. What is the difference between /classify and /faq-search?
Answer:

2. What is cosine similarity in one sentence?
Answer:

3. Why return top-3 instead of only top-1?
Answer:

4. Why is FAQ search not full RAG yet?
Answer:

5. What can go wrong with embedding search on nonsense input?
Answer:

Learned today
Tried / stuck
Tomorrow (Day 9)

 Add /faq-answer — LLM answers only from top-3 FAQ context

 OR Track A: work-code AI review on one method
