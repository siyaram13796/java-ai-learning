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
