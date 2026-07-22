# Day 9 — July 22, 2026

## Goal
Build RAG-lite: retrieve top FAQ matches, then generate an answer **only from that context**.

**Project:** `D:\demo1\demoAI`  
**Port:** 8180  
**Endpoints:** `/faq-search` (Day 8), `/faq-answer` (Day 9)

---

## Done today

- [ ] Added `GET /faq-answer?question=...`
- [ ] Reused top-3 retrieval from FAQ embeddings
- [ ] Prompt rule: answer only from context / say "I don't know"
- [ ] Returned answer + source FAQs
- [ ] Tested in-scope + out-of-scope questions

---

## Flow

```text
question
  → embed + top-3 FAQ matches
  → build context
  → LLM generate answer from context only
  → return answer + sources











  Test results
Question	Answer summary	Said "I don't know"?	Sources OK?
forgot password
get refund
app crashes
pizza recipe
wrong tax
Practice question answers
1. What is RAG in one sentence?
Answer:

2. Why must the LLM answer only from retrieved context?
Answer:

3. What is the difference between /faq-search and /faq-answer?
Answer:

4. What happens if retrieval is wrong but generation still runs?
Answer:

5. When would you still say "I don't know" even if top-3 returned something?
Answer:

Learned today
Tried / stuck
