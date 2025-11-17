# 🧪 **Book Store App QA Project — Test Plan (Phase 1: Planning & Setup)**

## 📘 Document Information
- **Project Name:** Book Store App  
- **Phase:** 1 — Planning & Setup  
- **Week:** 1 (Due: November 5, 2025)  
- **Version:** 1.0  
- **Date Prepared:** November 5, 2025  
- **Repository:**  

---

## 👥 **Team Roles & Responsibilities**

| Role | Team Member | Responsibilities |
|------|--------------|------------------|
| **Test Manager** | **Derick Maloba** | - Coordinate test plan & schedule<br>- Track progress & metrics<br>- Lead overall QA execution and reporting |
| **Risk Analyst** | **Margaret Wairimu** | - Identify and prioritize project risks<br>- Design test cases around high-risk areas<br>- Collaborate on mitigation strategies |
| **Test Executor** | **Molefi Mothibi** | - Execute manual test cases<br>- Log defects with clear evidence<br>- Validate and retest resolved issues |

---

## 🎯 **Objective and Scope**

### Objective
To ensure the **Book Store App** functions correctly, efficiently, and securely by verifying that all core features (catalog, cart, checkout, payment, and orders) meet the defined **functional and non-functional requirements**.

### Scope (Phase 1)
- Understand the application’s core modules and architecture  
- Define testing objectives, scope, and environments  
- Identify initial risks and dependencies  
- Set up project management tools (Jira/GitHub Projects)  
- Draft the test plan and align team responsibilities

---

## ✅ **In-Scope Features (Based on FR Codes)**

| Area | Feature | FR Code |
|------|----------|---------|
| Catalog & Discovery | Search, filter, and sort books | FR-O01 |
| Cart & Checkout | Add/remove/update items, 4-step checkout | FR-O02 |
| Payments | Paystack integration, currency validation | FR-O03 |
| Orders | Order history, CSV export, refunds | FR-O04–O05 |
| Accessibility & Performance | WCAG 2.1 AA, LCP ≤ 2.5s | FR-X01–X02 |
| Compatibility | Responsive across browsers/devices | FR-X03 |

---

## 🚫 **Out-of-Scope**
- Real payment transactions (Paystack sandbox only)  
- Backend API integrations or production data  
- Advanced analytics or admin promotions  
- Real shipping providers  

---

## 💻 **Test Environments**

| Environment | Details |
|--------------|----------|
| **OS** | Windows 11 / macOS Ventura |
| **Browsers** | Chrome (latest), Firefox (latest), Edge |
| **Devices** | Laptop + Mobile view via DevTools |
| **Network** | Normal and throttled (3G) conditions |
| **Hosting** | Local environment (`npm install`, `npm start`) |

---

## 🧰 **Tools & Utilities**

| Category | Tool | Purpose |
|-----------|------|----------|
| **Project Management** | Jira / GitHub Projects | Issue tracking, Kanban board |
| **Test Documentation** | Markdown (`tests/*.md`) | Test plan, cases, defect logs |
| **Accessibility** | axe DevTools, WAVE | Accessibility audits |
| **Performance** | Lighthouse | LCP, CLS, TTI metrics |
| **Bug Evidence** | OS Screen Recorder / Screenshots | Defect documentation |

---

## ⚠️ **Initial Risks & Mitigation Plan**

| Risk | Impact | Probability | Mitigation |
|------|---------|--------------|-------------|
| Paystack integration fails in sandbox | High | Medium | Mock payment responses; retry with test keys |
| Accessibility violations (ARIA, focus) | Medium | High | Early audit with axe & WAVE tools |
| Checkout flow errors or data loss | High | Medium | Test persistence and validation early |
| CSV export corruption | Medium | Medium | Validate columns and UTF-8 encoding |
| Missing test coverage for intentional defects | High | Medium | Trace to FR codes and track on board |

---

## 🔍 **Test Types Planned**

| Test Type | Description |
|------------|-------------|
| **Functional Testing** | Validate core flows — catalog, cart, checkout, payments |
| **Accessibility Testing** | Use automated and manual checks (WCAG 2.1 AA) |
| **Performance Testing** | Measure LCP, TTI via Lighthouse |
| **Compatibility Testing** | Verify UI responsiveness across major browsers |
| **Regression Testing** | Check intentional defects and fixed bugs |

---

## 🚪 **Entry Criteria**
- Application runs locally without errors (`npm install` & `npm start`)  
- Project board created and accessible  
- Team roles and responsibilities assigned  
- Test environment configured  
- Initial risk list documented  

## 🚪 **Exit Criteria (for Phase 1)**
- Approved test plan document (`tests/test-plan.md`)  
- Project board populated with Epics, Stories, and Tasks  
- Risks validated and logged  
- App successfully runs locally across test environments  

---

## 🧩 **Deliverables (Week 1)**
- ✅ `tests/test-plan.md` (this document)  
- ✅ Active project board (Jira/GitHub Projects)  
- ✅ Team role and communication plan  
- ✅ Confirmed local app setup (`npm install`, `npm start`)  

---

## 📞 **Communication Plan**
| Channel | Purpose |
|----------|----------|
| **WhatsApp Group** | Daily coordination, quick updates |
| **GitHub Issues / Jira Comments** | Defect tracking and status updates |
| **Weekly Meeting (Wednesday)** | Progress review with instructor |
| **Google Meet / Zoom** | Ad-hoc discussions or test reviews |

---

## 🏁 **Sign-Off**
| Role | Name | Approval |
|------|------|----------|
| **Test Manager** | Derick Maloba | ✅ |
| **Risk Analyst** | Margaret Wairimu | ✅ |
| **Test Executor** | Molefi Mothibi | ✅ |

---

### ✅ **Summary**
This Phase 1 Test Plan establishes the foundation for the Book Store App QA project by defining the scope, environment setup, risk assessment, and team responsibilities.  
The next phase (Week 2) will focus on **Test Case Design and Early Execution** based on the functional requirements provided....
