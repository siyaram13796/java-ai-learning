# Day 4 — July 20, 2026

## Goal
Deepen demoAI experiments: latency, temperature, hallucination, embeddings.

**Project:** `D:\demo1\demoAI` (Spring AI + Ollama)  
**Port:** 8189

---

## Done today

- [ ] Latency logging on `/ask` (or notes of manual timing)
- [ ] Temperature experiment: `0` vs `0.8`
- [ ] Hallucination hunt: 3 `/movie` titles checked on IMDb/Google
- [ ] Similarity pairs tested via `/similarity`
- [ ] (Optional) Memory test with `/remember`

---

## Practice 1 — Latency

Prompt used: `What is a token in LLMs? Answer in 2 sentences.`

| Run | Latency (ms) | Notes |
|-----|--------------|-------|
| 1 | _______ | |
| 2 | _______ | |
| 3 | _______ | |

**Average latency:** _______ ms  

**Observation:** (e.g. 2nd call faster / model warm / CPU slow)

---

## Practice 2 — Temperature

Endpoint: `/movie?genre=comedy`

| Temperature | Run 1 title | Run 2 title | Run 3 title | Same or different? |
|-------------|-------------|-------------|-------------|-------------------|
| 0 | | | | |
| 0.8 | | | | |

**Learned:**
- Temperature **0** → more ________________
- Temperature **0.8** → more ________________
- Use low temperature for: classification / JSON / stable answers
- Use higher temperature for: creative writing / brainstorming

---

## Practice 3 — Hallucination hunt

Endpoint: `/movie?genre=action` (prefer temperature 0.8)

| Title | Year (from JSON) | Real? (IMDb/Google) | Notes |
|-------|------------------|---------------------|-------|
| | | ✅ / ❌ | |
| | | ✅ / ❌ | |
| | | ✅ / ❌ | |

**One-line lesson:**
```text
Hallucination: the model generates plausible text; it does not query a movie database.
/movie can invent titles that look real in JSON.
