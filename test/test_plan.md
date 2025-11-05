# ✅ Week 1 Setup Checklist — Zero Bug Society

**Team:** Zero Bug Society  
**Due Date:** Wednesday, November 5, 2025  
**Status:** In Progress

---

## 🎯 Week 1 Objectives

- [ ] **Repository Setup** — Clone, install, and run application locally
- [ ] **Project Board** — Create and configure Jira/GitHub Projects
- [ ] **Test Plan** — Complete initial test plan document
- [ ] **Team Organization** — Assign roles and establish communication
- [ ] **Tool Setup** — Install and verify all testing tools

---

## 👥 Team Roles Assignment

| Role | Team Member | Status |
|------|-------------|--------|
| **Test Manager** | [Name TBD] | ⏳ Pending |
| **Risk Analyst** | [Name TBD] | ⏳ Pending |
| **Test Executor** | [Name TBD] | ⏳ Pending |

### Role Confirmation Checklist
- [ ] All team members understand their role responsibilities
- [ ] Contact information shared (email, phone, preferred messaging)
- [ ] Primary and backup communication channels established
- [ ] Meeting availability confirmed for weekly sync (Wednesdays)

---

## 💻 Repository Setup

### Local Environment Setup
- [ ] Clone repository from [repository URL]
- [ ] Install Node.js (v16+ recommended)
- [ ] Run `npm install` successfully
- [ ] Create `.env` file in root directory
- [ ] Add Paystack test key: `REACT_APP_PAYSTACK_PUBLIC_KEY=pk_test_...`
- [ ] Add currency: `REACT_APP_CURRENCY=ZAR` (or NGN/GHS/USD)
- [ ] Run `npm start` and verify app loads at `http://localhost:3000`
- [ ] Navigate to catalog page and verify books display
- [ ] Add item to cart and verify functionality
- [ ] Clear localStorage and verify fresh state

### Troubleshooting Common Issues
**Problem:** `npm install` fails  
**Solution:** Delete `node_modules` and `package-lock.json`, retry

**Problem:** "Please enter a valid Key" error  
**Solution:** Verify `.env` contains `pk_test_` key, restart dev server

**Problem:** Payment window doesn't open  
**Solution:** Check browser console for script errors; disable ad blockers

---

## 🎫 Project Board Setup (Jira or GitHub Projects)

### Jira Setup (Recommended)
- [ ] Create free Jira Cloud account at atlassian.com
- [ ] Create new project: "Book Store QA — Zero Bug Society"
- [ ] Select **Kanban** board template
- [ ] Configure issue types: Epic, Story, Task, Bug
- [ ] Set up workflow: To Do → In Progress → In Review → Done
- [ ] Add custom field: **Severity** (Critical, Major, Minor, Cosmetic)
- [ ] Add custom field: **FR Code** (text field for traceability)
- [ ] Create components:
  - Catalog
  - Cart
  - Checkout
  - Payments
  - Orders
  - Admin
  - Notifications
  - Accessibility
  - Performance
- [ ] Create labels: `intentional-defect`, `regression`, `a11y`, `perf`, `security`
- [ ] Invite team members as collaborators
- [ ] Share board URL with instructor

### GitHub Projects Setup (Alternative)
- [ ] Navigate to repository → Projects tab
- [ ] Create new project: "QA Testing Board"
- [ ] Select **Kanban** template
- [ ] Add custom fields:
  - Severity (single select: Critical, Major, Minor)
  - Priority (single select: High, Medium, Low)
  - FR Code (text)
  - Environment (text: browser, OS, device)
- [ ] Create views:
  - All Issues
  - Open Bugs by Severity
  - In Progress
  - Blocked
- [ ] Invite team members
- [ ] Share project URL with instructor

### Board Verification
- [ ] Create sample bug issue to test workflow
- [ ] Verify all team members can create/edit issues
- [ ] Test status transitions (drag-and-drop working)
- [ ] Confirm filters and search functionality
- [ ] Screenshot board setup for Week 1 submission

---

## 🛠️ Testing Tools Installation

### Accessibility Tools
- [ ] **axe DevTools** — Install browser extension
  - Chrome: [Web Store link]
  - Firefox: [Add-ons link]
  - Verify: Run scan on catalog page
- [ ] **WAVE** — Install extension or use web version
  - Verify: Run scan on checkout page
- [ ] **Screen Reader** — Install and test
  - Windows: Download NVDA (free)
  - macOS: Enable VoiceOver (built-in)
  - Test: Navigate catalog with keyboard only

### Performance Tools
- [ ] **Lighthouse** — Verify Chrome DevTools access
  - Open DevTools → Lighthouse tab
  - Run audit on catalog page
  - Target: Performance score > 90
- [ ] **Network Throttling** — Set up profiles
  - Fast 3G: 1.6 Mbps down, 750 Kbps up, 562ms latency
  - Slow 4G: 4 Mbps down, 3 Mbps up, 20ms latency
  - Test: Load catalog with throttling enabled

### Browser Setup
- [ ] **Chrome** (latest): Installed and updated
- [ ] **Firefox** (latest): Installed and updated
- [ ] **Safari** (macOS only): Updated to latest
- [ ] **Edge** (latest): Installed and updated
- [ ] Device emulation configured:
  - Chrome DevTools → Toggle device toolbar
  - Test: iPhone 12 (390x844), iPad (768x1024)

### Recording Tools
- [ ] **Screen Recording** — Test capture
  - Windows: Game Bar (Win + G)
  - macOS: QuickTime (Cmd + Ctrl + N)
  - Alternative: Loom, OBS Studio
- [ ] **Screenshot Tool** — Verify quick capture
  - Windows: Snip & Sketch (Win + Shift + S)
  - macOS: Screenshot (Cmd + Shift + 4)
  - Browser: DevTools screenshot (Cmd/Ctrl + Shift + P → "screenshot")

---

## 📝 Test Plan Creation

### Document Preparation
- [ ] Review `docs/functional-requirements.md` thoroughly
- [ ] Review `docs/technical-specs.md` for constraints
- [ ] Review `docs/submission.md` for template guidance
- [ ] Identify all FR codes (FR-O01 through FR-X04)
- [ ] Map high-risk areas to test priorities

### Test Plan Sections Completion
- [ ] **Objective and Scope** — Clear, measurable goals
- [ ] **In-Scope Features** — All FR codes listed and mapped
- [ ] **Out-of-Scope** — Boundaries defined
- [ ] **Environments** — Browser/device matrix documented
- [ ] **Tools** — All accessibility/performance tools listed
- [ ] **Risks and Mitigations** — At least 5 risks with impact/probability
- [ ] **Test Types** — Functional, a11y, perf, compatibility percentages
- [ ] **Entry/Exit Criteria** — Specific, verifiable conditions
- [ ] **Team Roles** — Responsibilities clearly defined
- [ ] **Communication Plan** — Channels and schedule established

### Review and Approval
- [ ] Test Manager review: Structure and completeness
- [ ] Risk Analyst review: Risk coverage and test types
- [ ] Test Executor review: Practicality and clarity
- [ ] Team consensus on approach and priorities
- [ ] Save as `tests/test-plan.md` in repository
- [ ] Commit and push to repository

---

## 📞 Communication Setup

### Team Channels
- [ ] Primary channel selected: [Discord/Slack/Teams/WhatsApp]
- [ ] Channel created: "Zero Bug Society — Book Store QA"
- [ ] All members joined and notifications enabled
- [ ] Pin important links: Jira board, repo, meeting links
- [ ] Test message sent and confirmed by all members

### Meeting Schedule
- [ ] Weekly sync time confirmed: [Day/Time TBD]
- [ ] Calendar invites sent with Zoom/Teams link
- [ ] Recurring meeting set up (Wednesdays through Nov 18)
- [ ] Meeting notes template created in shared drive
- [ ] Backup communication plan for absences

### Document Sharing
- [ ] Shared drive created: [Google Drive/OneDrive/Dropbox]
- [ ] Folder structure:
  - `/01-Planning` (test plan, strategy docs)
  - `/02-Test-Cases` (scenarios, checklists)
  - `/03-Evidence` (screenshots, videos, logs)
  - `/04-Defects` (bug reports, analysis)
  - `/05-Reports` (weekly progress, final report)
  - `/06-Meetings` (agendas, notes, recordings)
- [ ] All team members have edit access
- [ ] Naming convention agreed: `YYYYMMDD_DocumentName_v1.0`

---

## 🧪 Initial Testing Verification

### Smoke Test Checklist
- [ ] **Home/Catalog** — Books display with images and prices
- [ ] **Search** — Query returns filtered results
- [ ] **Cart** — Add item, quantity updates, remove works
- [ ] **Checkout** — All 4 steps accessible
- [ ] **Orders** — Empty state displays correctly
- [ ] **Admin** — Unauthorized message for non-admin role

### Currency Testing
- [ ] Test with `REACT_APP_CURRENCY=ZAR` (default)
- [ ] Verify currency symbol displays correctly (R for ZAR)
- [ ] Test with `REACT_APP_CURRENCY=NGN` (restart required)
- [ ] Verify currency symbol displays correctly (₦ for NGN)
- [ ] Document any currency formatting issues

### Environment Variables Verification
- [ ] Print environment variables in console:
  ```javascript
  console.log('Paystack Key:', process.env.REACT_APP_PAYSTACK_PUBLIC_KEY);
  console.log('Currency:', process.env.REACT_APP_CURRENCY);
  ```
- [ ] Confirm values match `.env` file
- [ ] Test payment initialization (can cancel immediately)

---

## 📊 Week 1 Deliverables Final Check

### Required Artifacts
- [ ] Repository runs locally (verified by all team members)
- [ ] Project board created and shared with instructor
- [ ] `tests/test-plan.md` completed and committed
- [ ] Team roles assigned and documented
- [ ] Communication plan established and tested

### Submission Preparation
- [ ] Create `tests/` directory in repository (if not exists)
- [ ] Move `test-plan.md` to `tests/` directory
- [ ] Add team name to first page: "Zero Bug Society"
- [ ] Add date to document: "November 5, 2025"
- [ ] Commit with message: "Week 1: Initial test plan and setup"
- [ ] Push to repository
- [ ] Verify GitHub/GitLab shows updated files
- [ ] Export Jira board screenshot or CSV
- [ ] Prepare 2-minute progress summary for Wednesday meeting

### Pre-Meeting Checklist (for Nov 5 sync)
- [ ] Review test plan one final time
- [ ] Prepare 3 questions for instructor
- [ ] Screenshot board with initial tasks
- [ ] Test meeting link 5 minutes early
- [ ] Have repository open and ready to share screen

---

## 🎯 Week 2 Preview (Nov 6-11)

### Upcoming Tasks
- [ ] Design detailed test cases in `tests/test-cases.md`
- [ ] Begin test execution on high-priority flows
- [ ] Start defect log in `tests/defect-log.md`
- [ ] Capture initial evidence (screenshots, videos)
- [ ] Update board daily with progress

### Preparation
- [ ] Review test case template in `docs/submission.md`
- [ ] Identify 3-5 critical user flows to test first
- [ ] Set up evidence folder structure
- [ ] Practice screen recording workflow

---

## ✅ Sign-Off

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Test Manager | [Name] | ___________ | ___/___/2025 |
| Risk Analyst | [Name] | ___________ | ___/___/2025 |
| Test Executor | [Name] | ___________ | ___/___/2025 |

**Checklist Completed:** _____ / _____ items  
**Readiness Score:** _____% (target: 100% by Nov 5)

---

**Notes:**
- Mark ✅ for completed items
- Mark ⏳ for in-progress items
- Mark ❌ for blocked items (add blocker details below)

**Blockers:**
_[None yet — will update as needed]_

---

**Document Version:** 1.0  
**Last Updated:** November 5, 2025  
**Next Review:** November 6, 2025