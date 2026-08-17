# TaskFlow Knowledge Base — Technical Content Portfolio

A 10-article customer support knowledge base written, structured, and illustrated end-to-end for **TaskFlow**, a fictional SaaS project management tool. Built as a portfolio piece to demonstrate technical content development skills: information architecture, procedural writing, visual explanation, and self-service support design.

> **Note:** TaskFlow is a fictional product created for this portfolio. All screens, URLs, and pricing referenced in the articles are illustrative, not real.

---

## Why this project exists

Support documentation is a distinct discipline from marketing or blog writing — it has to be scannable under stress, accurate down to the click, and structured so both humans and search engines can find the one paragraph that solves a reader's problem. This project simulates a real knowledge base sprint: taking a product with common SaaS workflows (onboarding, permissions, billing, integrations, an API) and producing a consistent, professional article for each one.

It's meant to show, not just tell, what I can do as a technical content developer:

- Turn a product feature into a clear, task-oriented support article
- Design a repeatable article template that scales across a whole knowledge base
- Create original instructional illustrations rather than relying on stock screenshots
- Structure content for skimmability: outlines, numbered steps, tables, and FAQs
- Anticipate real user problems and document troubleshooting paths, not just the happy path

---

## What's inside

```
taskflow-kb/
├── README.md                          ← you are here
├── docs/                               ← the 10 knowledge base articles (.docx)
│   ├── KB01_Creating_Your_TaskFlow_Account_and_Workspace.docx
│   ├── KB02_Creating_and_Managing_Projects.docx
│   ├── KB03_User_Roles_and_Permissions.docx
│   ├── KB04_Setting_Up_Integrations.docx
│   ├── KB05_Login_and_2FA_Troubleshooting.docx
│   ├── KB06_Managing_Billing_Plans_and_Invoices.docx
│   ├── KB07_Building_Automations_with_Workflow_Rules.docx
│   ├── KB08_Importing_and_Exporting_Project_Data.docx
│   ├── KB09_Configuring_Notifications_and_Alerts.docx
│   └── KB10_Getting_Started_with_the_TaskFlow_API.docx
├── images/                             ← the 10 original illustrations (.png), one per article
│   ├── 01_account_signup_flow.png
│   ├── 02_project_hierarchy.png
│   ├── 03_roles_permissions_matrix.png
│   ├── 04_integrations_hub.png
│   ├── 05_login_troubleshooting_tree.png
│   ├── 06_billing_plan_comparison.png
│   ├── 07_automation_rule_builder.png
│   ├── 08_import_export_flow.png
│   ├── 09_notification_channels.png
│   └── 10_api_request_flow.png
├── diagram_helpers.py                  ← reusable Python/matplotlib helper library for the illustrations
├── make_diagrams.py                    ← generates all 10 illustrations from diagram_helpers.py
├── data.js                             ← all article copy, structured as data (title, steps, FAQ, etc.)
└── build.js                            ← generates all 10 .docx files from data.js using docx.js
```

Every article is a **standalone Word document** — no shared template file to open first — so each one can be reviewed, downloaded, or dropped into a CMS independently.

---

## The 10 articles

| # | Article | Category | Audience | Level |
|---|---|---|---|---|
| KB01 | Creating Your TaskFlow Account and Workspace | Getting Started | New users | Beginner |
| KB02 | Creating and Managing Projects in TaskFlow | Projects | All users | Beginner |
| KB03 | Understanding User Roles and Permissions | Account & Security | Admins / Owners | Intermediate |
| KB04 | Setting Up Integrations: Slack, Google Drive & Calendar | Integrations | All users | Beginner |
| KB05 | Troubleshooting Login and Two-Factor Authentication Issues | Account & Security | All users | Beginner |
| KB06 | Managing Billing, Plans, and Invoices | Billing | Owners / Admins | Beginner |
| KB07 | Building Automations with Workflow Rules | Automation | PMs / Admins | Intermediate |
| KB08 | Importing and Exporting Project Data (CSV/Excel) | Data Management | All users | Beginner |
| KB09 | Configuring Notifications and Alert Preferences | Settings | All users | Beginner |
| KB10 | Getting Started with the TaskFlow REST API | Developer | Developers | Intermediate |

Together they cover the full lifecycle of a support knowledge base: **onboarding → core usage → account/security → billing → power features (automation, API) → data portability**, which is deliberate — it mirrors how a real support team organizes a help center around the customer journey rather than around internal product teams.

---

## The article template

Every article follows the same repeatable structure, so a reader who's used one TaskFlow article already knows how to navigate the next one:

1. **Header metadata** — category, audience, difficulty, read time, last-updated date (the kind of metadata a real help-desk CMS uses for search and freshness audits)
2. **"In this article" outline** — a numbered preview of every section, so the reader can jump straight to their problem
3. **Overview** — one paragraph of plain-language context before any instructions
4. **What you'll need** — prerequisites, to prevent readers from getting halfway through and hitting a wall
5. **Original illustration** — a custom diagram (flow, hierarchy, matrix, or decision tree) that does work text alone can't
6. **Step-by-step instructions** — numbered steps grouped under task-oriented headings, with callout notes where a step has a common gotcha
7. **Troubleshooting table** — Issue / Likely Cause / Fix, for the scenarios where the happy path didn't work
8. **FAQ** — quick answers to edge-case questions that don't warrant their own section
9. **Related articles** — cross-links that keep readers inside the knowledge base
10. **Footer support prompt** — a consistent "still stuck?" escape hatch

This structure is intentionally boring and consistent — predictability is a feature in support content, not a lack of creativity.

---

## The illustrations

Every article includes one original diagram designed to replace a paragraph of description with something scannable in two seconds. Rather than reuse one visual style everywhere, each illustration uses the diagram type that actually fits its content:

- **Linear process flows** (KB01 sign-up, KB08 import/export) — for sequential steps
- **Hierarchy diagrams** (KB02 workspace → project → task → subtask)
- **Permission matrices** (KB03 roles × capabilities grid)
- **Hub-and-spoke diagrams** (KB04 integrations, KB09 notification channels)
- **Decision trees** (KB05 login troubleshooting) — because troubleshooting is inherently branching logic, not a straight line
- **Comparison cards** (KB06 pricing plans)
- **Trigger → condition → action diagrams** (KB07 automation logic)
- **Request/response sequence diagrams** (KB10 API flow)

All illustrations were built programmatically in Python (`matplotlib`) rather than dragged together in a design tool, which made it possible to keep a single consistent brand palette, spacing system, and typographic scale across all 10 — the same discipline a real content team would apply with a shared Figma library or diagram-as-code pipeline.

---

## How the docs were generated

Both the illustrations and the Word documents are produced from **structured source data**, not hand-formatted one at a time:

- `data.js` holds every article as structured content (headings, step lists, tables, FAQ pairs) — effectively a lightweight content model, similar to how a real knowledge base is often stored in a headless CMS rather than as loose Word files
- `build.js` walks that data and assembles each `.docx` with a shared visual system (typography, color, tables, callouts, numbered/bulleted lists, headers/footers with page numbers)
- `make_diagrams.py` + `diagram_helpers.py` generate the 10 illustrations from a shared helper library, guaranteeing visual consistency

This "content as data" approach is the same principle behind docs-as-code and component-based help centers: write the content once, structured, and let tooling handle consistent presentation — which scales far better than formatting 10 documents by hand once you're maintaining hundreds of articles.

---

## Skills demonstrated

- **Information architecture** — organizing a knowledge base by user journey, with a consistent per-article template and cross-linking
- **Procedural / instructional writing** — clear, numbered, testable steps written from the user's point of view
- **Visual communication** — choosing the right diagram type per concept and producing original illustrations
- **Troubleshooting documentation** — anticipating failure modes, not just documenting the happy path
- **Content structuring & tooling** — treating content as structured data and generating polished output programmatically
- **Audience awareness** — adjusting tone, depth, and prerequisites for audiences ranging from brand-new end users to developers integrating with a REST API

---

## Viewing the articles

Each file in `/docs` is a standard `.docx` and opens in Microsoft Word, Google Docs, LibreOffice, or any compatible viewer. No special software is required.

---

*This is a portfolio project built to demonstrate technical content development skills. TaskFlow is not a real product.*
