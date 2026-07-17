# Day 1 — July 17, 2026

## Goal
Phase 0 setup + Week 1: first AI practice on real Java code.

---

## Done today

- [x] Logged into GitHub
- [x] Created repo `java-ai-learning`
- [x] Used Cursor on real code: `ProductSnapshotTask.insert()`
- [x] Completed 4 prompt exercises:
  1. Explain method (onboarding)
  2. Refactor for readability
  3. Generate JUnit 5 tests
  4. NPE / race / security review

---

## Learned

- `insert(ProductSnapshot, checkExisting)` optionally skips insert if a duplicate snapshot exists
- Returns **`-1`** when insert is skipped (duplicate found)
- Duplicate lookup depends on **`soldBy`**:
  - `null` → query by product + collection only
  - `""` → query with empty soldBy + fulfilledBy
  - non-empty → full match including soldBy + fulfilledBy
- Schema **`ra_rentals_rtl`** skips duplicate check entirely
- Callers use `updateLastKnownSnapshot()` which already ignores `-1`

---

## Risks found (ProductSnapshotTask)

| Risk | Type |
|------|------|
| Null `pojo`, product, or collection | NPE |
| Null `schemaName` from JPA | NPE on `toLowerCase()` |
| Check-then-insert without lock | Race → duplicate rows |
| Non-numeric product/collection IDs | NumberFormatException |
| Inconsistent soldBy duplicate rules | Logic / data duplicates |

---

## Tried / stuck

- Legacy `mws` project uses **JUnit 3.8**, not JUnit 5
- Generated JUnit 5 tests need Mockito + new dependencies OR go in this learning repo first
- Chose **Ollama** (free local LLM) instead of paid OpenAI/Groq for now

---

## Tomorrow (Day 2)

- [ ] Install Ollama + run `ollama pull llama3.2`
- [ ] Add 2–3 more prompts to cheat sheet (aim for 10 total)
- [ ] Practice same 4 prompts on **another** Java class
- [ ] Optional: 4th prompt on a different method in same file

---

## Time spent
~2–3 hours (setup + 4 AI exercises)

---

## One-line summary
Day 1 complete: I can use AI to explain, refactor, test, and review legacy Java safely.
