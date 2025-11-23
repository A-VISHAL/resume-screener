🚀 Workflow Overview
1. Gmail Trigger — Start the Automation

The workflow begins when a new email with an attachment is received.
This attachment is assumed to be a candidate’s resume.

Steps:

Detect new incoming email

Fetch the attached resume

Upload it to Google Drive for processing

2. File Type Switch (PDF / DOCX / TXT)

Resumes can arrive in different formats.
The workflow automatically checks the type and routes it correctly:

PDF → Extract PDF Text

DOC / DOCX → Extract Document Text

TXT → Direct text extraction

This ensures all resumes are normalized into raw, readable text.

3. Extract Text From Job Description File

In parallel, the workflow downloads the job requirement document and extracts its text.
This allows the system to compare the resume with the job description.

4. AI Agent — Generate Candidate Insights

Both extracted texts (resume + job description) are sent to an AI Agent.

The AI agent performs:

Candidate profile extraction

Skills matching

Experience analysis

Relevance scoring

Overall fit score from 0–10

The AI returns a structured JSON containing:

Name

Email

Skills

Experience summary

Match score

Recommended decision

5. Information Extractor

The structured AI output is cleaned and formatted for storage.
Fields like:

Candidate Name

Contact Details

Skills

Score

Fit Status

are extracted cleanly.

6. Store Results in Google Sheets

All candidate information is appended into a Google Sheet, creating a growing resume database.

Stored fields include:

Resume Text

Job Description Match

Fit Score

Candidate Summary

Date

7. Telegram Notification (If Fit Score ≥ 7)

After scoring, the workflow checks:

If candidate score >= 7 → send Telegram alert  
Else → no notification  


This ensures only high-potential candidates reach your Telegram channel instantly.

🧩 Workflow Features

✔ Automated resume ingestion
✔ Multi-format document extraction (PDF, DOCX, TXT)
✔ AI-powered structured analysis
✔ Job requirement matching
✔ Automatic data storage
✔ Real-time Telegram notifications
✔ Fully end-to-end automation using n8n

🗂 Tech Stack

n8n workflow automation

Google Drive (file storage)

Google Sheets (database)

Gmail (trigger)

AI Agent (Gemini/OpenAI)

Telegram Bot (notifications)

📌 Purpose

This workflow automates the entire candidate screening process by:

Eliminating manual resume reading

Increasing accuracy with AI

Standardizing candidate evaluation

Saving recruiter time
