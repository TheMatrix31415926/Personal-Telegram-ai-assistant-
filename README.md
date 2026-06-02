# Personal-Telegram-ai-assistant-

# 🚀 AI Personal Assistant for Daily Tasks (n8n + OpenAI)

An intelligent multi-agent AI assistant built with **n8n**, **OpenAI GPT-4o**, **Telegram**, **Google Calendar**, **Gmail**, **Airtable**, and **Tavily Search**.

This assistant acts as a personal productivity companion capable of managing emails, contacts, calendar events, content creation, internet research, and job searches through a single conversational interface.

---

## ✨ Features

### 📩 Email Management

* Send professional emails
* Create email drafts
* Reply to emails
* Retrieve emails
* Manage Gmail labels
* Mark emails as unread

### 📅 Calendar Management

* Create calendar events
* Create events with attendees
* Retrieve upcoming events
* Update existing events
* Delete events

### 👥 Contact Management

* Search contacts
* Add new contacts
* Update contact information
* Store contacts in Airtable

### ✍️ AI Content Creation

* Generate blog posts
* Research topics using Tavily Search
* Produce SEO-friendly HTML articles
* Automatically cite sources

### 🌐 Web Research

* Real-time internet search using Tavily API
* News lookup
* Topic research
* Information gathering

### 💼 Job Search Assistant

* LinkedIn job search integration
* Job discovery automation

### 🎙️ Voice Assistant

* Telegram voice message support
* Speech-to-text transcription using OpenAI Whisper
* Voice and text conversations

### 🧠 Conversational Memory

* Persistent memory per Telegram user
* Context-aware conversations
* Follow-up question handling

---

# 🏗️ Architecture

```text
Telegram User
      │
      ▼
Telegram Trigger
      │
 ┌────┴─────┐
 │          │
Text      Voice
 │          │
 │      Whisper
 │          │
 └────┬─────┘
      ▼
Main AI Agent (GPT-4o)
      │
      ├── Email Agent
      ├── Calendar Agent
      ├── Contact Agent
      ├── Content Creator Agent
      ├── LinkedIn Job Agent
      ├── Tavily Search
      └── Think Tool
```

---

# 🤖 AI Agent System

The project follows a **multi-agent architecture**.

## 1. Main Assistant Agent

Acts as the central orchestrator.

Responsibilities:

* Understand user intent
* Select the correct specialized agent
* Manage memory
* Route requests
* Return responses to Telegram

### Tool Routing Logic

| Request Type          | Tool Used                      |
| --------------------- | ------------------------------ |
| Send Email            | Contact Agent → Email Agent    |
| Draft Email           | Contact Agent → Email Agent    |
| Calendar Event        | Calendar Agent                 |
| Meeting with Attendee | Contact Agent → Calendar Agent |
| Blog Writing          | Content Creator Agent          |
| News Research         | Tavily Search                  |
| Job Search            | LinkedIn Scraper               |

---

## 2. Email Agent

Handles Gmail operations.

### Capabilities

* Send Email
* Create Draft
* Reply to Email
* Get Emails
* Get Labels
* Label Emails
* Mark Unread

### Technologies

* GPT-4o
* Gmail API
* n8n AI Agent

---

## 3. Calendar Agent

Handles Google Calendar operations.

### Capabilities

* Create Events
* Create Events with Attendees
* Update Events
* Delete Events
* Fetch Calendar Events

### Technologies

* GPT-4o
* Google Calendar API

---

## 4. Contact Agent

Stores and retrieves contact information.

### Capabilities

* Search Contacts
* Add Contacts
* Update Contacts

### Database

Airtable

Example Contact Structure:

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "phoneNumber": "+123456789"
}
```

---

## 5. Content Creator Agent

AI-powered blogging assistant.

### Capabilities

* Research topics
* Generate blogs
* Create HTML formatted content
* Add citations
* SEO-friendly writing

### Stack

* GPT-4o Mini
* Tavily Search API

---

## 6. LinkedIn Job Agent

Dedicated workflow for job discovery.

### Capabilities

* Search jobs
* Filter opportunities
* Retrieve job information

---

# 🎙️ Voice Workflow

```text
Telegram Voice Message
        │
        ▼
Download Voice File
        │
        ▼
OpenAI Whisper
        │
        ▼
Transcribed Text
        │
        ▼
Main Assistant
```

This allows users to interact entirely through voice commands.

---

# 🧠 Memory System

The assistant uses n8n's Buffer Memory node.

### Benefits

* Remembers previous messages
* Maintains conversation context
* Supports multi-turn interactions
* Stores memory per Telegram user

Session Key:

```javascript
Telegram Chat ID
```

---

# 🛠️ Technology Stack

| Category            | Technology          |
| ------------------- | ------------------- |
| Workflow Automation | n8n                 |
| LLM                 | GPT-4o              |
| Speech Recognition  | OpenAI Whisper      |
| Messaging Platform  | Telegram            |
| Email               | Gmail API           |
| Calendar            | Google Calendar API |
| Contacts Database   | Airtable            |
| Web Search          | Tavily API          |
| Storage             | Airtable            |
| Memory              | n8n Buffer Memory   |

---

# 📂 Project Structure

```text
AI-Personal-Assistant/
│
├── Ai Assistant for daily task.json
│
├── Email Agent.json
│
├── Calendar Agent.json
│
├── Contact Agent.json
│
├── Content Creator Agent.json
│
└── Linkedin Bot.json
```

---

# ⚙️ Setup Instructions

## 1. Clone Repository

```bash
git clone https://github.com/yourusername/AI-Personal-Assistant.git
```

---

## 2. Import Workflows

Import all JSON files into n8n:

```text
Main Workflow
Email Agent
Calendar Agent
Contact Agent
Content Creator Agent
LinkedIn Agent
```

---

## 3. Configure Credentials

Add:

* OpenAI API Key
* Gmail OAuth
* Google Calendar OAuth
* Telegram Bot Token
* Airtable Token
* Tavily API Key

---

## 4. Activate Workflows

Enable:

```text
Email Agent
Calendar Agent
Contact Agent
Content Creator Agent
LinkedIn Agent
Main Assistant
```

---

## 🚀 Example Commands

### Email

```text
Send an email to John asking for tomorrow's meeting time.
```

### Calendar

```text
Schedule a meeting with Sarah tomorrow at 3 PM.
```

### Contacts

```text
Save Rahul's contact information.
```

### Blog Creation

```text
Write a blog about AI Agents in 2026.
```

### Research

```text
Search the latest AI news.
```

### Jobs

```text
Find Machine Learning Engineer jobs in Bangalore.
```

---

# 🔐 Security Notes

Before publishing:

* Remove API keys
* Remove OAuth credentials
* Remove Airtable IDs
* Remove Telegram Bot Tokens
* Replace personal email addresses with placeholders

Example:

```text
your-email@gmail.com
YOUR_OPENAI_API_KEY
YOUR_TAVILY_API_KEY
```

---

# 🌟 Future Enhancements

* WhatsApp Integration
* Slack Integration
* Multi-user authentication
* RAG Knowledge Base
* Long-term Memory
* CRM Integration
* Lead Generation Agent
* Meeting Summarization
* Autonomous Task Execution

---

# 👨‍💻 Author

**Dewanshu**

AI/ML Engineer | Automation Developer | n8n Builder

### Skills

* AI Agents
* n8n Automation
* OpenAI APIs
* MLOps
* Workflow Orchestration
* Python
* LLM Applications
* Retrieval-Augmented Generation (RAG)

---

⭐ If you found this project useful, consider giving the repository a star.

