# MATalogics Day 14–17 — SQL Database Development Knowledge

## Overview

This repository contains my completed work for the **MATalogics AI Automation Internship — Day 14–17: SQL Database Development Knowledge**.

The assignment focused on developing practical knowledge of:

* PostgreSQL
* SQL
* Database design
* Primary and foreign keys
* Database relationships
* CRUD operations
* Sales and lead analytics
* AI-powered CRM database design
* AI customer support database design
* n8n automation
* PostgreSQL + Supabase integration
* AI-powered lead qualification
* Customer conversation memory
* Natural Language to SQL
* Automated database reporting

The practical work progressed from basic SQL and database concepts to complete **AI automation workflows using n8n, PostgreSQL, Supabase, AI models, and Slack**.

---

# Phase 1 — Learning & Preparation

Before starting the practical tasks, the required PostgreSQL, SQL, database, and Supabase learning material was reviewed.

The learning topics included:

* PostgreSQL fundamentals
* PostgreSQL installation
* SQL fundamentals
* Creating databases
* Database concepts
* Connecting n8n with Supabase
* Using Supabase PostgreSQL with n8n

---

# Phase 2 — Install & Setup

The database environment was prepared for the practical tasks.

The following concepts were studied and applied:

* Server
* Database
* Schema
* Table
* Row
* Column
* Data Type
* Primary Key
* Foreign Key
* NULL
* Relationships
* CRUD operations
* SQL queries

The practical environment used **PostgreSQL, Supabase, and n8n**.

---

# Phase 3 — SQL Practical Tasks

## Task 1 — Lead Management Database

A lead management database was created using PostgreSQL.

### Lead Table

The lead table contains fields including:

| Column     | Purpose                 |
| ---------- | ----------------------- |
| id         | Unique lead identifier  |
| name       | Lead name               |
| email      | Lead email              |
| phone      | Lead phone number       |
| company    | Company name            |
| source     | Lead acquisition source |
| lead_score | Lead score              |
| status     | Lead status             |
| created_at | Lead creation timestamp |

### SQL Operations

The following SQL operations were performed:

1. Create the leads table
2. Insert at least 10 leads
3. Display all leads
4. Display qualified leads
5. Display leads with a score greater than 70
6. Update a lead's status
7. Delete a lead
8. Display the top 5 leads according to lead score

### SQL Concepts Demonstrated

* CREATE TABLE
* INSERT
* SELECT
* WHERE
* UPDATE
* DELETE
* ORDER BY
* LIMIT

SQL queries and execution screenshots are included in the repository.

---

# Task 2 — SQL Sales Analytics

The lead database was used to perform sales and lead analytics.

The following questions were answered using SQL:

### Question 1 — Total Leads

The total number of leads was calculated using:

```sql
COUNT()
```

### Question 2 — Leads by Status

Lead counts were calculated for:

* New
* Contacted
* Qualified
* Converted
* Lost

### Question 3 — Average Lead Score

The average lead score was calculated using:

```sql
AVG()
```

### Question 4 — Highest Scoring Lead

The lead with the highest score was identified using:

```sql
ORDER BY
```

### Question 5 — Leads by Source

Lead counts were grouped according to their source using:

```sql
GROUP BY
```

Examples of lead sources include:

* Facebook
* LinkedIn
* Website
* Google
* Referral

### Question 6 — Leads Between Score 50 and 80

Leads with scores between 50 and 80 were retrieved and sorted from highest to lowest using:

```sql
BETWEEN
ORDER BY
```

### SQL Concepts Demonstrated

* SELECT
* WHERE
* ORDER BY
* LIMIT
* COUNT()
* AVG()
* GROUP BY
* BETWEEN

---

# Phase 4 — Database Design on Paper

Database structures were designed on paper before implementing the automation workflows.

The designs included:

* Tables
* Columns
* Data types
* Primary keys
* Foreign keys
* Relationships
* One-to-many relationships
* ER-style database diagrams

---

# Task 3 — AI Automation CRM

A database design was created for an **AI-powered CRM for a digital marketing agency**.

The system is designed to receive leads from:

* Website
* Facebook
* Instagram
* LinkedIn
* WhatsApp

The AI system analyzes leads and assigns:

* Lead score
* Lead status
* Lead category

### Core Tables

The database design includes:

* Customers
* Leads
* Conversations
* Messages

The relationships between customers, leads, conversations, and messages were represented using primary and foreign keys.

An ER-style database diagram is included in the screenshots.

---

# Task 4 — AI Customer Support Knowledge System

A complete database structure was designed for an **AI Customer Support Agent**.

The system is designed to store:

* Customer information
* Support tickets
* Conversations
* Messages
* Products
* Orders
* FAQs

The database relationships allow an AI support agent to access previous customer conversations and order information when responding to customer requests.

The design also supports questions such as:

> "What was my previous order and why was my support ticket opened?"

The required tables, columns, primary keys, foreign keys, relationships, and ER-style diagram are included in the repository.

---

# Phase 5 — n8n + PostgreSQL + Supabase

The final phase connected database development with practical AI automation.

The automation architecture used:

```text
n8n
  ↓
PostgreSQL
  ↓
Supabase
  ↓
AI / Automation
```

The workflows demonstrate how data can move between n8n, PostgreSQL, Supabase, and AI services.

---

# Task 5 — Lead Capture Automation

## Objective

A lead capture automation was developed to receive new leads through an n8n webhook.

### Workflow

```text
Webhook
   ↓
Validate Lead
   ↓
PostgreSQL
   ↓
Supabase
   ↓
Response
```

### Lead Information

The workflow receives:

* Name
* Email
* Phone
* Company
* Message
* Source

### Automation Features

The workflow:

1. Receives the lead through a webhook.
2. Validates required fields.
3. Inserts the lead into PostgreSQL.
4. Stores/synchronizes the lead in Supabase.
5. Returns a successful response.
6. Handles invalid or missing data.

Screenshots of the n8n workflow, PostgreSQL table, Supabase table, successful execution, and SQL used are included.

---

# Task 6 — AI Lead Qualification + Database

## Objective

An AI-powered lead qualification workflow was developed to analyze incoming leads.

The AI determines:

* Lead score
* Lead status
* Lead category

### Workflow

```text
Webhook
   ↓
AI Agent
   ↓
Analyze Lead
   ↓
PostgreSQL
   ↓
Supabase
   ↓
CRM Record
```

### Example AI Analysis

```text
Lead Score: 87
Status: Qualified
Category: High Intent
```

The workflow stores both the original lead information and the AI-generated analysis in the database.

The final record is stored in both PostgreSQL and Supabase.

An IF-based qualification branch can also be used to identify leads with a score of 70 or above.

---

# Task 7 — AI Customer Conversation Memory

## Objective

A persistent customer conversation memory system was developed using PostgreSQL and Supabase.

### Workflow

```text
Chat / Webhook
      ↓
Find Customer
      ↓
PostgreSQL / Supabase
      ↓
Retrieve Previous Messages
      ↓
AI Agent
      ↓
Generate Response
      ↓
Save New Message
```

The system stores:

* Customer information
* Previous questions
* Previous answers
* Previous conversations
* Current conversation

The database is used as persistent memory rather than relying only on temporary AI conversation memory.

### Test Scenario

Initial message:

> "My name is Ahmed and I need help with my order."

Later question:

> "What is my name?"

The system retrieves the customer's name from the persistent database.

---

# Task 8 — Natural Language → SQL AI Agent

## Objective

An AI-powered database assistant was developed that allows a business user to ask database questions using normal English.

### Workflow

```text
User Question
      ↓
AI Agent
      ↓
Generate SQL
      ↓
PostgreSQL
      ↓
Supabase
      ↓
Database Result
      ↓
AI
      ↓
Human-readable Answer
```

### Supported SQL Operations

The AI agent was designed to generate safe read-only SQL for:

* SELECT
* WHERE
* ORDER BY
* COUNT
* AVG
* GROUP BY

### Example Questions

Examples tested include:

* How many leads are there?
* Show me the top 5 leads.
* How many qualified leads came from Facebook?
* What is the average lead score?
* Show leads grouped by source.

### Security

The workflow includes an SQL safety check to prevent destructive database operations.

Destructive operations such as:

```text
DROP TABLE
DELETE
TRUNCATE
```

are blocked.

### Test Results

The workflow successfully handled:

* COUNT queries
* AVG queries
* WHERE + COUNT queries
* ORDER BY queries
* GROUP BY queries
* Unsafe SQL security testing

The security test confirmed that an unsafe SQL request was blocked instead of being executed.

---

# Task 9 — Automated Database Reporting

## Objective

An automated daily lead reporting workflow was developed to collect database information, calculate business statistics, generate an AI summary, and deliver the report through Slack.

### Workflow

```text
Schedule Trigger
       ↓
PostgreSQL Report Data
       ↓
Supabase Leads
       ↓
Calculate Metrics
       ↓
AI Report Generator
       ↓
Slack
```

### PostgreSQL

PostgreSQL is used to calculate:

* Total Leads
* New Leads
* Qualified Leads
* Converted Leads
* Average Lead Score

The reporting query uses SQL aggregation functions such as `COUNT()` and `AVG()`.

### Supabase

Supabase retrieves the individual lead records from the `lead_qualification` table.

This data is used to calculate:

* Top Lead Source
* Top 5 Leads

### Calculate Metrics

An n8n Code node combines the PostgreSQL statistics and Supabase lead records.

It calculates:

* Total Leads
* New Leads
* Qualified Leads
* Converted Leads
* Average Lead Score
* Top Lead Source
* Top 5 Leads
* Conversion Rate

### AI Report Generation

The calculated metrics are passed to an AI model, which generates a concise business report using only the provided data.

### Slack Delivery

The final report is automatically sent to the Slack channel:

```text
#daily-lead-reports
```

### Test Result

The successful test generated a report containing:

```text
Daily Lead Report

Total Leads: 1
New Leads: 0
Qualified Leads: 1
Converted Leads: 0
Average Lead Score: 75
Top Lead Source: Website
Conversion Rate: 0%

Top Lead:
Ahmed Khan — Ahmed Tech Solutions — Score: 75 — Status: Qualified
```

The successful Slack delivery confirms the complete reporting flow from database retrieval to AI-generated business reporting.

---

# Database & Automation Architecture

The overall practical architecture developed during the assignment can be summarized as:

```text
                ┌─────────────────┐
                │      n8n        │
                │   Automation    │
                └────────┬────────┘
                         │
             ┌───────────┴───────────┐
             ↓                       ↓
      ┌──────────────┐       ┌──────────────┐
      │ PostgreSQL   │       │   Supabase   │
      │   Database   │       │   Database   │
      └──────┬───────┘       └──────┬───────┘
             │                       │
             └───────────┬───────────┘
                         ↓
                  ┌──────────────┐
                  │ AI / LLM     │
                  │ Processing   │
                  └──────┬───────┘
                         ↓
                  ┌──────────────┐
                  │ Automation   │
                  │ / Slack      │
                  └──────────────┘
```

---

# Technologies Used

| Technology | Purpose                                      |
| ---------- | -------------------------------------------- |
| PostgreSQL | Relational database and SQL queries          |
| pgAdmin    | PostgreSQL database management               |
| Supabase   | Cloud database and PostgreSQL backend        |
| n8n        | Workflow automation                          |
| AI / LLM   | Lead analysis, SQL generation, and reporting |
| JavaScript | Data transformation and metric calculation   |
| Slack      | Automated report delivery                    |

---

# Deliverables Included

## SQL Tasks

* SQL queries
* SQL execution screenshots
* Database/table screenshots
* Lead management operations
* Sales analytics results

## Paper Database Tasks

* Database structures
* Tables
* Columns
* Data types
* Primary keys
* Foreign keys
* Relationships
* ER-style diagrams
* AI CRM database design
* AI customer support database design

## n8n Tasks

For Tasks 5–9:

* n8n workflow screenshots
* PostgreSQL screenshots
* Supabase screenshots
* Successful execution screenshots
* SQL queries used
* Exported n8n workflow JSON files

---

# Repository Structure

```text
Day-14-17/
│
├── README.md
│
├── SQL-Queries/
│   ├── Task-01-Lead-Management.sql
│   └── Task-02-Sales-Analytics.sql
│
├── n8n-Workflows/
│   ├── Task-05-Lead-Capture.json
│   ├── Task-06-AI-Lead-Qualification.json
│   ├── Task-07-Customer-Conversation-Memory.json
│   ├── Task-08-Natural-Language-to-SQL.json
│   └── Task-09-Automated-Database-Reporting.json
│
└── Screenshots/
    ├── Phase-2/
    ├── Task-01/
    ├── Task-02/
    ├── Task-03/
    ├── Task-04/
    ├── Task-05/
    ├── Task-06/
    ├── Task-07/
    ├── Task-08/
    └── Task-09/
```

---

# Conclusion

The MATalogics Day 14–17 assignment provided practical experience in moving from fundamental SQL and database concepts to AI-powered database automation.

The completed work demonstrates practical understanding of **PostgreSQL, SQL queries, relational database design, Supabase, n8n automation, AI agents, persistent conversation memory, natural-language database querying, SQL safety, lead qualification, and automated business reporting**.

The final workflows demonstrate how database systems can be integrated with AI and automation platforms to create practical business solutions.
