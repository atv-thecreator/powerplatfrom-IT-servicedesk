# Enterprise IT Service Desk Solution (Microsoft Power Platform)

[![Platform](https://img.shields.io/badge/Platform-Microsoft_Power_Platform-0078D4?logo=microsoft)](https://powerplatform.microsoft.com/)
[![Dataverse](https://img.shields.io/badge/Database-Microsoft_Dataverse-742774)](https://powerplatform.microsoft.com/en-us/dataverse/)
[![Architecture](https://img.shields.io/badge/Architecture-Model--Driven_App_%2B_Power_Automate-00838F)](#solution-architecture)

An end-to-end IT Ticketing & Management solution built on the **Microsoft Power Platform** using **Dataverse**, a **Model-Driven App**, and **Power Automate Cloud Flows**. This repository contains the unmanaged solution package representing the core database schema, site map design, custom fields, and automated background notification architecture.

---

## 🛠️ Solution Architecture & Components
### 1. Dataverse Relational Database Schema (`IT Tickets`)
* **Primary Entity:** `IT Tickets` (`crfac_itticket` / custom Dataverse table)
* **Custom Columns & Schema Design:**
  * `Priority` (Choice / OptionSet) — Dynamic categorisation (`Low`, `Medium`, `High`, `Critical`)
  * `Status` (Choice / OptionSet) — Incident lifecycle management (`New`, `In Progress`, `On Hold`, `Resolved`, `Closed`)
  * Default Metadata Attributes (Created On, Modified By, Owner, Status Reason)

### 2. User Interface: Model-Driven Application (`IT Management Portal`)
* Custom Site Map (`IT Management Portal` Navigation) configured for back-office IT admins and tier-1 support engineers.
* Custom views and form layouts enabling rapid incident triage, ticket assignment, and status auditing.
* Responsive desktop & tablet layout driven natively by Dataverse schema boundaries.

### 3. Process Automation: Cloud Flow (`New Ticket Email Alert`)
* **Trigger:** Microsoft Dataverse Connector — `When a row is added, modified or deleted`
  * *Change Type:* `Added`
  * *Table Name:* `IT Tickets`
  * *Scope:* `Organization`
* **Action:** Mail Connector (`V3`) automated notification engine executing instant real-time stakeholder updates upon ticket creation.
* ## 🚀 Deployment & Installation Instructions

### Prerequisites
* A Power Platform environment with **Microsoft Dataverse** enabled.
* **Environment Maker** or **System Customizer** security role.

### Import Steps (Power Apps Maker Portal)
1. Clone or download this repository as a `.zip` file.
2. Sign in to the **[Power Apps Maker Portal](https://make.powerapps.com)**.
3. Select your target Dataverse Environment.
4. Navigate to **Solutions** on the left menu $\rightarrow$ Click **Import solution**.
5. Browse and select the repository archive (`.zip`).
6. Click **Next**, map connection references for the **Mail / Power Automate Connector**, and click **Import**.
7. Once imported, click **Publish all customizations**.

---

## 💡 Key Skills & Engineering Principles Demonstrated
* **Database Modeling:** Custom table schema design, data typing, and choices setup in Dataverse.
* **User Experience Design:** Building Model-Driven Apps, configuring Site Maps, and optimizing back-office admin layouts.
* **Workflow Automation:** Constructing event-driven triggers and automated notification workflows via Power Automate.
* **Application Lifecycle Management (ALM):** Solution packaging, environment separation, component dependency mapping, and GitHub source control versioning.

---
*Maintained by Arun Teja — Power Platform & IT Solutions Portfolio*
