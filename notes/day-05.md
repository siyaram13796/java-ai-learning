# Day 5 — July 21, 2026

## Goal
Practice structured thinking with AI: work-code review **or** ticket classifier in demoAI.

**Track chosen:** A / B (circle one)

---

## Done today

### If Track A
- [ ] Explained one new Java method
- [ ] Refactored for readability
- [ ] Security / NPE / race review
- [ ] JUnit 5 test ideas
- [ ] Interview questions prompt
- [ ] Saved review under `reviews/`

**Method name:** _______________________________  
**Class:** _______________________________

### If Track B
- [ ] Added `/classify` (or similar) endpoint
- [ ] Structured JSON record (category, priority, confidence, reason)
- [ ] Tested 5 sample tickets
- [ ] Used temperature ~0 for more stable labels

---

## Practice question answers

### 1. What is structured output and why is it useful in Java backends?
Answer:



### 2. Why is JSON / schema better than free text for a classifier?
Answer:



### 3. What can go wrong if the LLM returns wrong category? (business risk)
Answer:



### 4. How would you reduce wrong classifications?
Answer:



### 5. When would you use Track A skills (code review prompts) at work this week?
Answer:



### Track B — ticket results (if applicable)

| # | Ticket text | Category | Priority | Correct? |
|---|-------------|----------|----------|----------|
| 1 | I was charged twice and need a refund today | | | |
| 2 | App crashes when I open settings | | | |
| 3 | How do I reset my password? | | | |
| 4 | Where is the user guide PDF? | | | |
| 5 | My invoice shows wrong tax for last month — urgent | | | |

### 6–7. Any wrong classifications? Why?
Answer:



---

## Learned today

- 
- 
- 

---

## Tried / stuck

- 
- 

---

## Tomorrow (Day 6)

- [ ] Continue classifier hardening (retries, null text, bad JSON) **OR**
- [ ] Another work-code review with prompt cheat sheet
- [ ] Optional: add confidence threshold — if low, return "NEEDS_HUMAN_REVIEW"

---

## Time spent
~2–2.5 hours

---

## One-line summary
Day 5 complete: practiced [work-code AI review / ticket classifier structured output] and answered structured-output interview-style questions.














Practice question answers
1. Why validate LLM output in Java, not only in the prompt?
Answer: Prompts guide the model, but the model can still return invalid/unexpected values. Java validation is a hard guardrail: remap bad categories/priorities, block empty input, and enforce business rules so the API stays safe even when the LLM is wrong.

2. Why is a confidence threshold useful?
Answer: Low confidence means the model is unsure. Auto-routing unsure tickets can send work to the wrong team. If confidence < 0.7, mark as NEEDS_HUMAN_REVIEW so a person decides.

3. What should happen for blank input — call LLM or fail fast?
Answer: Fail fast with HTTP 400. Blank text wastes time/CPU, can cause bad/hallucinated output, and is not a valid ticket. Do not call the LLM.

4. What’s the difference between prompt rules and code guardrails?
Answer:

Prompt rules = instructions to the model (“use only these categories”). Soft.
Code guardrails = Java checks after the response (validate labels, confidence gate, 400 on blank). Hard. Production AI needs both.
Learned today
Structured output alone is not enough — add Java-side validation
Confidence gates prevent blind trust in weak LLM answers
Local Ollama can OOM; smaller models (llama3.2:1b) keep practice working
Empty-input 400 is a good API design pattern
Tried / stuck
Ollama OOM with llama3.2 full model while Spring Boot was running
Fixed by switching to llama3.2:1b and freeing RAM
(Add more if needed)
