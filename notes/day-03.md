# Day 3 — July 20, 2026

## Goal
Call a local LLM from Java, test Spring AI endpoints, and learn core LLM concepts.

---

## Done today

- [x] Used existing project **demoAI** (`D:\demo1\demoAI`) instead of plain `hello-llm`
- [x] Stack: Spring Boot 3.3 + Spring AI + Ollama
- [x] Configured Ollama model: `llama3.2`
- [x] Embedding model: `mxbai-embed-large` (for `/embed`, `/similarity`)
- [x] Tested endpoints (fill in after you run):
  - [ ] `/ask?message=...`
  - [ ] `/translate?text=Hello&language=Hindi`
  - [ ] `/movie?genre=comedy`
  - [ ] `/remember?message=...&sessionId=s1`
  - [ ] `/embed?text=hello`
  - [ ] `/similarity?text1=cat&text2=kitten`

---

## Project: demoAI

**Port:** 8189  
**Run:**
```bash
cd D:\demo1\demoAI
mvn spring-boot:run
