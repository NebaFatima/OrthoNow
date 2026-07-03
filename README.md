# OrthoNow Developer Assignment — Namoza

Three deliverables for OrthoNow's digital growth engagement: a GTM event schema, a conversion-optimized landing page, and a CRM integration design.

## 📂 Repository Structure

```
├── index.html                          # Task 01 demo — 3-step booking form (uses tracking.js)
├── Task_1/
│   ├── tracking.js                     # Centralized dataLayer manager module
│   └── task1_gtm_schema.md             # Event schema, naming conventions, GTM container config
├── Task_2/
│   ├── landing.html                    # Conversion-optimized landing page (single self-contained file)
│   └── pagespeed-task2.png             # Lighthouse screenshot — Score: 100
├── Task_3/
│   └── integration_design.md           # Written answer (397 words) + requirements checklist
└── README.md
```

### Live URLs (GitHub Pages)

| Page | URL | PageSpeed Mobile |
| :--- | :--- | :--- |
| Task 1 — 3-step booking form | [nebafatima.github.io/OrthoNow/index.html](https://nebafatima.github.io/OrthoNow/index.html) | **100** |
| Task 2 — Conversion landing page | [nebafatima.github.io/OrthoNow/Task_2/landing.html](https://nebafatima.github.io/OrthoNow/Task_2/landing.html) | **100** |

---

## 🛠 Tech Stack

- **Frontend**: HTML5, CSS3 (custom properties), Vanilla JS (ES6+)
- **Tracking**: GTM dataLayer API, GA4 Funnel Exploration
- **Integration**: HubSpot CRM APIs, Karix WhatsApp Business API

---

## 🚀 Local Setup

1. Clone this repository
2. Open `index.html` in a browser to see the Task 1 booking form demo
3. Open `Task_2/landing.html` to see the Task 2 landing page
4. To verify tracking: open DevTools Console, type `window.dataLayer`, then step through the form

---

## 🏛 Architectural Decisions

### 1. Zero-Dependency Frontend
Both pages use vanilla HTML, CSS, and JS with no frameworks or external requests. This keeps the total page weight under 20KB and ensures PageSpeed scores of 100 on mobile.

### 2. Event-Driven Tracking (Task 01)
Instead of generic "Form Submit" triggers, the schema uses custom `dataLayer` events that fire only after front-end validation passes. This means Google Ads optimizes for real leads, not invalid submissions.

### 3. Phone Deduplication (Task 03)
HubSpot deduplicates on email, not phone. Since the form collects no email, every submission would create a duplicate without a Search API call before creation. The integration design handles this with a search-before-create pattern in a serverless middleware.

---

## 📝 Submission Notes

- **Validation**: Regex validation for phone numbers and name length
- **Loading States**: Submit button shows loading state to prevent double-submissions
- **Accessibility**: Semantic HTML, ARIA labels, and high contrast ratios
