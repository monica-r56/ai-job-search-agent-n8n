# ⚙️ Setup Guide

Follow these steps to run the workflows.

---

## Prerequisites

- n8n (Self-hosted or Cloud)
- Google Account
- Gemini API Key

---

## Step 1 — Import Workflows

Import both workflow JSON files into n8n.

- `resume-search-generator.json`
- `automated-job-search-workflow.json`

---

## Step 2 — Configure Credentials

Create the following credentials inside n8n.

### Google Gemini

- Create an API Key from Google AI Studio.
- Add it as a **Google Gemini** credential.

---

### Google Drive

Connect your Google account using OAuth2.

Used for:

- Downloading the resume PDF

---

### Google Docs

Connect your Google account using OAuth2.

Used for:

- Saving generated search filters
- Reading search filters

---

### Google Sheets

Connect your Google account using OAuth2.

Used for:

- Saving job search results

---

## Step 3 — Update Configuration

Open the **Config** node and configure:

| Field | Example |
|--------|---------|
| Max Jobs | 10 |
| Preferred Remote | Remote / Hybrid / On-Site / Blank |
| Easy Apply | Yes / No |

Leave **Preferred Remote** blank if no preference is required.

---

## Step 4 — Update File References

Replace the following with your own files:

- Resume PDF (Google Drive)
- Google Document
- Google Spreadsheet

---

## Step 5 — Run the Resume Workflow

Execute the **Resume Search Generator** once.

This will:

- Read the resume
- Generate personalized search filters
- Save them to Google Docs

---

## Step 6 — Run the Job Search Workflow

Execute the **Automated Job Search Workflow** or enable the schedule.

The workflow will:

- Read search filters
- Search LinkedIn jobs
- Extract job details
- Save results to Google Sheets

---

## Expected Output

The Google Sheet will contain:

- Role
- Company
- Location
- Description
- Apply Link
- Status

---

## Notes

- Use the same Google account for Drive, Docs, and Sheets.
- Make sure all shared files are accessible by the connected account.
- Update the configuration values anytime to customize future searches.