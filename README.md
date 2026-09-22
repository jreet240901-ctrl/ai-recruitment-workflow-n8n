# 🤖 AI Recruitment Workflow & Resume Screening System

An end-to-end **AI-powered recruitment automation system** built with **n8n, OpenAI, Google Workspace, and Telegram** to automate candidate intake, resume management, AI-based screening, candidate tracking, and HR queries.

---

## 📌 Project Overview

Recruitment teams often spend significant time manually reviewing applications, downloading resumes, extracting candidate information, maintaining screening records, and responding to repetitive HR queries.

This project automates the recruitment workflow from **candidate application to AI-powered resume screening and HR decision support**.

The system connects application data, resumes, AI agents, cloud storage, email automation, candidate tracking, and an HR assistant into one integrated workflow.

---

## 🎯 Problem Statement

Traditional recruitment processes involve several repetitive activities:

* Manually checking new applications
* Sending acknowledgement emails
* Downloading candidate resumes
* Organizing resumes into folders
* Reading and extracting resume information
* Comparing resumes with the applied job role
* Rating candidates manually
* Maintaining candidate screening records
* Searching candidate information repeatedly

This workflow reduces these repetitive tasks through **workflow automation and AI-assisted recruitment screening**.

---

## 💡 Solution

The system uses **n8n as the automation engine** and integrates AI into the recruitment process.

### Automated Process

```text
Candidate Application
        ↓
Google Sheets Trigger
        ↓
AI Application Acknowledgement
        ↓
Automated Email
        ↓
Resume Link Extraction
        ↓
Resume Download
        ↓
Google Drive Storage
        ↓
Resume Text Extraction
        ↓
AI Resume Screening Agent
        ↓
Candidate Rating & Classification
        ↓
Candidate Tracker
        ↓
Telegram HR Assistant
```

---

## ⚙️ Key Features

### 1. Automated Candidate Intake

New candidate applications are automatically detected from Google Sheets.

The workflow captures information such as:

* Candidate Name
* Applied Role
* Contact Number
* Email Address
* Resume
* Application details

---

### 2. AI-Powered Application Acknowledgement

An AI-powered workflow generates an acknowledgement message and automatically sends an email to the applicant.

This eliminates the need for HR teams to manually respond to every application.

---

### 3. Automated Resume Management

The workflow automatically:

1. Extracts the resume link from the application
2. Downloads the resume
3. Stores the resume in Google Drive
4. Retrieves the stored resume
5. Extracts the resume text for AI analysis

---

### 4. AI Resume Screening

The **AI Resume Screening Agent** evaluates the candidate's resume against the **position applied for**.

The AI analyzes the available resume information and generates:

* Candidate Name
* Applied Role
* Contact
* Email
* Rating
* Screening Result
* Short Reason / Remarks

### Screening Scale

| Rating | Classification  |
| ------ | --------------- |
| 9–10   | Excellent Match |
| 7–8    | Good Match      |
| 5–6    | Average Match   |
| 3–4    | Weak Match      |
| 0–2    | Not Suitable    |

The workflow uses the screening result to categorize candidates as:

```text
Rating ≥ 7       → Selected
Rating 5–6.9     → Hold
Rating < 5       → Rejected
```

---

## 📊 Candidate Tracking

Screening results are automatically recorded in a centralized candidate tracker.

### Candidate Tracker Fields

```text
Name
Role Applied
Contact No.
Gmail
Rating
Result
Remarks
```

This provides HR teams with a structured view of screened candidates.

---

## 🤖 HR Telegram Assistant

The project also includes an **AI-powered Telegram HR Assistant**.

HR can query the candidate tracker using natural language.

For example:

```text
Who has the highest rating?

Show candidates with rating above 7.

Show all selected candidates.

Find candidates who applied for Finance.

Give me the contact details of a candidate.

Show the screening result of a particular candidate.

Give me a summary of the candidates.
```

The AI assistant retrieves information from the candidate tracker and provides the relevant response.

---

## 🧠 AI & Automation Architecture

```text
                    ┌─────────────────────┐
                    │ Candidate Application │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │ Google Sheets Trigger│
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │ AI HR Assistant      │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │ Gmail Automation     │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │ Resume Extraction    │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │ Google Drive         │
                    │ Resume Storage       │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │ PDF Text Extraction  │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │ AI Resume Screening  │
                    │ Agent                │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │ Rating + Result +    │
                    │ Remarks              │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │ Candidate Tracker    │
                    └─────────────────────┘


             HR Query
                 ↓
        ┌──────────────────┐
        │ Telegram Trigger │
        └────────┬─────────┘
                 ↓
        ┌──────────────────┐
        │ HR Query AI Agent│
        └────────┬─────────┘
                 ↓
        ┌──────────────────┐
        │ Candidate Tracker│
        └────────┬─────────┘
                 ↓
        ┌──────────────────┐
        │ HR Response      │
        └──────────────────┘
```

---

## 🛠️ Technology Stack

| Technology         | Purpose                           |
| ------------------ | --------------------------------- |
| **n8n**            | Workflow automation               |
| **OpenAI**         | AI agents and resume analysis     |
| **Google Sheets**  | Application & candidate tracker   |
| **Google Drive**   | Resume storage                    |
| **Gmail**          | Automated applicant communication |
| **Telegram**       | HR assistant interface            |
| **AI Agents**      | Resume screening & HR queries     |
| **PDF Extraction** | Resume text processing            |

---

## 📁 Repository Structure

```text
ai-recruitment-workflow-n8n/
│
├── README.md
│
├── workflows/
│   └── automated-recruitment-ai-resume-screening.json
│
├── screenshots/
│   ├── recruitment-workflow.png
│   ├── ai-resume-screening.png
│   ├── candidate-tracker.png
│   └── telegram-hr-assistant.png
│
├── docs/
│   └── setup-guide.md
│
└── .gitignore
```

---

## 🔧 n8n Workflow

The complete n8n workflow is available in the repository:

👉 **[View / Download Workflow JSON](./workflows/automated-recruitment-ai-resume-screening.json)**

The workflow can be imported into n8n and configured with the required credentials and services.

---

## 🚀 Setup

### Step 1 — Import Workflow

Open n8n and import:

```text
workflows/automated-recruitment-ai-resume-screening.json
```

### Step 2 — Connect Credentials

Configure your own credentials for:

* OpenAI
* Google Sheets
* Google Drive
* Gmail
* Telegram

### Step 3 — Configure Google Sheets

Connect the candidate application sheet and candidate screening tracker.

### Step 4 — Configure Google Drive

Create/configure the folder used for storing candidate resumes.

### Step 5 — Configure AI Screening

Set the required AI model and screening instructions.

### Step 6 — Configure Telegram

Connect the Telegram bot and HR query workflow.

### Step 7 — Test the Workflow

Submit a test candidate application and verify:

```text
Application
      ↓
Acknowledgement
      ↓
Resume Storage
      ↓
AI Screening
      ↓
Candidate Tracker
      ↓
HR Query
```

### Step 8 — Activate

After successful testing, activate the n8n workflow.

---

## 📸 Project Screenshots

Screenshots can be added to the `screenshots/` folder.

Recommended screenshots:

### Workflow Architecture

![Recruitment Workflow](./screenshots/recruitment-workflow.png)

### AI Resume Screening

![AI Resume Screening](./screenshots/ai-resume-screening.png)

### Candidate Tracker

![Candidate Tracker](./screenshots/candidate-tracker.png)

### Telegram HR Assistant

![Telegram HR Assistant](./screenshots/telegram-hr-assistant.png)

---

## 📈 Business Value

This project demonstrates how AI and workflow automation can support recruitment operations by:

* Reducing repetitive manual tasks
* Automating candidate communication
* Centralizing resume management
* Standardizing initial resume screening
* Maintaining structured candidate records
* Enabling faster candidate information retrieval
* Providing an AI interface for HR queries

The system is designed as an **AI-assisted recruitment workflow**, with human HR teams remaining responsible for final recruitment decisions.

---

## 🔐 Security & Privacy

This repository should not contain:

* Real candidate resumes
* Personal candidate information
* API keys
* Passwords
* Private credentials
* Production database credentials
* Confidential company information

Use sample or anonymized data when demonstrating the project publicly.

---

## 🎓 Project Focus

```text
AI Automation
Workflow Automation
AI Agents
Recruitment Technology
Resume Screening
HR Technology
Business Process Automation
No-Code / Low-Code Automation
```

---

## 👩‍💻 My Role

I designed and implemented the workflow architecture, including:

* Recruitment workflow automation
* AI-based resume screening logic
* Resume processing pipeline
* Candidate tracking system
* Automated applicant communication
* HR Telegram assistant
* Integration between AI, Google Workspace and n8n

---

## ⭐ Project Highlights

**End-to-End AI Recruitment Automation**

From:

> **Candidate Application → Resume Processing → AI Screening → Candidate Tracking → HR Query Assistant**

This project demonstrates the practical application of **AI Agents + Workflow Automation + Business Process Automation** in an HR/recruitment environment.

---

## 📌 Author

**Jaspreet Kaur**

M.Com | Finance & AI Automation

Areas of Interest:

**AI Automation • Finance • Business Analytics • AI Agents • Workflow Automation**
