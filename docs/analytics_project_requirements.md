# **Analytics Product Requirements Document (PRD)**

## **1\. Problem Statement**

Teams using LLMs struggle to attribute changes in customer outcomes to specific prompt versions, configurations, LLM models, or workflow actions. Without clear analytics, iteration slows, issues go undiagnosed, and teams lack confidence in AI-driven decisions.

The analytics system must provide granular, real-time, and historical insights that link customer intent through capabilities and actions to measurable outcomes, enabling fast, data-driven iteration and troubleshooting.

---

## **2\. User Roles & Needs**

| Role | Needs from Analytics |
| ----- | ----- |
| Product Manager | Understand impact of prompt/config changes on key business metrics; track experiment success. |
| Prompt Engineer | Compare prompt variants; identify winning prompts by outcome metrics; monitor latency and errors. |
| Operations / Support | Diagnose customer issues by tracing outcomes to specific actions or intents; monitor system health. |
| Engineer | Monitor LLM model performance; track API latency/errors; integrate analytics into existing dashboards. |
| Enablement | Standardize analytics views and reporting across teams; ensure data consistency and accessibility. |

---

## **3\. Core Features**

### **3.1 Multi-Dimensional Attribution Analytics**

* Link outcomes to variables: prompt versions, configurations, LLM models, capabilities, actions, and intents.  
* Support filtering and segmentation by any combination of these variables.

### **3.2 Real-Time & Historical Dashboards**

* Visualize key metrics (conversion %, latency, sentiment, resolution time) over selectable time ranges.  
* Overlay multiple metrics/trends for correlation analysis.  
* Show prediction overlays and anomaly detection alerts.

### **3.3 Drill-Down & Detail Views**

* From high-level KPIs to experiment, capability, action, and intent-level data.  
* Sortable, filterable tables with detailed logs and timestamps.

### **3.4 Customizable Filters & Views**

* Time range selectors (1D, 7D, 1M, 3M, 6M, 1Y).  
* Filters for LLM model, experiment version, intent, capability, action, and outcome metric type.

### **3.5 Export & Sharing**

* Export dashboard views and data as CSV or PDF reports.  
* Shareable links preserving current filters and views.

---

## **4\. Data Inputs & Outputs**

| Data Type | Source / Integration | Usage in Analytics |
| ----- | ----- | ----- |
| Experiment Data | Internal DB (prompts, configs, versions) | Attribution of outcomes to experiment variants |
| Outcome Metrics | CRM, CSAT, Analytics platforms, manual input | Measure success/failure of experiments |
| LLM Model Logs | API providers (GPT-4, Gemini, Claude) | Latency, error rates, model-specific performance |
| Intent & Capability Tags | NLU systems or internal classification | Segment outcomes by user intent and capability |
| User Feedback | Thumbs up/down, ratings | Qualitative success signals |

---

## **5\. Platform & Integration Requirements**

* Support multi-LLM API key management and data ingestion.  
* Integrate with CRM, CSAT, and analytics platforms for automated metric imports.  
* Provide REST/GraphQL APIs and webhooks for programmatic data access and event notifications.  
* Secure authentication and role-based access control (e.g., via Supabase).  
* Scalable data storage and query performance for real-time analytics.

---

## **6\. Success Metrics for Analytics**

| Metric Name | Description | Example Use Case |
| ----- | ----- | ----- |
| Dashboard Load Time | Time to load analytics dashboards | Ensure \< 3 seconds for good UX |
| Data Freshness | Latency between data generation and display | Real-time or near real-time (\< 1 min) |
| User Engagement | Frequency of dashboard use by roles | Track adoption and identify training needs |
| Attribution Accuracy | Correct linkage of outcomes to variables | Validate with manual audits |
| Alert Responsiveness | Time to detect and notify anomalies | \< 5 minutes for critical issues |

---

## **7\. Analytics UI/UX Design Guidelines (Summary)**

* Dark theme with blue gradients and white text for clarity and reduced eye strain.  
* Multi-line and bar charts with overlay capability.  
* Interactive tooltips and drill-down tables.  
* Filters panel with searchable dropdowns for intents, capabilities, actions, and models.  
* Responsive design for desktop and tablet.  
* Export and sharing options prominently accessible.

---

## **8\. Clarifying Questions & Answers for Lovable** 

### **1\. What are the priority outcome metrics to support initially?**

* Outcome metrics must be defined by the customer and tied explicitly to their user journey and business goals.  
* Metrics should have tangible, quantifiable value such as money saved/earned, time saved, conversion rates, or customer satisfaction improvements.  
* Example initial metrics to support (aligned with your core problem and Toma use case):  
  * Call Conversion % (e.g., lead converted to sale)  
  * Resolution Time (time to complete a customer request)  
  * LLM Latency (response time impacting user experience)  
  * Deflection Rate (issues resolved without escalation)  
  * Escalation Frequency (fallbacks to human agents)  
  * User Sentiment (thumbs up/down, ratings)  
* For dummy/demo data, show an AI LLM responsible for converting leads on an ecommerce website, tracking conversion %, average order value, and customer satisfaction.

---

### **2\. Which LLM providers and CRM/analytics platforms must be integrated first?**

* HubSpot is a priority CRM platform for outcome metric integration, given its widespread use and rich API ecosystem.  
* Initial LLM providers to support via API keys:  
  * OpenAI GPT-4 (industry standard, broad adoption)  
  * Google Gemini (emerging competitor)  
  * Anthropic Claude (privacy-focused alternative)  
* Analytics platforms for future integration could include Google Analytics, Mixpanel, or custom internal tools, but start with CRM data for direct business outcomes.

---

### **3\. Are there existing data schemas or APIs to connect for outcome metrics?**

* The platform should support flexible ingestion of outcome metrics via:  
  * Direct API integrations with CRM and analytics platforms (e.g., HubSpot APIs).  
  * Manual input or CSV upload for custom or legacy systems.  
  * Webhook/event-driven ingestion for real-time updates.  
* Data schemas should be extensible to accommodate different metric types and metadata (timestamps, experiment IDs, intent/capability tags).  
* Example schema elements:  
  * experiment\_id, metric\_name, metric\_value, timestamp, intent, capability, action, llm\_model, user\_id (optional).

---

### **4\. What level of prediction and anomaly detection is expected in MVP?**

* MVP should include basic predictive analytics and anomaly detection focused on:  
  * Trend forecasting for key metrics (e.g., conversion rate trends over time).  
  * Simple anomaly alerts when metrics deviate significantly from historical baselines (e.g., \>20% drop in conversion).  
* Advanced features like confidence scoring, auto-suggested prompt improvements, or multi-agent evaluation layers are future enhancements beyond MVP.  
* Prediction models should be configurable and transparent, allowing users to understand and trust alerts.

---

### **5\. What user roles and permissions should be enforced in analytics views?**

* Role-based access control (RBAC) is essential to ensure data security and relevance:

| Role | Permissions & Views |
| ----- | ----- |
| Product Manager | Full access to outcome metrics, experiment performance, and high-level dashboards. |
| Prompt Engineer | Access to prompt variant comparisons, latency, error rates, and detailed experiment data. |
| Operations / Support | Access to real-time health dashboards, anomaly alerts, and drill-downs for troubleshooting. |
| Engineer | Access to LLM model performance, API usage, logs, and integration settings. |
| Enablement | Read-only access to standardized reports and analytics for training and process improvement. |
| Admin | Full system access including user management, API keys, and governance controls. |

* Permissions should be enforced both in the UI and API layers, ideally integrated with Supabase authentication and policies.

