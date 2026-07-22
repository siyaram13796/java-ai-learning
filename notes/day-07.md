# Day 7 — July 22, 2026

## Goal
Improve ticket classifier accuracy using **few-shot prompting** (examples in system prompt), while keeping Day 6 Java guardrails.

**Project:** `D:\demo1\demoAI`  
**Port:** 8180  
**Model:** `llama3.2:1b`

---

## Done today

- [ ] Added 3 few-shot examples to `/classify` system prompt
- [ ] Retested 5 tickets and compared to Day 6
- [ ] Confirmed empty text still returns HTTP 400
- [ ] Noted effect on ambiguous ticket (`help`)

---

## Few-shot vs zero-shot

| Style | Meaning |
|-------|---------|
| Zero-shot | Rules only (Day 5–6) |
| Few-shot | Rules + example tickets + expected JSON (Day 7) |

---

## Before / after results

| Ticket | Day 6 | Day 7 few-shot | Better? |
|--------|-------|----------------|---------|
| charged twice | | | |
| app crashes | | | |
| reset password | | | |
| user guide PDF | | | |
| invoice wrong tax urgent | | | |
| help | | | |

---

## Practice question answers

### 1. What is few-shot prompting?
Answer:



### 2. Why can examples improve classification more than rules alone?
Answer:



### 3. Can few-shot replace Java guardrails? Why or why not?
Answer:



### 4. When would you add more examples vs change temperature?
Answer:



### 5. What is one risk of putting many long examples in the prompt?
Answer:



---

## Learned today

- 
- 

---

## Tried / stuck

- 

---

## Tomorrow (Day 8)

- [ ] Start `faq-search` concepts (embeddings list + top-3 similar FAQs) in demoAI
- [ ] OR work-code AI prompt practice (Track A)

---

## Time spent
~2 hours

---

## One-line summary
Day 7 complete: added few-shot examples to /classify and compared accuracy vs Day 6 zero-shot rules.
