
# 🧪 Book Store App QA Project — Final Report  
**Phase 4: Project Completion**

---

**Version:** 1.0  
**Date:** 18 November 2025  
**Prepared By:** Molefi Mothibi  
**Reviewed By:** Derick Maloba  
**Risk Analyst:** Margaret Wairimu  

---

## 🧭 1. Executive Summary

This Final Report summarizes QA activities across **Week 1 → Week 3** for the Book Store App.  
Testing achieved 100% functional requirement coverage across Catalog, Cart, Checkout, Payments, Orders, Accessibility, and Performance.

**Critical issues remain** in currency consistency, rounding behavior, accessibility compliance, and sanitization.  
These affect payment accuracy, UX validity, and WCAG compliance.

---

## 🗂️ 2. Test Approach

### ✔ Functional Testing  
Core features validated: Catalog → Cart → Checkout → Payment → Orders.

### ✔ Accessibility Testing  
WCAG 2.1 AA applied using axe/WAVE + manual keyboard navigation.

### ✔ Performance Testing  
- LCP  
- TTI  
- Lazy-load effectiveness  
Measured via Lighthouse under Slow 3G throttling.

### ✔ Compatibility  
Cross-browser testing on Chrome, Edge, Firefox, and Safari.

### ✔ Security & Input Validation  
Markdown sanitization  
Unsafe URL scheme filtering  
localStorage resilience

---

## 🌐 3. Test Environment

| Component | Details |
|-----------|----------|
| **Browsers** | Chrome 118, Edge 118, Firefox 120, Safari iOS |
| **Devices** | Windows 10 Laptop, Android Mobile |
| **Network** | Default + Slow 3G |
| **Tools** | Lighthouse, axe DevTools, Cypress, Chrome DevTools |
| **Stack** | React 18, Tailwind, Paystack, React Router |

---

## 🔗 4. Requirements Coverage

| FR Code | Requirement | Status |
|---------|-------------|---------|
| FR-O01 | Catalog & Discovery | ✔ Covered |
| FR-O02 | Cart & Checkout | ⚠ Partial — rounding issues |
| FR-O03 | Paystack Payment | ⚠ Partial — verify stub failing |
| FR-O04 | Orders History | ✔ |
| FR-O05 | CSV Export | ✔ |
| FR-X01 | Accessibility | ⚠ Missing aria-busy, aria-modal |
| FR-X02 | Performance | ⚠ LCP above 2.5s |
| FR-X03 | Multi-browser compatibility | ✔ |
| FR-S01 | Sanitization & Security | ✖ Missing |

---

## 📊 5. Final Execution Results

| Metric | Result |
|--------|---------|
| Total Test Cases | 32 |
| Passed | 21 |
| Failed | 8 |
| Blocked | 3 |
| Defects Logged (Total) | 11 |

---

## 🐞 6. Defect Analysis (Critical & High Severity)

### ❌ **BUG-003 — Currency Mismatch**

Evidence:
```js
formatCurrency(book.price)
startPayment({ currency: APP_CURRENCY })
❌ BUG-004 — Rounding Errors
Evidence:

const tax = +(subtotal * 0.08).toFixed(2);
❌ BUG-006 — XSS via Markdown
Unsafe schemes allowed, no sanitizer.

❌ BUG-002A — Missing aria-busy
Loading states not announced to assistive tech.

❌ BUG-011 — Payment Verify Stub Failure
Breaks E2E checkout.

♿ 7. Accessibility & Performance Findings

Accessibility Issues:
Missing ARIA attributes (aria-busy, aria-disabled, aria-modal)

Emoji icons lack screen-reader metadata

No focus-return or trapping in dialogs

Performance Metrics (Slow 3G):
LCP: ~3.8 seconds (Goal ≤ 2.5s)

TTI: ~4.2 seconds (Goal ≤ 3.5s)

Lazy-loading improved image jank but not enough to pass thresholds.

🛠️ 8. Recommendations

Functional
Use minor-unit integers for totals

Standardize currency

Fix notification badge state updates

Accessibility
Implement ARIA states

Improve modal structure

Add alt text for decorative icons

Security
Apply markdown sanitization

Validate URL schemes

Harden localStorage access

Performance
Preload LCP image

Optimize catalog images

Add skeleton loaders

🏁 9. Final Conclusion

The Book Store App demonstrates strong functionality in core areas.
However, critical issues in payments, accessibility, rounding accuracy, and sanitization prevent it from being production-ready.

The testing phase successfully identified these issues and provides clear recommendations for remediation.

Final QA Status: Requires Fixes Before Release