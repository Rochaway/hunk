# **User Journey Design: From Problem to Outcome with Lovable**

---

## **1\. Entry Point: How Does the User Start?**

Options for “Start” (choose or combine based on your product context):

* Landing Page / Dashboard CTA:  
  User clicks a prominent button like “Create New Experiment” or “Start Tracking an Outcome.”  
* Guided Setup Wizard:  
  Onboarding flow triggered on first login or from a “New Campaign” button.  
* Chat-Driven Assistant:  
  User opens a chat interface and types “I want to track an outcome” or “Help me set up an experiment.”

Recommendation:  
Use a guided setup wizard accessible from the dashboard with a clear CTA:

*“Start your journey: Define your outcome and build your AI experiment.”*

---

## **2\. Step 1: Define the Outcome You Want to Track & Deliver**

UI:

* Clean, minimal input screen with a single question:  
  *“What customer outcome are you trying to track and improve?”*  
* Examples and tooltips to help non-technical users:  
  * “Increase lead conversion rate”  
  * “Reduce call resolution time”  
  * “Improve customer satisfaction score”  
* Option to select from common templates or enter a custom outcome.

Behind the Scenes:

* Capture outcome as a structured object with fields like:  
  * Outcome name  
  * Description  
  * Tangible value (e.g., revenue, time saved)  
  * Associated user journey stage (optional)

---

## **3\. Step 2: Choose Your Experiment Template / Workflow Model**

UI:  
Present 3-5 predefined experiment templates based on common LLM use cases and complexity, e.g.:

| Template Option | Description |
| ----- | ----- |
| 1\. Intent \> Prompt \> Outcome | Simple flow: Define user intent, write prompt, assign outcome metric. |
| 2\. Intent \> Capabilities \+ Actions \+ Prompt \> Outcome | More detailed: Define intent, capabilities, actions, then prompt and outcome. |
| 3\. Intent \> Actions \+ Prompt \> Outcome | Focus on actions triggered by intent, then prompt and outcome. |
| 4\. Intent \> Codebase \> Actions \> Prompt \> Outcome | For technical users: integrate codebase hooks, actions, prompt, and outcome. |
| 5\. Custom / Blank | Start from scratch or customize any part of the flow. |

* Each option includes a brief explanation and example use case.  
* Allow users to preview or “Learn More” about each template.

Behind the Scenes:

* Store user’s template choice to tailor subsequent steps and UI.

---

## **4\. Step 3: Configure Your Experiment Components**

Guided, step-by-step form tailored to chosen template:

* Intent Definition:  
  * Select or define user intents relevant to the outcome.  
  * Provide examples or import from existing NLU systems if available.  
* Capabilities & Actions (if applicable):  
  * Define high-level capabilities (e.g., “Book Appointment”).  
  * Define discrete actions/workflows under each capability (e.g., “User Lookup”, “Check Availability”).  
  * Option to reuse existing capabilities/actions or create new ones.  
* Prompt Setup:  
  * Write or import prompt templates.  
  * Support variables/placeholders for dynamic input.  
  * Preview prompt with sample data.  
* Codebase Integration (if applicable):  
  * Connect to user’s code repository or API endpoints.  
  * Map code hooks to actions or intents.  
  * Provide API key input fields and test connection buttons.  
* Outcome Metric Assignment:  
  * Connect to CRM, analytics, or manual input for outcome metrics.  
  * Map metrics to intents, capabilities, or actions as needed.

UI/UX Notes:

* Use progressive disclosure: show only relevant fields per template and user expertise.  
* Provide inline help, examples, and validation.  
* Allow saving progress and returning later.

---

## **5\. Step 4: Review & Confirm Your Setup**

UI:

* Summary page showing all configured components: intents, capabilities, actions, prompts, outcome metrics, integrations.  
* Visual flow diagram illustrating the experiment pipeline.  
* Edit buttons to jump back to any step.  
* “Launch Experiment” button to deploy.

---

## **6\. Step 5: Automated Build Suggestion & Deployment**

Behind the Scenes:

* Based on user inputs, Lovable generates a custom LLM edge function build plan:  
  * Code snippets for prompt execution.  
  * API integration templates.  
  * Data tracking hooks.  
* Present this plan to the user for review with option to customize or request help.  
* Upon approval, deploy the edge function and connect to data pipelines.

---

## **7\. Step 6: Monitor & Iterate**

* Redirect user to real-time analytics dashboard showing experiment performance.  
* Provide actionable insights, alerts, and rollback options.  
* Offer suggestions for prompt improvements or new experiments based on data.

---

## **Additional Design Considerations**

* Non-Technical Users:  
  * Use plain language, examples, and tooltips.  
  * Minimize jargon and technical fields unless user opts in.  
  * Provide “Help me decide” or “Suggest a template” AI assistant.  
* Technical Users:  
  * Expose advanced configuration options (codebase hooks, API keys).  
  * Allow importing/exporting JSON/YAML experiment definitions.  
  * Provide debugging and logs access.  
* General UX:  
  * Responsive design for desktop and tablet.  
  * Save and resume functionality.  
  * Clear progress indicators and next-step guidance.

---

# **Summary Table: User Journey Steps**

| Step \# | User Action / System Response | Key UI Elements / Features |
| ----- | ----- | ----- |
| 1 | User starts journey via dashboard CTA or wizard | CTA button, welcome screen |
| 2 | User defines outcome to track | Single input with examples, tooltips |
| 3 | User selects experiment template | Template cards with descriptions |
| 4 | User configures intents, capabilities, actions, prompts, integrations | Guided form, progressive disclosure, validation |
| 5 | User reviews and confirms setup | Summary page, visual flow diagram |
| 6 | Lovable suggests build plan and deploys edge function | Generated code preview, deploy button |
| 7 | User monitors experiment and iterates | Analytics dashboard, alerts, rollback options  |

