# Code Review: findDupicateProductForProductCleanup

**Method:** `findDupicateProductForProductCleanup(long siteId, long fingerprintId, Boolean manufacturersAreEqual, String fingerprintColumn, String pagination)`  
**Returns:** `Flux<DuplicateProduct>`  
**Review date:** July 20, 2026  
**Tool:** Cursor AI (Week 1 / Day 2 practice)

---

## What the method does

1. Resolve tenant from Reactor context (fallback to `AppTenantContext` if null or `ra_hi_rtl`)
2. Require non-blank `fingerprintColumn`
3. Build JOIN clause from fingerprint (+ manufacturer equality flag)
4. Run `COUNT(*)` once (Mono + `.cache()`)
5. Run SELECT of duplicate product pairs (Flux)
6. Attach `totalCount` to each emitted `DuplicateProduct`

**Business rule:** pairs where products share fingerprint metadata, same site (`owner_id`), `p1.product_id < p2.product_id`, and not present in `product_duplicate_ignore`.

---

## Flow

```text
deferContextual
  → resolve tenant
  → normalize fingerprint (null/blank → error)
  → buildJoinClause
  → count SQL (cached Mono)
  → data SQL + pagination
  → SET search_path TO tenant, ra_hi_rtl
  → map rows → DuplicateProduct
  → concatMap + setTotalCount
