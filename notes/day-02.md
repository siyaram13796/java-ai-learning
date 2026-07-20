# Day 2 — July 20, 2026

## Goal
Continue Week 1: practice the same 4 AI prompts on a **new** Java method, and prepare Ollama for Week 2.

---

## Done today

- [x] Practiced 4 prompts on `findDupicateProductForProductCleanup`
  1. Explain (onboarding)
  2. Refactor for readability
  3. NPE / race / security (SQL injection, tenant, pagination)
  4. JUnit 5 + StepVerifier tests
- [ ] Ollama installed + model pulled (`llama3.2` or `llama3.2:1b`)
- [x] Cheat sheet still at ~10 prompts (from Day 1)
- [x] Review notes saved under `reviews/`

---

## Method practiced

**Name:** `findDupicateProductForProductCleanup(siteId, fingerprintId, manufacturersAreEqual, fingerprintColumn, pagination)`  
**Returns:** `Flux<DuplicateProduct>`  
**Stack:** Reactor + R2DBC, multi-tenant `search_path`

---

## Learned

- Reactive duplicate finder: resolve tenant → validate fingerprint → count once (cached) → stream pairs → attach `totalCount`
- `fingerprintId` parameter is **unused** (API smell)
- Method name typo: `Dupicate` (missing `l`)
- Biggest risks are **string-built SQL**:
  - tenant in `SET search_path TO ...`
  - raw `pagination` appended to SQL
  - fingerprint column used in JOIN (must be allowlisted)
- Pagination without `ORDER BY` can skip/duplicate rows across pages
- Mixing Reactor `TenantContext` + `AppTenantContext` ThreadLocal is risky under reactive schedulers
- Prefer `StepVerifier` for `Flux`/`Mono` tests

---

## Risks found (summary)

| Risk | Severity |
|------|----------|
| Tenant concatenated into `SET search_path` | Critical |
| Raw pagination string appended to SQL | Critical |
| Fingerprint column not clearly allowlisted | High |
| Silent tenant fallback / ThreadLocal in reactive | High |
| No ORDER BY with pagination | Medium |
| Unbounded LIMIT (DoS) | Medium |
| Count vs data query drift | Low–Medium |

---

## Tried / stuck

- Full R2DBC mocking is brittle — better to unit-test validation helpers + use Testcontainers later
- Ollama install status: _______________ (fill in)

---

## Tomorrow (Day 3)

- [ ] Finish Ollama if not done
- [ ] Scaffold `projects/hello-llm`
- [ ] Call Ollama from a tiny Java main class (`http://localhost:11434`)
- [ ] Log latency (and tokens if available)

---

## Time spent
~2–2.5 hours

---

## One-line summary
Day 2 complete: applied the same AI workflow to a reactive SQL method and learned that string-built SQL (tenant + pagination) is the main production risk.
