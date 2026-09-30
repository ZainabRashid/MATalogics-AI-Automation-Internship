# AI Client Onboarding System

## 📌 Overview

This project is a complete **AI-powered client onboarding automation system** designed to automate the process of collecting, analyzing, storing, and notifying the team about new clients.

The system uses a **Vapi Voice Agent** to collect client information, sends the data to **n8n** for AI-powered processing and classification, and then automatically creates records in **Airtable**, onboarding pages in **Notion**, and notifications in **Slack**.

### Workflow

**Client → Vapi Voice Agent → n8n Webhook → AI Processing → Airtable + Notion + Slack**

---

## 🎯 Objective

The objective of this project is to build an end-to-end business automation that:

* Collects client information through a voice conversation
* Identifies and classifies the client's requested service
* Determines lead priority based on project budget
* Generates an AI summary
* Recommends the next action for the team
* Stores client information in Airtable
* Creates an onboarding page in Notion
* Sends a priority-based notification to Slack

---

## 🛠️ Technologies Used

* **Vapi** – Voice AI Agent
* **n8n** – Workflow automation and orchestration
* **AI / LLM** – Client request classification and analysis
* **Airtable** – Client database
* **Notion** – Client project and onboarding management
* **Slack** – Team notifications
* **Webhooks** – Communication between Vapi and n8n

---

# 🤖 Vapi Voice Agent

### Agent Name

`Client Onboarding Agent`

The voice agent collects only the following information from the client:

1. Client Name
2. Company Name
3. Email
4. Service Required
5. Project Description
6. Budget

The agent naturally asks for any missing information and submits the collected information to the n8n webhook at the end of the conversation.

---

# ⚙️ n8n Automation Workflow

The n8n workflow receives the client information through a webhook and processes it using AI.

### Processing Steps

1. Receive client information from Vapi
2. Process the client request using AI
3. Classify the requested service
4. Determine lead priority
5. Generate a short summary
6. Recommend the next action
7. Create an Airtable client record
8. Create a Notion onboarding page
9. Send a Slack notification

---

# 🧠 AI Client Classification

The AI generates the following information:

```json
{
  "service_category": "Web & Mobile Development",
  "priority": "High",
  "summary": "Restaurant requires website and mobile ordering application.",
  "next_action": "Schedule technical consultation"
}
```

### Priority Rules

| Budget                | Priority |
| --------------------- | -------- |
| PKR 500,000 or above  | HIGH     |
| PKR 200,000 – 499,999 | MEDIUM   |
| Below PKR 200,000     | LOW      |

---

# 📊 Airtable

Airtable is used as the central client database.

### Table

`Client Onboarding`

### Fields

* Client Name
* Company
* Email
* Service
* Description
* Budget
* Category
* Priority
* Summary
* Status
* Created At

Every new client is automatically added with:

`Status = New`

---

# 📝 Notion

A Notion database named:

`Client Projects`

is used to manage client onboarding and project information.

For every new client, n8n automatically creates a page containing:

```text
ABC Restaurant

Client: Ali
Service: Web & Mobile Development
Budget: PKR 500,000
Priority: HIGH

Summary:
Restaurant requires website and mobile ordering application.

Next Action:
Schedule technical consultation

Status: New
```

---

# 💬 Slack Notifications

The system sends a notification to:

`#new-clients`

### High Priority

```text
HIGH PRIORITY CLIENT

Ali - ABC Restaurant
Service: Web & Mobile Development
Budget: PKR 600,000
Priority: HIGH

AI Summary:
Restaurant requires website and mobile ordering application.

Next Action:
Schedule technical consultation
```

### Medium Priority

```text
MEDIUM PRIORITY CLIENT
```

### Low Priority

```text
STANDARD CLIENT
```

The Slack message changes automatically according to the AI-generated priority.

---

# 🧪 Testing

The system is designed to be tested using three client calls.

### Test 1 — High Priority

**Budget:** PKR 600,000

Expected result:

`HIGH`

### Test 2 — Medium Priority

**Budget:** PKR 300,000

Expected result:

`MEDIUM`

### Test 3 — Low Priority

**Budget:** PKR 100,000

Expected result:

`LOW`

### Expected End-to-End Flow

For each test:

```text
Vapi Call
   ↓
n8n Webhook
   ↓
AI Classification
   ↓
Airtable Record
   ↓
Notion Onboarding Page
   ↓
Slack Notification
```

---

# 📁 Project Structure

```text
AI-Client-Onboarding-System/
│
├── README.md
│
├── n8n/
│   └── AI Client Onboarding Workflow.json
│
├── Vapi/
│   └── Vapi Agent Configuration.json
│
└── Screenshots/
    ├── Airtable/
    ├── Notion/
    ├── Slack/
    └── Vapi/
```

---

# 📸 Screenshots

The screenshots section contains evidence of the completed automation, including:

### Airtable

* Client onboarding table
* Three test clients
* Client data and AI classification

### Notion

* Client Projects database
* Three automatically created onboarding pages

### Slack

* `#new-clients` notifications
* High, Medium, and Low priority messages

### Vapi

* Client Onboarding Agent configuration
* Tool/webhook configuration
* Test call evidence

---

# ✅ Expected Outcome

This automation demonstrates a complete AI-powered business workflow where a client can provide their requirements through a voice conversation and the system automatically:

**Collects → Understands → Classifies → Stores → Creates Onboarding Tasks → Notifies the Team**

The project demonstrates practical integration of **Voice AI, AI classification, workflow automation, databases, project management, and team communication tools** in a single end-to-end business automation.
