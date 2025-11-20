
# 📘 **Book Store App — Final Software Test Report**
**Document ID:** BS-TR-2025-003  
**Version:** 1.0  
**Date of Report:** November 18, 2025  
**Prepared By:** QA Team  
**Project:** Book Store App (React, Paystack Integration)

---

# 📝 **Executive Summary**

This final report summarizes the complete testing effort conducted on the **Book Store App** during Weeks 1–3.  
Testing focused on catalog functionality, cart and checkout flows, currency consistency, payment integration, accessibility, performance, and defect validation.

### **Key Findings**
- Multiple **high‑impact defects** identified (currency mismatch, rounding errors, A11y gaps, XSS vulnerability)
- Core catalog and cart functionality is stable across major browsers
- Payment flow is partially functional due to a failing verification stub
- Accessibility issues affect WCAG compliance (missing ARIA attributes, focus inconsistencies)
- LCP slightly above target on 3G throttling profiles

### **Recommendation**
Proceed with development fixes before release. Current version is **not ready for production** due to unresolved payment, security, and accessibility issues.

---

# 🎯 **1. Test Objective**

The main objectives of this testing cycle were to:

1. Validate that all implemented features function according to specifications  
2. Confirm that intentional defects are identified and documented  
3. Measure accessibility & performance against defined benchmarks  
4. Verify payment initiation flow (Paystack sandbox)  
5. Assess app stability under multiple environments and throttled networks  

Testing was carried out from **Nov 5 – Nov 18, 2025**.

---

# 🔍 **2. Areas Covered**

## 2.1 Functional Testing
- Catalog listing, search, sorting  
- Cart operations (add, remove, update)  
- Checkout page navigation  
- Currency formatting & totals  
- Order persistence in localStorage  
- Admin guard route  
- Paystack initiation behavior  

## 2.2 Non‑Functional Testing
- **Performance:** LCP, TTI, lazy-load validation  
- **Compatibility:** Chrome, Firefox, Edge, Safari Mobile  
- **Accessibility:** Labels, roles, aria-live, keyboard navigation  
- **Security:** Input validation, markdown sanitization gaps  

---

# 🛑 **3. Areas Not Covered**

- End-to-end payment verification (stub incomplete)  
- Real server-side APIs  
- Advanced Return/Refund workflow  
- Admin console CRUD operations  
- Deep link navigation  

---

# 🧪 **4. Testing Approach**

### **4.1 Test Strategy**
A combined strategy was used:

- **Risk‑based testing** focused on payment, totals, accessibility  
- **Black‑box techniques:** EP, BVA, Decision Tables  
- **Exploratory testing** for cart and checkout transitions  
- **Regression testing** after Week 3 defects  

### **4.2 Testing Process**
1. **Planning** – Requirements analysis, FR mapping  
2. **Test Design** – Test cases drafted (Week 2)  
3. **Execution** – Week 3 manual execution  
4. **Defect Logging** – Documented with IDs and evidence  
5. **Reporting & Finalization** – Consolidated into this report  

### **4.3 Tools Used**
- Jira / GitHub Projects  
- Chrome DevTools (Performance + Network)  
- Lighthouse  
- axe DevTools  
- Local React Dev Server  

---

# 🧩 **5. Key Test Cases (Sample)**

### **TC‑PAY‑001 — Paystack Payment Initiation**
**Preconditions:** Cart has items  
**Steps:** Click "Buy Now" → Proceed to Paystack  
**Expected:** Payment window loads with correct currency  
**Actual:** Currency mismatch (ZAR vs UI format)  
**Status:** ❌ FAIL

### **TC‑CART‑004 — Quantity Updates**
**Steps:** Update item quantity in cart  
**Expected:** Subtotal updates correctly  
**Actual:** Correct  
**Status:** ✅ PASS

### **TC‑A11Y‑003 — Button Loading State**
**Expected:** Buttons reflect `aria-busy="true"`  
**Actual:** Missing attribute  
**Status:** ❌ FAIL

---

# 🐞 **6. Defect Summary**

| Severity | Count | Closed | Open |
|----------|--------|---------|-------|
| Critical | 1 | 0 | 1 |
| High | 4 | 1 | 3 |
| Medium | 3 | 1 | 2 |
| Low | 3 | 2 | 1 |
| **Total** | **11** | **4** | **7** |

### **6.1 Critical Defect**
#### **BUG‑006 — XSS via Markdown (Critical)**
Markdown allows `javascript:` injection.  
**Status:** OPEN  
**Risk:** High — Security vulnerability.

---

# 📊 **7. Overall Status**

### **7.1 Execution Metrics**
- **Test cases planned:** 32  
- **Executed:** 32  
- **Pass rate:** 65%  
- **Blocked:** 3 (Payment verification)  

### **7.2 Quality Assessment**
| Area | Status | Notes |
|-------|---------|--------|
| Catalog | ✓ Stable | No major issues |
| Cart | ✓ Stable | Subtotals consistent |
| Checkout | ⚠ Partial | Missing validation messages |
| Payment | ❌ Fail | Currency + verification issues |
| Accessibility | ❌ Fail | Missing ARIA attributes |
| Performance | ⚠ Partial | LCP slightly above threshold |

---

# ⚠️ **7.3 Risk Assessment**

| Risk | Impact | Status |
|------|---------|---------|
| Currency mismatch | High | Open |
| Rounding inaccuracies | Medium | Open |
| XSS markdown exploit | High | Open |
| Missing A11y compliance | Medium | Open |
| Payment verification incomplete | High | Blocker |

---

# 🚀 **7.4 Final Release Recommendation**

**NOT RECOMMENDED FOR RELEASE**  
The current build contains unresolved critical and high-severity defects — particularly in **payment reliability**, **security**, and **accessibility**.

**Conditions before release:**
1. Fix currency mismatch across UI and backend  
2. Implement markdown sanitization  
3. Add ARIA attributes to interactive components  
4. Complete payment verification handler  
5. Re-run regression + A11y audit  

---

# 📎 **8. Appendices**

### **8.1 Test Case Execution Details**
Provided in `/tests/test-cases.md`.

### **8.2 Defect Log**
See `/tests/defect-log.md`.

### **8.3 Performance Metrics**
Lighthouse JSON results available upon request.

### **8.4 Evidence**
## Code Snippets

### 1. Currency Mismatch Evidence
```javascript
// UI formatting
{formatCurrency(book.price)}
```

```javascript
// Payment layer using different currency source
export const startPayment = async ({ currency = APP_CURRENCY }) => { ... }
```

### 2. Rounding Issue Evidence
```javascript
const tax = +(subtotal * 0.08).toFixed(2);
```

### 3. Missing aria-busy Evidence
```jsx
<button disabled={loading}>
  {loading ? "Processing..." : "Buy Now"}
</button>
```

# 📝 **9. Approvals**

| Role | Name | Approval |
|-------|--------|-----------|
| **Test Manager** | Derick Maloba | Pending |
| **Risk Analyst** | Margaret Wairimu | Pending |
| **Test Executor** | Molefi Mothibi | Pending |

---

# ✅ **End of Test Report**
