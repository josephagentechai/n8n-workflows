# Automation 02: Invoice Reminders

Every weekday at 9am, finds overdue invoices, sends staged reminders and emails finance a summary. No AI is used.

## Files

- `Automation 02 - Invoice Reminders.json`: the n8n workflow
- `Receivables.csv`, `Exceptions.csv`: blank Google Sheet tabs

## After importing into n8n

This copy has private details removed, so fill these in first:

- Import the .json file into n8n.
- Create a Google Sheet with one tab per .csv file in this folder, named exactly as the file (for example, `Receivables.csv` becomes a tab called Receivables).
- Paste your Google Sheet ID over `PASTE_YOUR_GOOGLE_SHEET_ID` in all 3 Google Sheets nodes.
- Paste your email over `PASTE_YOUR_TEST_EMAIL` in **Config**.
- Connect your Google Sheets account and your Gmail account in **Send Reminder** and **Email Finance Summary**.
- If you use Automation Error Alert, choose it as the Error Workflow in this workflow's settings.

## Set up

1. In **Config**, enter finance_email, company_name and paynow_uen.
2. Add your invoices to the **Receivables** tab. Write dates as yyyy-mm-dd and start reminder_count at 0.

## Test

1. Keep test_mode on in **Config**, so every email goes to test_email.
2. Add one overdue test invoice and one with an unreadable due date.
3. Click Execute Workflow.
4. Check for one reminder and one summary, with the bad row listed in **Exceptions**.

## Go live

1. Publish Automation Error Alert first.
2. Set test_mode to false, then publish this workflow.
