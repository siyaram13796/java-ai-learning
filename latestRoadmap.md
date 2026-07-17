# 90-Day AI Learning Roadmap for Java Developers

**Audience:** Java developers with ~5 years experience  
**Goal:** Become an AI-ready Java engineer who can ship RAG/chat features in Spring apps, use AI tools daily, and clear AI-related interviews.  
**Last updated:** July 2026

---

## Table of Contents

1. [Overview](#1-overview)
2. [Phase 0 — Setup](#2-phase-0--setup-day-1–2)
3. [Month 1 — AI Fluency + LLM Fundamentals](#3-month-1--ai-fluency--llm-fundamentals)
4. [Month 2 — Build Real AI Features in Java](#4-month-2--build-real-ai-features-in-java)
5. [Month 3 — Cloud, Security, System Design](#5-month-3--cloud-security-system-design)
6. [Portfolio Projects](#6-portfolio-projects)
7. [Time Budget](#7-time-budget)
8. [Learning Resources](#8-learning-resources)
9. [Interview Question Bank](#9-interview-question-bank)
10. [Resume Bullets](#10-resume-bullets)
11. [Success Checkpoints](#11-success-checkpoints)
12. [Learning Order](#12-learning-order)
13. [Progress Tracker](#13-progress-tracker)

---

## 1. Overview

### What you already have
- Strong Java fundamentals
- Backend / Spring experience
- Production problem-solving skills

### What you will add
| Skill | Why it matters |
|-------|----------------|
| AI coding assistants | Immediate productivity boost |
| LLM APIs from Java | Core integration skill |
| Embeddings + RAG | Most common enterprise AI pattern |
| Spring AI / LangChain4j | Java-native AI frameworks |
| Agents + tool calling | Next-level AI features |
| Cloud AI + security | Production readiness |
| AI system design | Senior / interview level |

### What not to over-invest in early
- Deep ML math
- Training models from scratch
- Every new AI framework

---

## 2. Phase 0 — Setup (Day 1–2)

### Checklist
- [ ] Install **Cursor** (or GitHub Copilot + IntelliJ)
- [ ] Create accounts: OpenAI / Azure OpenAI / Groq (free tiers help)
- [ ] Create GitHub repo: `java-ai-learning`
- [ ] Pick one cloud: **Azure** (enterprise Java friendly) or **AWS Bedrock**

### Daily habit (entire 90 days)
| Activity | Duration |
|----------|----------|
| Focused learning | 60–90 min |
| Use AI on real work code | 30 min |
| Notes: learned / failed / retry | 5–10 lines |

---

## 3. Month 1 — AI Fluency + LLM Fundamentals

### Week 1: Become AI-native at work

**Learn**
- Prompt patterns: explain, debug, refactor, generate tests, write docs
- How to review AI code (null checks, security, edge cases, complexity)

**Practice**
- [ ] Refactor one old Java class with AI
- [ ] Generate JUnit 5 tests for a service
- [ ] Ask AI to explain a complex method in your current project

**Output**
- Personal **prompt cheat sheet** (10 reusable prompts)

**Sample prompts to save**
```text
Explain this Java method like I'm onboarding: risks, edge cases, and how to test it.
Refactor this service for readability without changing behavior. Keep Java 17 style.
Generate JUnit 5 tests with happy path, nulls, and boundary cases.
Find possible NPE, race conditions, and security issues in this code.
```

---

### Week 2: How LLMs work (practical)

**Learn**
- Tokens, context window, temperature
- Chat vs completion APIs
- System vs user prompts
- Hallucinations and why they happen

**Practice**
- [ ] Call OpenAI (or compatible) API from a tiny Java main class
- [ ] Log: prompt tokens, completion tokens, latency

**Output**
- `hello-llm` Java mini project

**Key concepts to write in your notes**
| Term | Meaning |
|------|---------|
| Token | Unit of text the model reads/writes |
| Context window | Max tokens the model can see at once |
| Temperature | Randomness of output (0 = deterministic) |
| Hallucination | Confident but incorrect answer |

---

### Week 3: Prompt engineering for backend use cases

**Learn**
- Structured output (JSON mode / schema)
- Few-shot prompting
- Tool/function calling concept
- Guardrails: “answer only from context”

**Practice**
- [ ] Build: Support ticket classifier (text → category + priority JSON)
- [ ] Add retries + timeout + error handling

**Output**
- `ticket-classifier` Spring Boot endpoint: `POST /classify`

**Example response contract**
```json
{
  "category": "BILLING",
  "priority": "HIGH",
  "confidence": 0.86,
  "reason": "Customer mentions double charge and urgent refund"
}
```

---

### Week 4: Embeddings + similarity search

**Learn**
- What embeddings are
- Cosine similarity
- Chunking basics
- Why a vector DB is needed

**Practice**
- [ ] Embed 20 FAQs
- [ ] Retrieve top-3 similar FAQs for a user question
- [ ] Start in-memory (List + cosine), then optionally pgvector

**Output**
- `faq-search` demo (retrieval only, no LLM generation yet)

---

## 4. Month 2 — Build Real AI Features in Java

### Week 5: Spring AI or LangChain4j basics

**Pick one**
- **Spring AI** — if you live in Spring Boot
- **LangChain4j** — if you want more framework-agnostic control

**Learn**
- ChatClient / AiServices
- Prompt templates
- Advisors / memory basics

**Practice**
- [ ] Chat endpoint with conversation memory (in-memory)
- [ ] Switch model provider via config

**Output**
- `spring-ai-chat` service

---

### Week 6: RAG end-to-end (core skill)

**Architecture**
```text
Docs (PDF/MD)
   → Chunk text
   → Create embeddings
   → Store in vector DB
   → Retrieve relevant chunks
   → Generate answer with citations
```

**Suggested stack**
- Java 17+, Spring Boot 3
- Spring AI or LangChain4j
- PostgreSQL + pgvector (or OpenSearch)
- Local files or S3 for docs

**Practice**
- [ ] Ingest 5–10 internal-style docs
- [ ] Ask questions and return answer + source snippets

**Output**
- `company-docs-rag` (**Portfolio Project #1**)

---

### Week 7: Make RAG production-ish

**Implement**
- [ ] Chunk size / overlap tuning
- [ ] Metadata filters (department, product, date)
- [ ] Prompt rule: use only context; say “I don’t know” when unsure
- [ ] Cache frequent queries
- [ ] Basic evaluation set (20 Q&A pairs)

**Also add**
- Request logging: user query, retrieved docs, tokens, cost estimate

**Output**
- README with architecture diagram + eval results table

---

### Week 8: Agents + tools (practical)

**Learn**
- Tool / function calling
- When to use agent vs plain RAG
- Multi-step flows and failure handling

**Practice**
- Agent that can:
  - [ ] Search docs
  - [ ] Call Java method: `getOrderStatus(orderId)`
  - [ ] Summarize result

**Output**
- `support-agent` demo (**Portfolio Project #2**)

---

## 5. Month 3 — Cloud, Security, System Design

### Week 9: Cloud AI integration

**Learn one path deeply**
- Azure OpenAI + Azure AI Search, or
- AWS Bedrock + OpenSearch, or
- GCP Vertex AI

**Practice**
- [ ] Move RAG app from local API keys to cloud-managed model
- [ ] Externalize config (env vars, secrets)
- [ ] Add rate limiting

**Output**
- Deployed demo (Docker Compose is enough)

---

### Week 10: Reliability, cost, security

**Must-know for senior Java roles**
- Timeouts, circuit breaker, fallback
- Token / cost budgets
- PII redaction before sending to LLM
- Prompt injection basics
- AuthZ: who can ask what

**Practice**
- [ ] Add Resilience4j (or similar)
- [ ] Block prompts that ask for secrets
- [ ] Mask emails / phone numbers in logs

**Output**
- Security & ops checklist in your repo

---

### Week 11: System design for AI features

**Design drills (write answers for each)**
- [ ] Customer-support copilot
- [ ] Document Q&A for 10M pages
- [ ] AI code review assistant for PRs
- [ ] Fraud alert summarizer for transactions

**Cover in each design**
- Latency budget
- Cost model
- Retrieval quality
- Human-in-the-loop
- Observability

---

### Week 12: Portfolio + interview polish

**Ship**
- [ ] Clean README, architecture, demo video (5–8 min)
- [ ] 2 projects live on GitHub
- [ ] One-page “AI skills” bullets for LinkedIn / resume

**Interview prep topics**
- RAG vs fine-tuning
- Chunking tradeoffs
- Embedding model choice
- Hallucination mitigation
- Adding AI to an existing Spring microservice
- Cost / latency tradeoffs
- Java-specific: sync vs async AI calls, thread pools, backpressure

---

## 6. Portfolio Projects

### Project 1: Internal Docs RAG Assistant
**Features**
- Upload PDF / Markdown
- Ask questions
- Get answer + citations
- Admin page to re-index

**Why it matters**
- Covers the most common enterprise AI use case

### Project 2: Customer Support Copilot
**Features**
- Classify ticket
- Retrieve policy docs
- Suggest reply
- Call tool for order status
- Human approve before send

**Why it matters**
- Shows RAG + tools + workflow judgment

These two cover ~80% of enterprise AI interview expectations.

---

## 7. Time Budget

| Activity | Time / week |
|----------|-------------|
| Concepts + docs | 4–5 hrs |
| Coding projects | 6–8 hrs |
| AI-assisted daily work practice | 2–3 hrs |
| Notes / LinkedIn learning post | 1 hr |
| **Total** | **~13–17 hrs** |

**Busy schedule option:** Slow track = 6 months (each week over 2 calendar weeks).

---

## 8. Learning Resources

### Official docs (prefer these)
| Topic | Resource |
|-------|----------|
| Spring AI | https://docs.spring.io/spring-ai/reference/ |
| LangChain4j | https://docs.langchain4j.dev/ |
| OpenAI API | https://platform.openai.com/docs |
| Azure OpenAI | https://learn.microsoft.com/azure/ai-services/openai/ |
| AWS Bedrock | https://docs.aws.amazon.com/bedrock/ |
| pgvector | https://github.com/pgvector/pgvector |

### Concepts to search / study
- “RAG retrieval augmented generation”
- “text embeddings cosine similarity”
- “prompt injection OWASP LLM”
- “hybrid search keyword + vector”
- “LLM evaluation faithfulness groundedness”

### Java practice stack
- Java 17+
- Spring Boot 3
- Maven or Gradle
- PostgreSQL + pgvector
- Docker Compose
- JUnit 5
- Resilience4j

---

## 9. Interview Question Bank

Practice from Week 8 onward.

1. What is RAG and when would you **not** use it?
2. How do you reduce hallucinations in production?
3. How do you choose chunk size and overlap?
4. Embeddings vs keyword search — when do you combine both (hybrid)?
5. How do you secure PII with third-party LLMs?
6. How would you add AI search to an existing Java monolith safely?
7. How do you estimate monthly LLM cost for 1M queries?
8. Sync API vs async queue for LLM calls — when each?
9. How do you evaluate answer quality continuously?
10. Fine-tuning vs prompt engineering vs RAG — decision framework?
11. What is prompt injection and how do you mitigate it?
12. How do you design fallbacks when the LLM / vector DB is down?
13. How would you version prompts and measure regressions?
14. What observability metrics matter for an AI feature?
15. How do you prevent an agent from calling unsafe tools?

---

## 10. Resume Bullets

After 90 days, you should be able to write:

- Built a Spring Boot RAG service with embeddings + vector search and citation-based answers
- Integrated LLM APIs with retries, cost tracking, and structured JSON outputs
- Implemented tool-calling agent for support workflows (docs + order lookup)
- Added evaluation set and reduced hallucination rate through prompt + retrieval tuning

---

## 11. Success Checkpoints

| Milestone | Target |
|-----------|--------|
| **Day 30** | Call LLMs from Java; explain tokens & embeddings |
| **Day 60** | Working RAG app with citations |
| **Day 90** | Design + defend an enterprise AI feature end-to-end |

---

## 12. Learning Order

Follow this sequence (do not jump around):

1. AI coding assistant mastery  
2. LLM API from Java  
3. Embeddings  
4. RAG  
5. Spring AI / LangChain4j  
6. Tools / agents  
7. Cloud + security + evals  
8. System design + interviews  

---

## 13. Progress Tracker

Copy this section into your notes and tick weekly.

### Month 1
- [ ] Week 1 — AI-native work + prompt cheat sheet
- [ ] Week 2 — `hello-llm`
- [ ] Week 3 — `ticket-classifier`
- [ ] Week 4 — `faq-search`

### Month 2
- [ ] Week 5 — `spring-ai-chat`
- [ ] Week 6 — `company-docs-rag` (v1)
- [ ] Week 7 — RAG production hardening + evals
- [ ] Week 8 — `support-agent`

### Month 3
- [ ] Week 9 — Cloud deploy
- [ ] Week 10 — Security / reliability / cost controls
- [ ] Week 11 — 4 system design writeups
- [ ] Week 12 — Portfolio polish + interview prep

### Final ship checklist
- [ ] 2 GitHub projects with README + architecture
- [ ] Demo video (5–8 min)
- [ ] Resume / LinkedIn AI skills updated
- [ ] Can answer interview bank confidently

---

## Quick Reference — Suggested Weekly Outcomes

| Week | Project / Artifact |
|------|--------------------|
| 1 | Prompt cheat sheet |
| 2 | `hello-llm` |
| 3 | `ticket-classifier` |
| 4 | `faq-search` |
| 5 | `spring-ai-chat` |
| 6 | `company-docs-rag` |
| 7 | Eval report + hardened RAG |
| 8 | `support-agent` |
| 9 | Cloud-deployed demo |
| 10 | Security & ops checklist |
| 11 | AI system design notes |
| 12 | Portfolio + interview ready |

---

## Next Steps

1. Complete Phase 0 setup today  
2. Start Week 1 prompt practice  
3. Create GitHub repo `java-ai-learning`  
4. Optionally scaffold Week 2 `hello-llm` project structure  

---

*This document is a personal learning plan for Java developers adopting AI skills for enterprise backend roles.*
