# Awesome-Visual-Customer-Journey-Workflow-Builder

# Awesome Visual Customer Journey & Workflow Builder

> A curated list of top Visual Customer Journey and Workflow Builder platforms — both SaaS/Hosted commercial solutions and open-source alternatives for designing automated, multi-step customer experiences across channels.  
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Freshworks Customer Journeys](#freshworks-customer-journeys)
  - [Salesforce Flow Builder](#salesforce-flow-builder)
  - [Zapier](#zapier)
  - [Make](#make)
  - [Microsoft Power Automate](#microsoft-power-automate)
  - [Tray.io](#trayio)
  - [Workato](#workato)
  - [Relay.app](#relayapp)
- [Open-Source Software](#-open-source-software)
  - [Helio](#helio)
  - [n8n](#n8n)
  - [Activepieces](#activepieces)
  - [Metabot CJM Designer](#metabot-cjm-designer)
  - [FlowForge](#flowforge)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Visual Customer Journey and Workflow Builder platforms. These are not open-source but are included as reference points for feature comparison.

### Freshworks Customer Journeys
**Type:** Marketing journey builder within Freshworks CRM  
Freshworks provides a dedicated Customer Journeys builder for marketing automation. The visual canvas connects trigger blocks (email activity, list membership, page visits, Shopify events, form submissions) to action blocks (send email, update fields, webhooks, WhatsApp/SMS messages) and condition blocks for branching [citation:1]. Time delays and traffic splits allow for staggered, multi-path journeys. Annotations help teams document why specific conditions exist. The builder validates journeys for errors before activation. Part of the broader Freshworks CRM ecosystem.

### Salesforce Flow Builder
**Type:** Declarative automation canvas across Salesforce clouds  
Salesforce Flow Builder is the automation backbone for the Salesforce platform, used for everything from simple record updates to complex multi-step customer journeys. It supports Screen Flows (user-facing wizards), Record-Triggered Flows (automation on data changes), and Scheduled Flows. Fonteva's documentation demonstrates building member journey flows from scratch with stages, screens, and decision elements [citation:7]. Sinch's guide shows how Flow Builder orchestrates SMS drip campaigns with behavioral triggers and multi-channel coordination [citation:2]. The learning curve is steep, but the integration depth within Salesforce is unmatched.

### Zapier
**Type:** No-code automation with paths  
Zapier connects 7,000+ apps with trigger-action workflows. Multi-step Zaps support filters, formatters, and Paths for branching. While not designed specifically for customer journey mapping, it is widely used for lifecycle automation (welcome sequences, lead nurturing, onboarding) when combined with a CRM or marketing tool.

### Make
**Type:** Visual automation with granular data control  
Make's scenario builder shows data flowing between modules, with support for branching, iteration, and error handling. It offers more control over data transformation than Zapier, making it suitable for complex journey logic where customer data needs to be shaped between steps.

### Microsoft Power Automate
**Type:** Business automation across Microsoft 365 and Dynamics  
Power Automate lets business users build workflows with a visual designer and hundreds of connectors. It integrates with Dynamics 365 for customer journey automation and can orchestrate multi-step processes across Microsoft and third-party services. Best suited for organizations already embedded in the Microsoft ecosystem.

### Tray.io
**Type:** Enterprise iPaaS with embedded automation  
Tray.io provides a visual canvas with 650+ connectors and a Connector SDK. Its Embedded offering lets SaaS vendors embed automation capabilities into their own products, enabling customer-facing journey builders within third-party platforms. Features include callable workflows for reusable logic and Insights for health monitoring.

### Workato
**Type:** Enterprise automation with governance  
Workato combines enterprise-grade security with a consumer-grade design interface, targeting both IT and business users. Recipes can orchestrate complex multi-step customer processes across cloud and on-premises systems, with cross-enterprise visibility for IT governance.

### Relay.app
**Type:** Human-in-the-loop workflow automation  
Relay.app differentiates with workflows that pause at defined steps for human judgment, approval, or input. This suits customer journey processes where not every decision should be automated — such as high-value sales follow-ups or escalation handling. It integrates with CRM and project tools and is frequently cited for its clean interface.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Visual Customer Journey and Workflow Builder tools. All listed projects offer source code you can deploy on your own infrastructure.

### Helio
**Stack:** TypeScript / React Flow / Temporal / PostgreSQL / ClickHouse | **License:** AGPL-3.0  
An open-source, AI-native growth platform that combines a Customer Data Platform (CDP) with visual journey orchestration. The journey builder uses a **React Flow canvas** that compiles into a validated DAG, with one Temporal workflow per enrolled contact for durable execution . Journeys survive process restarts (`kill -9` with timers expired), support live-data branches, and trigger from the event stream. Multi-channel delivery covers email, SMS (Twilio), WhatsApp (Cloud API), web push, and in-app messages. Includes an **AI copilot** that generates segments, journeys, and on-brand emails from natural language descriptions, plus an **MCP server** for external AI agents to drive campaigns programmatically [citation:3]. Segmentation uses a visual nested AND/OR builder over fields, JSON attributes, and recency, with always-live membership (segments are predicates, not sync jobs). Migration importers detect HubSpot/Mailchimp/Klaviyo exports, and a Segment-compatible HTTP Tracking API accepts existing instrumentation. **Free forever** — no plans, contact caps, or metering [citation:3].  
**Best for:** Teams wanting a genuinely self-hosted, AI-native customer journey platform with durable execution, multi-channel delivery, and no vendor lock-in.

### n8n
**Stack:** TypeScript / Node.js | **License:** Sustainable Use License (source-available)  
n8n is the most widely adopted source-available workflow automation platform, with a visual canvas and 500+ native integrations. While not purpose-built for customer journey mapping, it is frequently used for lifecycle automation, onboarding sequences, and CRM-triggered workflows. The visual builder supports branching and code steps where needed, and self-hosting eliminates per-task pricing. **Note:** The Sustainable Use License restricts certain commercial resale; it is not OSI-approved open source, though internal self-hosting is permitted.

### Activepieces
**Stack:** TypeScript | **License:** MIT  
Activepieces is a genuinely MIT-licensed open-source automation platform positioned as a permissively licensed alternative to n8n. The Community Edition is free to self-host with a visual builder and a growing integration library. It can be used for customer-facing automation flows, though it lacks dedicated journey-specific features like contact enrollment, wait steps optimized for time-based journeys, or built-in CDP capabilities.

### Metabot CJM Designer
**Stack:** React | **License:** Apache 2.0  
A visual no-code editor specifically for building funnels, customer journeys, and AI pipelines on top of the Metabot low-code engine [citation:4]. The repository provides an open-source example implementation with core UI logic (nodes, edges, inspector dialogs, toolbar, import/export) and a JSON schema for describing funnel steps [citation:9]. It integrates with Metabot via a `cjm/import` API endpoint. **Important:** This is a reference implementation and educational example rather than a production-ready platform — you bring your own execution engine (Metabot) and adapt the designer for your needs.  
**Best for:** Developers wanting a starting point for building a custom journey editor on top of a low-code engine.

### FlowForge
**Stack:** PHP | **License:** AGPL-3.0  
An open-source, self-hosted automation platform designed to run on **PHP shared hosting** (cPanel, Hostinger) with a single cron job — a rarity in this space, where most tools require Node.js or Docker [citation:14]. Features include 1,690 apps, an AI workflow builder (bring your own OpenAI/Anthropic/Gemini key), automatic retries, and MCP support. **AI voice agents** can answer calls and book appointments. While not a dedicated customer journey tool, it can orchestrate CRM and marketing automation workflows on infrastructure that most SMBs already have.  
**Best for:** Teams on shared PHP hosting wanting self-hosted automation without VPS or container infrastructure.

---

## 📊 Comparison at a Glance

| Software | License | Type | Visual Canvas | Durable Execution | Multi-Channel | Self-Hosted | Best For |
|----------|---------|------|---------------|-------------------|---------------|-------------|----------|
| **Freshworks** | Proprietary | Marketing journeys | ✅ | (Cloud) | ✅ Email/SMS/WhatsApp | ❌ | Freshworks CRM users |
| **Salesforce Flow** | Proprietary | Platform automation | ✅ | (Cloud) | Via integrations | ❌ | Salesforce ecosystem |
| **Zapier** | Proprietary | No-code automation | ✅ (Paths) | (Cloud) | Via integrations | ❌ | Broadest app coverage |
| **Make** | Proprietary | Visual automation | ✅ | (Cloud) | Via integrations | ❌ | Granular data shaping |
| **Power Automate** | Proprietary | Business automation | ✅ | (Cloud) | Via connectors | ❌ | Microsoft 365 |
| **Tray.io** | Proprietary | Enterprise iPaaS | ✅ | (Cloud) | Via connectors | ❌ | Embedded automation |
| **Workato** | Proprietary | Enterprise automation | ✅ | (Cloud) | Via connectors | ❌ | Governance + citizen integrators |
| **Relay.app** | Proprietary | HITL automation | ✅ | (Cloud) | Via integrations | ❌ | Human-in-the-loop |
| **Helio** | AGPL-3.0 | CDP + journeys | ✅ React Flow | ✅ Temporal | ✅ Email/SMS/WhatsApp/Push | ✅ | Full open-source journey platform |
| **n8n** | Sustainable Use | Source-available automation | ✅ | (Self-host) | Via integrations | ✅ | Powerful self-hosted automation |
| **Activepieces** | MIT | Open-source automation | ✅ | (Self-host) | Via integrations | ✅ | MIT-licensed self-hosted |
| **Metabot CJM** | Apache 2.0 | Journey editor example | ✅ | (Metabot) | (Check) | ✅ | Building custom journey editors |
| **FlowForge** | AGPL-3.0 | PHP automation | ✅ | (Cron) | Via integrations | ✅ | Shared PHP hosting |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Visual Customer Journey or Workflow Builder that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source (or clearly note the license if source-available but not OSI-approved, as with n8n).

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
