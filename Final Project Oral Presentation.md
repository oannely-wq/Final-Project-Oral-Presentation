# Final Project Oral Presentation: Automating Employee Department Updates

## 1. Introduction
* **Who am I:** My name is [Your Name], and I work in the Finance Department as an Accounts Payable Specialist.
* **My Role:** A key part of my job is ensuring that personnel costs are correctly booked to the proper departments and cost centers.

## 2. The Problem
* **The Situation:** Currently, when an employee is transferred to a different department, Human Resources updates this information in our HR system, BambooHR.
* **The Disconnect:** However, HR's process ends there. They often forget to manually update the employee's new department in our financial ERP system, NetSuite. 
* **The Consequence:** Because BambooHR and NetSuite are not synced, the Finance department lacks real-time data. If NetSuite is not updated, employee costs are booked to the wrong department. This leads to inaccurate financial reporting, budgeting errors, and hours of manual correction on our end.

## 3. The Goal
* **Objective:** To build an application workflow that automatically updates an employee's department in NetSuite the moment it is updated in BambooHR.

## 4. The Solution & AI Integration
* **The Core Workflow:** I propose using an integration platform like **Make.com** or **Zapier** to listen for a "Department Change" trigger in BambooHR. Once triggered, it will fetch the updated profile and update the NetSuite employee record.
* **Where AI Comes In:** Bridging the two systems isn't just about moving data; it's about translating it. HR and Finance speak different languages. HR might label a department "Digital Marketing," but NetSuite requires a strict financial code, like "Cost Center 420: Mktg." 
* **The AI Application:**
  * **Intelligent Data Mapping:** By inserting an **OpenAI (ChatGPT) module** into the middle of our Make.com or Zapier workflow, the AI acts as an intelligent translator. It takes the text string from BambooHR, identifies the correct corresponding financial cost center using a prompt, and formats it perfectly for NetSuite.
  * **AI-Generated Workflows:** Additionally, we can use tools like **Zapier Central (AI Copilot)** to actually build this integration. By simply typing the prompt, *"When an employee's department changes in BambooHR, map the department to a finance cost center and update NetSuite,"* the AI automatically builds the API connections for us.

## 5. Benefits and Impact
* **Elimination of Human Error:** We completely bypass the risk of HR forgetting the update or Finance typing the wrong cost center. Costs are allocated with 100% accuracy.
* **Time Savings:** Both HR and Finance are freed from double-entering data manually across two different software platforms.
* **Real-time Financial Integrity:** Our budgeting and expense reporting remain accurate at all times, rather than waiting for end-of-month reconciliations to catch mistakes.

## 6. Conclusion
* Applying AI to this problem handles both the "heavy lifting" of moving data and the "intelligent mapping" required to translate HR terms into Finance terms. 
* It's a perfect example of how AI can silently run in the background to enforce correct financial reporting.

## 7. GitHub Repository
* **Project Link:** [Final Project Oral Presentation](https://github.com/oannely-wq/Final-Project-Oral-Presentation)
