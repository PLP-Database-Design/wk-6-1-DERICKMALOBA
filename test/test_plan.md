🧪 Test Plan – Book Store App

Team: Zero Bug Society
Date: November 5, 2025
Version: 1.0

🎯 Objective and Scope
Objective

To ensure the Book Store App meets functional requirements, accessibility standards, performance benchmarks, and provides a seamless user experience across all supported platforms and browsers.

Scope

Comprehensive testing of the React-based Book Store application including catalog browsing, cart management, checkout workflow, payment processing, order management, and administrative functions.

📋 In-Scope Features
Feature Area	FR Codes	Description
Catalog & Discovery	FR-O01	Search, filter, sort, and view book details
Cart Management	FR-O01	Add/remove items, update quantities, and ensure cart persistence
Checkout Wizard	FR-O02	4-step process: Shipping → Review → Payment → Confirmation
Payments	FR-O03	Paystack integration, currency handling, success/error flows
Orders	FR-O04, FR-O05	Order history, details, status timeline, CSV export
Admin Console	FR-M01–M05	Catalog CRUD, inventory, orders dashboard, moderation
Notifications	FR-N01, FR-N02	Badge counts, mark as read, order updates
Accessibility	FR-X01	WCAG 2.1 AA compliance, keyboard navigation
Performance	FR-X02	LCP ≤ 2.5s (desktop), TTI ≤ 1s, lazy loading
🚫 Out-of-Scope

Backend API services (uses localStorage only)

Real payment processing (test mode only)

Multi-currency catalog displays

Real shipping carrier integration

Production deployment infrastructure

Load testing at scale

🌐 Environments
Browsers & Devices
Browser	Versions	Devices
Chrome	Latest 2	Desktop, Mobile, Tablet
Firefox	Latest 2	Desktop, Mobile, Tablet
Safari	Latest 2	Desktop, Mobile, Tablet
Edge	Latest 2	Desktop, Mobile, Tablet
Network Conditions

Normal: Unthrottled

Slow 3G: 500ms RTT, 50kbps throughput

Offline: Service worker behavior

Screen Readers

NVDA (Windows)

VoiceOver (macOS/iOS)

JAWS (Windows - if available)

🛠️ Tools
Testing Tools
Category	Tools
Accessibility	axe DevTools, WAVE, Lighthouse
Performance	Lighthouse, DevTools Performance Tab
Compatibility	BrowserStack, DevTools Device Emulation
Management	GitHub Projects, Jira
Recording	OBS, Browser Native Recording
Browser Extensions

React Developer Tools

Redux DevTools (if applicable)

axe DevTools

WAVE Evaluation Tool

⚠️ Risks and Mitigations
Risk	Impact	Probability	Mitigation
Payment gateway unavailability	High	Medium	Use test keys, simulate offline scenarios
localStorage quota exceeded	Medium	Low	Test with large datasets, implement error handling
Cross-browser compatibility issues	High	High	Early compatibility testing, progressive enhancement
Accessibility compliance gaps	Medium	Medium	Early a11y testing, automated scanning
Performance regression	Medium	Medium	Baseline performance metrics, continuous monitoring
Team resource constraints	Medium	Medium	Clear role definitions, regular sync meetings
🧩 Test Types
Functional Testing

Unit Testing – Component-level validation

Integration Testing – Component interaction flows

End-to-End Testing – Complete user journeys

Regression Testing – Verify existing functionality

Accessibility Testing

Automated: axe-core, Lighthouse a11y audits

Manual: Keyboard navigation, screen reader testing

Visual: Color contrast, focus indicators

Performance Testing

Core Web Vitals: LCP, FID, CLS measurements

Load Time: Initial page load and navigation

Responsiveness: Interaction latency

Compatibility Testing

Cross-Browser: Latest 2 versions of major browsers

Responsive Design: Mobile, tablet, desktop breakpoints

Progressive Enhancement: Graceful degradation

Security Hygiene

Input Validation: Form sanitization, XSS prevention

Data Storage: localStorage security, sensitive data handling

Payment Security: Test key usage, error handling

📊 Entry / Exit Criteria
Entry Criteria

✅ Application builds and runs without errors
✅ Test environment configured and accessible
✅ Test data prepared and loaded
✅ Project management board configured
✅ Team roles and responsibilities defined

Exit Criteria

✅ All critical and major defects resolved or accepted
✅ Test cases executed with ≥ 95% pass rate
✅ Accessibility compliance verified (WCAG 2.1 AA)
✅ Performance targets met across supported browsers
✅ Test documentation completed and reviewed
✅ Final report and video presentation delivered

📈 Success Metrics
Metric	Target
Test Case Coverage	≥ 95%
Critical Defect Resolution	100%
Accessibility Compliance	WCAG 2.1 AA
Performance Budget	LCP ≤ 2.5s, TTI ≤ 1s
Cross-Browser Compatibility	Latest 2 versions
🔄 Test Cycle Schedule
Week	Focus Areas	Deliverables
1	Planning & Setup	Test Plan, Environment Setup
2	Test Design & Execution	Test Cases, Early Results
3	Final Execution & Reporting	Final Report, Video Presentation
👥 Team Responsibilities
Role	Member	Responsibilities
Test Manager	Derick Maloba	Overall coordination, progress tracking, reporting
Risk Analyst	Margaret Wairimu	Test case design, risk assessment, strategy
Test Executor	Molefi Mothibi	Test execution, defect logging, evidence collection
🏆 Zero Bug Society – Delivering Quality Assurance Excellence

Last Updated: November 5, 2025
Next Review: November 11, 2025