# Day 6 — July 22, 2026

## Goal
Harden `/classify` with Java guardrails: empty input check, label validation, confidence gate.

**Project:** `D:\demo1\demoAI`  
**Port:** 8180  
**Model:** `llama3.2:1b` (switched from `llama3.2` due to OOM)

---

## Done today

- [x] Hardened `/classify` in `AiController`
  - [x] Blank/null text → HTTP 400 (no LLM call)
  - [x] Validate category (BILLING/TECHNICAL/ACCOUNT/OTHER)
  - [x] Validate priority (LOW/MEDIUM/HIGH)
  - [x] confidence < 0.7 → `NEEDS_HUMAN_REVIEW`
  - [x] Latency logging for classify
- [ ] Retested sample tickets (fill after testing)
- [ ] Confirmed empty text returns 400
- [ ] Fixed Ollama OOM by using smaller model

---

## What we built (flow)

```text
Request text
  → if blank → 400 Bad Request
  → call Ollama (structured JSON)
  → Java guardrails:
       invalid category → OTHER
       invalid priority → MEDIUM
       low confidence → NEEDS_HUMAN_REVIEW
  → return safe TicketClassification
