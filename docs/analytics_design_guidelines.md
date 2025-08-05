# **Analytics Design Guidelines Document**

Project: LLM Experimentation & Attribution Platform – Analytics Dashboard  
Date: 2025-08-01  
Author: \[Your Name\]

---

## **1\. Overview**

This document defines the visual and interaction design standards for the Analytics Dashboard of the LLM Experimentation & Attribution Platform. The goal is to provide a simple, intuitive, and powerful interface that enables product, engineering, and operations teams to:

* Attribute changes and improvements to variables, actions, capabilities, and intents.  
* Understand customer journey from intent to outcome with granular filtering.  
* Overlay trends and compare multiple metrics.  
* Predict future outcomes based on historical data.  
* Quickly drill down into problematic areas for diagnosis.

---

## **2\. Visual Style & Branding**

### **2.1 Color Palette**

| Purpose | Color Name | Hex Code | Usage Notes |
| ----- | ----- | ----- | ----- |
| Primary Blue Gradient | Blue Gradient 1 | \#1E3A8A | Main UI elements, headers, buttons |
|  | Blue Gradient 2 | \#3B82F6 | Hover states, highlights |
| Secondary White | White | \#FFFFFF | Backgrounds, text on dark |
| Accent / Success | Green | \#10B981 | Positive trends, success states |
| Accent / Warning | Yellow | \#FBBF24 | Warnings, cautions |
| Accent / Error | Red | \#EF4444 | Errors, negative trends |
| Neutral Dark Background | Dark Gray | \#111827 | Main background |
| Neutral Light Text | Gray | \#9CA3AF | Secondary text |

* Use blue gradients predominantly for charts, buttons, and key UI elements.  
* Backgrounds should be dark gray (\#111827) to reduce eye strain.  
* Text should be primarily white (\#FFFFFF) with secondary text in gray (\#9CA3AF).

### **2.2 Typography**

| Element | Font Family | Weight | Size (px) | Line Height | Usage |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Headings (H1, H2) | Inter, Sans-serif | Bold (700) | 24 \- 32 | 32px | Section titles, dashboard titles |
| Subheadings (H3, H4) | Inter, Sans-serif | Semi-bold (600) | 18 \- 20 | 28px | Chart titles, filters |
| Body Text | Inter, Sans-serif | Regular (400) | 14 \- 16 | 24px | Labels, descriptions |
| Buttons & UI Elements | Inter, Sans-serif | Medium (500) | 14 | 20px | Buttons, inputs |
| Numeric Data | Inter, Sans-serif | Bold (700) | 20 \- 28 | 28px | KPIs, metric values |

* Use Inter font for clarity and modern feel.  
* Maintain consistent font sizes and weights for hierarchy and readability.

---

## **3\. Layout & Components**

### **3.1 Dashboard Layout**

* Header:  
  * Project/Experiment name on left.  
  * Date range selector and filter button on right.  
  * Download report and settings icons next to filters.  
* KPI Summary Bar:  
  * Display 3-5 key metrics (e.g., conversion rate, latency, user sentiment) with numeric values and % change indicators.  
  * Use green/red arrows for positive/negative trends.  
* Main Chart Area:  
  * Multi-line or multi-bar charts with overlay capability.  
  * Allow users to toggle metrics on/off for comparison.  
  * Interactive tooltips showing detailed metric values on hover.  
  * Time range selectors (1D, 7D, 1M, 3M, 6M, 1Y).  
* Filters Panel (Collapsible):  
  * Filters for:  
    * Intent  
    * Capability  
    * Action  
    * LLM Model  
    * Experiment Version  
  * Searchable dropdowns for large lists.  
* Drill-Down Table/List:  
  * Below charts, show detailed data rows for experiments, actions, or intents.  
  * Columns: Name, Status, Metric Values, Date, Trend Indicator.  
  * Sortable and filterable columns.

---

### **3.2 UI Components**

| Component | Description & Usage | Style Notes |
| ----- | ----- | ----- |
| Buttons | Primary (blue gradient), Secondary (white border) | Rounded corners (6px), shadow on hover |
| Dropdowns | For filters and selections | Dark background, white text, subtle border |
| Date Picker | For selecting time ranges | Compact, inline calendar popup |
| Charts | Line, bar, area charts with overlay | Blue gradients for lines, green/red for trends |
| Tooltips | Show detailed metric info on hover | Dark background, white text |
| Tables | Data grids with sorting/filtering | Alternating row colors (\#1F2937, \#111827) |
| Icons | Minimalistic, white or blue accents | Use SVGs for scalability |

---

## **4\. Interaction & Usability**

* Filtering:  
  * Filters update charts and tables in real-time without page reload.  
  * Multiple filters can be combined with AND logic.  
* Trend Overlays:  
  * Users can overlay multiple metrics to compare trends visually.  
  * Use distinct but harmonious colors for each metric line/bar.  
* Drill-Down:  
  * Clicking on a chart segment or KPI opens detailed drill-down below or in a side panel.  
  * Drill-down supports pagination and search.  
* Responsive Design:  
  * Dashboard adapts gracefully to tablet and desktop screen sizes.  
  * Collapsible side filters on smaller screens.  
* Accessibility:  
  * Ensure color contrast meets WCAG AA standards.  
  * Keyboard navigable filters and controls.  
  * Screen reader friendly labels and descriptions.

---

## **5\. Predictive Analytics & Alerts**

* Prediction Overlays:  
  * Show forecasted trends as dashed or shaded lines on charts.  
  * Use tooltip to explain prediction confidence and data range.  
* Anomaly Alerts:  
  * Highlight data points or periods with significant deviations.  
  * Use subtle red/yellow markers with hover explanations.

---

## **6\. Export & Sharing**

* Provide Download Report button exporting current dashboard view as PDF or CSV.  
* Enable Shareable Links with current filters and date ranges applied.

---

## **7\. Example Color & Font CSS Snippet (for Lovable reference)**

css

:root {  
  \--color-primary-start: \#1E3A8A;  
  \--color-primary-end: \#3B82F6;  
  \--color-secondary: \#FFFFFF;  
  \--color-success: \#10B981;  
  \--color-warning: \#FBBF24;  
  \--color-error: \#EF4444;  
  \--color-bg-dark: \#111827;  
  \--color-text-secondary: \#9CA3AF;

  \--font-family: 'Inter', *sans-serif*;  
  \--font-weight-bold: 700;  
  \--font-weight-semibold: 600;  
  \--font-weight-regular: 400;  
  \--font-weight-medium: 500;  
}

---

## **8\. Summary**

This design guide ensures the analytics dashboard is:

* Visually consistent with your brand (blue gradients, dark theme, Inter font).  
* Functionally rich yet simple to use (filtering, overlays, drill-down).  
* Accessible and responsive for all users.  
* Equipped with predictive and alerting features for proactive insights.  
* 

