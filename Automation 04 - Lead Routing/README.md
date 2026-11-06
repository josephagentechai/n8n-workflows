# Automation 04: Lead Capture and Routing

Logs each enquiry, blocks spam and duplicates, assigns one rep and replies to the prospect. Reps get a reminder if a lead waits over 24 hours. No AI is used.

## Files

- `Automation 04 - Lead Capture and Routing.json`: the n8n workflow
- `Leads.csv`, `Territories.csv`: blank Google Sheet tabs

## After importing into n8n

This copy has private details removed, so fill these in first:

- Import the .json file into n8n.
- Create a Google Sheet with one tab per .csv file in this folder, named exactly as the file (for example, `Leads.csv` becomes a tab called Leads).
- Paste your Google Sheet ID over `PASTE_YOUR_GOOGLE_SHEET_ID` in all 5 Google Sheets nodes.
- Paste your email over `PASTE_YOUR_TEST_EMAIL` in **Config** and **Reminder Config**.
- Connect your Google Sheets account and your Gmail account in all four Gmail nodes.
- If you use Automation Error Alert, choose it as the Error Workflow in this workflow's settings.

## Set up

1. In **Config**, enter company_name and the fallback rep.
2. Add your reps to **Territories**. A blank postal_prefix covers the whole country.

## Test

1. Keep test_mode on in **Config** and **Reminder Config**, so every email goes to test_email.
2. Add a Singapore rep with postal_prefix 4 to **Territories**.
3. Submit the form with a Singapore postal code starting with 4. It should go to that rep.
4. Submit again with the same email. It should show as Duplicate.

## Go live

1. Publish Automation Error Alert first.
2. Set test_mode to false in both Config nodes, then publish this workflow.
3. Share the Production URL from **Lead Form**.
4. Ask reps to set status to Contacted in the **Leads** tab after each call.
