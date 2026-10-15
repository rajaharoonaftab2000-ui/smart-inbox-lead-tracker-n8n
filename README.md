# Smart Inbox Lead Tracker

An AI-powered email management system built with n8n, Gmail, Google Gemini, Google Sheets, and Telegram.

## Overview

This automation helps businesses organise incoming emails, capture potential leads, log complaints, and prepare replies to customer questions.

Google Gemini classifies incoming emails into Leads, Complaints, Questions, and Spam. Each category follows a separate processing path.

Two companion workflows provide daily activity summaries and workflow error alerts through Telegram.

## Workflow

Incoming Gmail Message → AI Email Classification → Route by Category → Process Email → Save Records or Prepare Draft → Telegram Notification

Depending on the email category, the workflow can:

- Extract and save lead information in Google Sheets.
- Check for duplicate sender email addresses.
- Send a Telegram follow-up reminder.
- Log complaints and notify the owner.
- Generate a Gmail reply draft for review.

## How It Works

1. 📩 **Receive an incoming email**
   The Gmail Trigger detects a new message in the connected inbox.

2. 🤖 **Classify the email**
   Google Gemini categorises the message as a Lead, Complaint, Question, or Spam.

3. 📋 **Extract lead information**
   For lead enquiries, the workflow extracts the customer's name, email address, phone number, and requirements.

4. 🔍 **Check for duplicate leads**
   The workflow checks previously processed email addresses before saving a new lead.

5. 📊 **Save the lead**
   New lead details are recorded in Google Sheets with a status, received timestamp, and follow-up information.

6. 🔔 **Send a follow-up reminder**
   After the configured waiting period, Telegram reminds the owner to follow up with the lead.

7. ⚠️ **Handle complaints**
   Complaint details are saved in a separate sheet, and a Telegram alert notifies the owner.

8. ✍️ **Prepare replies to questions**
   Google Gemini generates a professional English reply and saves it as a Gmail draft for review before sending.

## Companion Workflows

### Daily Report

The daily reporting workflow reads the lead and complaint sheets, counts records received that day, and sends a summary to Telegram.

The summary includes:

- New leads received.
- New complaints received.

### Error Tracker

The error tracking workflow sends a Telegram alert when a connected workflow fails.

The alert includes:

- Workflow name.
- Failed node.
- Error message.

## Features

- 📩 Gmail inbox monitoring
- 🤖 AI-powered email classification
- 📋 Contact details and requirements extraction
- 🔍 Duplicate checking by sender email address
- 📊 Google Sheets lead tracking
- ⚠️ Complaint logging and owner alerts
- ✍️ AI-generated Gmail reply drafts
- 🔔 Telegram follow-up reminders
- 📈 Daily lead and complaint summaries
- 🚨 Workflow error notifications
- ⚙️ Customisable prompts, schedules, and field mappings

## Technologies Used

- **n8n** — Workflow automation and routing
- **Gmail** — Incoming emails and reply drafts
- **Google Gemini** — Classification, information extraction, and reply generation
- **Google Sheets** — Lead tracking and complaint records
- **Telegram** — Alerts, reminders, and daily summaries

## Use Case

This automation is suitable for small businesses, agencies, and service providers that receive customer enquiries through email.

It helps organise potential customers, highlight complaints, and prepare responses while keeping lead records in a central spreadsheet.

The workflow can be adapted to different business categories, enquiry types, and follow-up processes.

## Setup Requirements

- A running n8n instance
- A connected Gmail account
- Google Gemini API access
- Google Sheets with lead and complaint tabs
- A Telegram bot and destination chat
- Configured credentials for each integration

Before testing:

- Update spreadsheet references and field mappings.
- Configure the Telegram destination.
- Review the classification and reply-generation instructions.
- Set the follow-up waiting period.
- Configure the daily reporting schedule and timezone.
- Link the main workflow to the error tracking workflow.

## Testing

1. Send a sample lead enquiry containing contact details and service requirements.
2. Check that the lead appears in Google Sheets.
3. Verify the Telegram follow-up reminder after the configured wait.
4. Send another enquiry from the same email address to check duplicate handling.
5. Send a sample complaint and check the complaint sheet and Telegram alert.
6. Send a business question and check the generated reply in Gmail Drafts.
7. Run the daily reporting workflow and check the Telegram summary.

## Important Notes

- This is a personal portfolio demonstration using sample data.
- Generated replies are saved as drafts and are not automatically sent.
- Duplicate checking uses the sender's email address, so another enquiry from the same address may be filtered out.
- Follow-up reminders do not check whether the owner has already replied.
- Spam is classified, but automatic deletion or archiving is not included.
- AI-generated classifications and replies should be reviewed during testing.
- Each workflow must be configured and activated for its intended use.

## Demo Video

[Watch the Smart Inbox Lead Tracker Demo](./Smart-Inbox-Silent-Captions.mp4)

## Project Status

Completed portfolio demo demonstrating AI email classification, lead tracking, complaint logging, Gmail draft creation, Telegram reminders, daily reporting, and error monitoring.
