# Employee Department Update Automation (BambooHR ⇄ NetSuite Sync)

Welcome to the repository for the **AI in Practice - Final Project**. This project details the design, technical architecture, and validation framework for an automated enterprise sync that bridges HR data and Finance ledgers using **Make.com** and **OpenAI**.

---

## 📋 Project Metadata

* **Author:** Kheit Ool, Accounts Payable Specialist  
* **Course:** AI in Practice (Final Project)  
* **Core Problem:** The manual disconnect between HR department updates (BambooHR) and ERP personnel booking ledgers (NetSuite), leading to financial misallocations.  
* **Solution:** An event-driven integration pipeline that utilizes a Large Language Model (LLM) as an intelligent ontological data translator to normalize and map natural department entries to strict accounting hierarchies.  
* **Integration Platform:** Make.com  
* **AI Model:** OpenAI GPT-4o-mini / GPT-4o  

---

## 📂 Repository Structure

The workspace contains the following files:

* 📂 **`C:\Users\kheit\.gemini\antigravity-ide\scratch\bamboo-netsuite-integration`**
  * 📄 **[final_project.md](file:///C:/Users/kheit/.gemini/antigravity-ide/scratch/bamboo-netsuite-integration/final_project.md)** - The primary technical submission document. Contains:
    * **Part 1:** Detailed Project Alignment & Self-Assessment against the assessment criteria.
    * **Part 2:** Detailed Project Architecture, including Make.com module configurations and a Mermaid sequence diagram.
    * **Part 3:** A step-by-step trace of a specific department change (Employee: **Kheit Ool** transitioning from `Administration: Finance` to `Administration: IT Total:IT`).
    * **Part 4:** Complete NetSuite Sandbox Testing, verification checklists (System Notes, Web Services logs), and rollback procedures.
  * 📄 **[README.md](file:///C:/Users/kheit/.gemini/antigravity-ide/scratch/bamboo-netsuite-integration/README.md)** - This repository index and overview guide.

---

## 🛠️ Key Architectural Pillars

```
+------------------+       Webhook        +------------------+
|    BambooHR      | ===================> |     Make.com     |
| (Source Record)  |                      | (Workflow Engine)|
+------------------+                      +------------------+
                                                   ||
                                          Retrieve | Dynamic Reference
                                         Catalogue | List
                                                   \/
+------------------+      REST Sync       +------------------+
| NetSuite Sandbox | <=================== |    OpenAI API    |
| (Target ERP)     |     Internal IDs     | (GPT Translator) |
+------------------+                      +------------------+
```

1. **Decoupled Workflow Middleware (Make.com):** Handles webhook ingestion, error catching, exponential backoff retries, and API token-based authentication (OAuth 2.0).
2. **Dynamic Context Injection (Halucination Safeguard):** The integration dynamically pulls NetSuite's active department catalogue before calling the LLM. It injects this catalogue into the prompt, forcing the LLM to map to a *valid, existing* financial node.
3. **Structured Outputs (Schema Enforcement):** Enforces a strict JSON response schema from OpenAI to ensure programmatic reliability.
4. **Human-in-the-Loop Routing:** Captures mapping low-confidence scores or mismatch flags and quarantines them via Slack alerting to prevent bad database writes.

---

## 🚀 Quick Start Guide

### Step 1: Set Up Your IDE Workspace
Ensure this directory is set as your active workspace in your IDE to browse the technical details.

### Step 2: Read the Technical Design
Open and review the comprehensive technical specifications detailed in **[final_project.md](file:///C:/Users/kheit/.gemini/antigravity-ide/scratch/bamboo-netsuite-integration/final_project.md)**.

### Step 3: Review the Sandbox Verification Plan
Navigate to **Part 4** of `final_project.md` to see instructions on how to mock payloads in Make.com, verify writes on NetSuite Sandbox System Notes, and audit the web service usage logs.
