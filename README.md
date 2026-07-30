# 🚀 AI-Powered Resume Driven Job Search Automation using n8n

An intelligent n8n automation that analyzes a resume using **Google Gemini**, generates personalized LinkedIn job search filters, searches for matching jobs, extracts job details, and automatically stores them in **Google Sheets** for tracking.

---

## ✨ Features

- 📄 Extracts text from a resume PDF
- 🤖 Uses Google Gemini to analyze skills and experience
- 🎯 Generates personalized job search filters
- 🔎 Searches LinkedIn jobs automatically
- 📌 Extracts job title, company, location, description, and apply link
- 📊 Stores results in Google Sheets
- ⚙️ Fully automated using n8n workflows

---

## 🏗️ Project Architecture

The project consists of **two independent workflows**.

### 1️⃣ Resume Search Generator

Analyzes the resume and creates personalized job search filters.

```text
Resume PDF
     │
     ▼
Google Drive
     │
     ▼
Extract Resume Text
     │
     ▼
Google Gemini
     │
     ▼
Generate Search Filters
     │
     ▼
Google Docs
```

---
## Templates

Copy the Resume template to google docs and Job Tracker template to google sheets in your space.

- 📄 [Job Resume Template](https://docs.google.com/document/d/1AkKWz6a68GOk4Xs31IMEl77G3gTwx-HPfs-nrLgTQEc/edit?usp=sharing)
- 📊 [Job Tracker Template](https://docs.google.com/spreadsheets/d/1mLdMQVrluE9gL_TmCDxWPtMxGWXCBXrGli1fLl3UJfw/edit?usp=sharing)
---

### 2️⃣ Automated Job Search Workflow

Uses the generated filters to search LinkedIn jobs and store the results.

```text
Schedule Trigger
      │
      ▼
Read Search Filters
      │
      ▼
Generate LinkedIn Search URLs
      │
      ▼
Search LinkedIn Jobs
      │
      ▼
Extract Job Details
      │
      ▼
Google Sheets
```

---

## 📂 Repository Structure

```text
.
├── workflows/
│   ├── AI Job Copilot.json
│
├── docs/
│   ├── architecture.md
│   ├── setup-guide.md
|   └── n8n-workshop-credential-setup.pdf
│
└── README.md
```

---

## 🛠️ Tech Stack

- n8n
- Google Gemini
- Google Drive API
- Google Docs API
- Google Sheets API
- LinkedIn Public Job Search
- JavaScript

---

## 📋 Prerequisites

Before running the workflows, configure:

- Google Gemini API Key
- Google Drive OAuth
- Google Docs OAuth
- Google Sheets OAuth

Detailed setup instructions are available in:

📄 **docs/setup-guide.md**

## 🔐 Credentials

For detailed credential setup instructions (Google Gemini, Google Drive, Google Docs, and Google Sheets), refer to the **[Setup Guide](https://docs.google.com/document/d/1_IpNdxmMhWPfoFT0qJvo0sgKCaX_MTBMbyCbul6FVD4/edit?usp=sharing)**.

---

## ⚙️ How It Works

### Resume Search Generator

- Downloads the resume PDF
- Extracts the resume text
- Uses Gemini to understand skills and experience
- Generates 3–5 personalized LinkedIn search filters
- Saves the filters to Google Docs

### Automated Job Search

- Reads the generated search filters
- Builds LinkedIn search URLs
- Searches LinkedIn jobs
- Extracts job details
- Stores results in Google Sheets

---

## 📊 Output

The workflow stores the following information:

- Job Role
- Company
- Location
- Description
- Apply Link
- Status

Example:

| Role | Company | Location | Status |
|------|---------|----------|--------|
| AI Engineer Intern | Company A | Bangalore | NEW |
| Software Engineer Intern | Company B | Remote | NEW |

---

## 📷 Workflow

> Add screenshots inside the `images/` folder.

### Resume Search Generator

```text
images/resume-generator.png
```

### Automated Job Search

```text
images/job-search-workflow.png
```

### Complete Workflow

```text
images/workflow-overview.png
```

---

## 🚀 Getting Started

1. Clone the repository.

```bash
git clone https://github.com/<your-username>/<repository-name>.git
```

2. Import workflow JSON file into n8n.

3. Configure all required credentials.

4. Run the **Resume Search Generator** once.

5. Enable or execute the **Automated Job Search Workflow**.

6. View matching jobs in Google Sheets.

---

## 📚 Documentation

- 📄 docs/architecture.md
- 📄 docs/setup-guide.md

---

## 💡 Future Improvements

- Support multiple job portals
- AI-based job ranking and scoring
- Automatic duplicate detection
- Resume-job matching score
- Email notifications
- Slack or Microsoft Teams integration
- Application tracking dashboard
