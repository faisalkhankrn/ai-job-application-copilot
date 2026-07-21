# Setup Guide

## Prerequisites

- An n8n installation or n8n Cloud workspace
- A Google account
- A Google Sheet used as the job tracker
- Gmail access for approved outreach workflows
- Access to a suitable job API
- An LLM credential for workflows that use AI nodes

## Step 1 — Prepare the tracker

Create columns such as:

- Job Title
- Company
- Location
- Job URL
- Date Posted
- Fit Score
- Shortlist Status
- CV Status
- Contact Status
- Application Status
- Last Updated

Use the job URL as the duplicate-matching key.

## Step 2 — Configure credentials

Create credentials inside n8n rather than typing secrets directly into workflow nodes.

Recommended credentials:

- Google Sheets OAuth
- Gmail OAuth
- Job API authentication, when required
- LLM provider credentials

## Step 3 — Import workflow exports

1. Open n8n.
2. Create a new workflow.
3. Choose the workflow import option.
4. Select the sanitised JSON export.
5. Reconnect your own credentials.
6. Replace example spreadsheet and folder IDs.
7. Review every node before execution.

## Step 4 — Test safely

- Run with sample data first.
- Keep email nodes disabled during initial testing.
- Confirm duplicate handling.
- Confirm that no private data appears in logs.
- Check the false and true branches separately.
- Activate schedules only after manual testing.

## Step 5 — Add screenshots

Useful screenshots include:

- Full workflow overview
- Filtering code node
- Google Sheets output
- Structured job-fit result
- Draft CV output
- Test email received

Blur personal information before saving screenshots.
