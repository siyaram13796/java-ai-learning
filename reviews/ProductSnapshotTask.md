# Code Review: ProductSnapshotTask.insert()

**File:** `com.rw.mws.task.v1.ProductSnapshotTask`  
**Method:** `insert(ProductSnapshot pojo, boolean checkExisting)`  
**Review date:** July 17, 2026  
**Tool:** Cursor AI (Week 1 practice)

---

## What the method does

1. Trims whitespace on the POJO
2. Optionally checks for an existing product snapshot (batch optimization)
3. Inserts a new row if no duplicate (or if check is disabled)
4. Returns new snapshot ID, or **`-1`** if insert was skipped

---

## Flow

```text
trim(pojo)
  → if checkExisting AND schema != ra_rentals_rtl
      → lookup existing by product/collection/soldBy rules
      → if duplicate → skip insert
  → if inserting → convert POJO, clear PK, insert, return ID
  → else → return -1
