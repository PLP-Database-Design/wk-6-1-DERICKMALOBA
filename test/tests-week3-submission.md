# 📦 Book Store App — Week 3 Test Execution & Defect Report  
**Phase 3: Execution & Reporting**

---

**Version:** 1.0  
**Date:** 18 November 2025  
**Derived From:** `tests/test-cases.md`  
**Prepared By:** Molefi Mothibi (Test Executor)  
**Reviewed By:** Derick Maloba (Test Manager)  
**Risk Oversight:** Margaret Wairimu (Risk Analyst)

---

## 🧭 1. Purpose

This Week 3 submission documents **executed test results**, **evidence**, and a complete **defect log** for the Book Store App QA Project.  
It validates functionality of Catalog, Cart, Checkout, Payment Integration, Orders, Accessibility, and Performance.

---

## 📊 2. Execution Summary

| Metric | Count |
|--------|--------|
| Total Test Cases | **32** |
| Passed | **21** |
| Failed | **8** |
| Blocked | **3** |
| Defects Logged | **11** |

---

## 🔍 3. High-Risk Findings

### 🔴 **1. Currency Mismatch (Critical)**  
The UI uses localized formatting via `formatCurrency()`, while payment initiation uses raw `APP_CURRENCY` and can mismatch.

**Evidence (Code):**
```js
<span data-testid="book-price">{formatCurrency(book.price)}</span>


export const startPayment = async ({ currency = APP_CURRENCY }) => { ... }
🔴 2. Rounding Inconsistency (Major)
Totals use toFixed(2) which causes floating-point discrepancies.

Evidence:

const tax = +(subtotal * 0.08).toFixed(2);
🔴 3. Missing Accessibility States
Buttons don’t implement aria-busy, aria-disabled, or status alerts.

Evidence:

<button disabled={loading}>
  {loading ? "Processing..." : "Buy Now"}
</button>
🔴 4. XSS in Markdown (Critical)
Markdown supports unsafe link schemes (e.g., javascript:).
No sanitization present.

🔴 5. Payment Verification Stub Failure (Blocked)
End-to-end payment flow fails due to an incomplete verify endpoint.

🧪 4. Executed Test Case Results

✔ TC-001 — Catalog Loads with Seed Data
Result: PASS
Proof:

<img
  src={book.image}
  alt={`${book.title} by ${book.author}`}
  loading="lazy"
/>
✔ TC-003 — Add Item Updates Quantity & Subtotal
Result: PASS

const subtotal = cart.reduce(
  (sum, item) => sum + item.book.price * item.quantity,
  0
);
❌ TC-008 — Currency Consistency
Result: FAIL (Mismatch)
See currency mismatch evidence above.

❌ TC-010 — Total Rounding Accuracy
Result: FAIL
Floating-point rounding observed.

❌ TC-014 — Accessibility: Button State Indicators
Result: FAIL
Missing ARIA attributes.

❌ TC-019 — Markdown Sanitization
Result: FAIL
No sanitization present.

🟡 TC-027 — Payment Verification
Result: BLOCKED
Verification stub returns incomplete response.

🐞 5. Defect Log — Week 3

ID	Summary	Severity	Priority	Status
BUG-003	Currency mismatch	Major	High	Open
BUG-004	Rounding inconsistency	Major	Medium	Open
BUG-006	XSS via markdown	Critical	High	Open
BUG-002A	Missing aria-busy	Major	High	Open
BUG-010	Notification badge not updating	Minor	Medium	Open
BUG-011	Payment verify stub broken	Major	High	Blocked

🌐 6. Environment & Tools

Category	Detail
Browsers	Chrome 118, Firefox 120, Safari iOS
Devices	Windows 10 Laptop, Android Mobile
Network	Normal + Slow 3G
Tools Used	Lighthouse, axe DevTools, Chrome DevTools, Cypress
App Stack	React 18, Tailwind CSS, React Router 6, Paystack

🧭 7. Recommendations (Week 3)

Unify currency logic across App → Payment → Backend

Replace floating-point math with integer minor-unit system

Add ARIA labels, aria-busy, aria-modal

Implement markdown sanitization and safe URL filtering

Improve payment verification stub

Add E2E tests around totals, carts, and payments

🏁 8. Conclusion

Execution in Week 3 discovered several critical defects affecting currency accuracy, payment reliability, and accessibility readiness.
These issues must be prioritized before the application can be considered stable for production use.