# Automation 05: Feedback Logging and Escalation

Logs each feedback form, replies to the customer and alerts the manager about ratings of 2 or below. The manager gets a reminder if a callback is overdue. No AI is used.

## Files

- `Automation 05 - Feedback Logging and Escalation.json`: the n8n workflow
- `Register.csv`: blank Google Sheet tab

## After importing into n8n

This copy has private details removed, so fill these in first:

- Import the .json file into n8n.
- Create a Google Sheet with one tab per .csv file in this folder, named exactly as the file (for example, `Register.csv` becomes a tab called Register).
- Paste your Google Sheet ID over `PASTE_YOUR_GOOGLE_SHEET_ID` in all 3 Google Sheets nodes.
- Paste your email over `PASTE_YOUR_TEST_EMAIL` in **Config** and **Reminder Config**.
- Connect your Google Sheets account and your Gmail account in all four Gmail nodes.
- If you use Automation Error Alert, choose it as the Error Workflow in this workflow's settings.

## Set up

1. In **Config**, enter manager_name, manager_email and company_name.
2. In **Reminder Config**, enter manager_email.

## Test

1. Keep test_mode on in **Config** and **Reminder Config**, so every email goes to test_email.
2. Submit the form with a score of 2. Expect a manager alert and an apology.
3. Submit the form with a score of 4. Expect a thank-you note.

## Go live

1. Publish Automation Error Alert first.
2. Set test_mode to false in both Config nodes, then publish this workflow.
3. Share the Production URL from **Feedback Form** with customers.
4. After each callback, set status to Closed and fill resolved_at in the **Register** tab.
