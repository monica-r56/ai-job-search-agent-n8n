# 🏗️ Architecture

## Overview

This project is built using **n8n** and consists of two independent workflows:

1. **Resume Search Generator**
2. **Automated Job Search Workflow**

The first workflow analyzes the user's resume and generates personalized job search filters. The second workflow uses those filters to search LinkedIn jobs and store the results in Google Sheets.

---

## Workflow 1 – Resume Search Generator

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
Gemini AI
      │
      ▼
Generate Search Filters
      │
      ▼
Google Docs
```

### Responsibilities

- Download the resume
- Extract text from the PDF
- Analyze skills and experience using Gemini
- Generate 3–5 personalized job search filters
- Save the generated filters to Google Docs

---

## Workflow 2 – Automated Job Search

```text
Schedule Trigger
      │
      ▼
Read Search Filters
      │
      ▼
Build LinkedIn Search URLs
      │
      ▼
Search LinkedIn Jobs
      │
      ▼
Extract Job Links
      │
      ▼
Extract Job Details
      │
      ▼
Store Results
```

### Responsibilities

- Run automatically on schedule
- Read saved search filters
- Search LinkedIn jobs
- Extract job information
- Save results to Google Sheets

---

## Systems Used

- n8n
- Google Gemini
- Google Drive
- Google Docs
- Google Sheets
- LinkedIn Public Job Search

---

## Data Flow

```text
Resume
   │
   ▼
Gemini
   │
   ▼
Search Filters
   │
   ▼
LinkedIn Search
   │
   ▼
Job Details
   │
   ▼
Google Sheets
```

---

## Output

The workflow stores the following job details:

- Job Role
- Company
- Location
- Description
- Apply Link
- Status