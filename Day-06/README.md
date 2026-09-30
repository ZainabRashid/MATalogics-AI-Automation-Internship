# Day 06 – Airtable & n8n Automation

## Overview

This project was completed as part of the **MATalogics AI Automation Internship – Day 06** assignment.

The objective was to learn the fundamentals of **Airtable** and understand how it can be used as a structured database for no-code and low-code business automation. The assignment also focused on integrating Airtable with **n8n** to create, update, delete, and search records and to build practical automation workflows.

---

# Module 1 – Airtable Fundamentals

## Airtable Account

An Airtable account was created to explore its database and automation capabilities.

## Key Airtable Concepts

The following concepts were explored:

* Bases
* Tables
* Fields
* Records
* Views
* Forms
* Automations
* Interfaces

## Airtable Base

A base named:

**MATalogics AI Operations**

was created for the practical assignment.

---

# Module 2 – Database Design

The AI Agency database was designed using multiple tables for different business operations.

## 1. Clients

| Field     | Purpose                  |
| --------- | ------------------------ |
| Client ID | Unique client identifier |
| Name      | Client name              |
| Company   | Client company           |
| Email     | Client email             |
| Status    | Client status            |

## 2. Projects

| Field        | Purpose                            |
| ------------ | ---------------------------------- |
| Project Name | Name of the project                |
| Assigned To  | Person responsible for the project |
| Deadline     | Project deadline                   |
| Status       | Current project status             |

## 3. Leads

| Field              | Purpose                           |
| ------------------ | --------------------------------- |
| Lead Name          | Name of the lead                  |
| Source             | Lead source                       |
| Contact Number     | Lead contact number               |
| Interested Service | Service the lead is interested in |

## 4. AI Agents

| Field             | Purpose                   |
| ----------------- | ------------------------- |
| Agent Name        | Name of the AI agent      |
| Type              | Type of AI agent          |
| Deployment Status | Current deployment status |
| Last Updated      | Last update date          |

## 5. Interns

| Field             | Purpose                            |
| ----------------- | ---------------------------------- |
| Intern Name       | Intern name                        |
| Department        | Assigned department                |
| Task Count        | Number of assigned/completed tasks |
| Performance Score | Performance score                  |

---

# Module 3 – Airtable + n8n Integration

Airtable was connected with n8n to understand database-based automation.

The integration covers the following operations:

* Create Record
* Update Record
* Delete Record
* Search Record

This integration demonstrates how Airtable can be used as a central data source for automation workflows.

---

# Module 4 – Automation Workflows

## Workflow 1 – Lead Management

### Flow

**New Lead in Airtable → n8n → Slack Notification**

When a new lead is added to Airtable, n8n processes the record and sends a notification to the relevant Slack channel.

---

## Workflow 2 – Client Onboarding

### Flow

**Airtable Record Created → n8n → Generate Client ID → Notify Team**

When a new client record is created, n8n generates a client identifier and sends a notification to the team.

---

## Workflow 3 – Project Tracking

### Flow

**Project Status Changed → n8n → Email Notification**

When a project status changes, n8n processes the update and sends an email notification.

---

## Workflow 4 – AI Agent Monitoring

### Flow

**AI Agent Status Updated → n8n → Operations Team Notification**

When an AI agent's deployment status is updated, n8n sends a notification to the operations team.

---

## Workflow 5 – Internship Tracker

### Flow

**Task Completed → n8n → Update Performance Score**

When an internship task is completed, the workflow updates the intern's performance information automatically.

---

# Module 5 – Practical Assignment

## AI Agency Database

The practical assignment focuses on building a structured database for an AI agency.

The system includes:

* Client Management System
* Lead Management System
* Project Tracker
* Internship Tracker
* AI Agent Tracker

The database structure demonstrates how Airtable can be used as a central source of business information for automation systems.

---

# Tools & Technologies

* Airtable
* n8n
* Slack
* Email Automation
* No-Code / Low-Code Automation

---

# Learning Outcomes

Through this assignment, I learned:

* Airtable database fundamentals
* Creating and managing bases and tables
* Designing structured database fields
* Working with Airtable views and forms
* Connecting Airtable with n8n
* Creating and updating Airtable records through automation
* Searching and deleting records
* Using Airtable as a central database for business workflows
* Building practical AI agency database systems
* Connecting database events with notifications and automated actions

---

# Conclusion

This project provided practical experience in using **Airtable as a structured business database** and integrating it with **n8n** to create automation workflows.

The resulting database structure covers clients, leads, projects, AI agents, and interns, providing a foundation for building automated AI agency operations.
