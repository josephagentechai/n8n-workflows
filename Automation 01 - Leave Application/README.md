# Automation 01: Leave Application

Checks leave requests against balances and public holidays, asks the manager to approve, then updates the balance. No AI is used.

## Files

- `Automation 01 - Leave Application.json`: the n8n workflow
- `Requests.csv`, `Employees.csv`, `Holidays.csv`: blank Google Sheet tabs

## After importing into n8n

This copy has private details removed, so fill these in first:

- Import the .json file into n8n.
- Create a Google Sheet with one tab per .csv file in this folder, named exactly as the file (for example, `Requests.csv` becomes a tab called Requests).
- Paste your Google Sheet ID over `PASTE_YOUR_GOOGLE_SHEET_ID` in all 11 Google Sheets nodes.
- Paste your email over `PASTE_YOUR_TEST_EMAIL` in **Config**.
- Connect your Google Sheets account and your Gmail account in all six Gmail nodes.
- If you use Automation Error Alert, choose it as the Error Workflow in this workflow's settings.

## Set up

1. In **Leave Form**, create a Basic Auth credential. Staff use this login to open the form.
2. In **Config**, enter hr_email and company_name.
3. Add your staff to the **Employees** tab and your public holidays to the **Holidays** tab. Update the holidays each year.

## Test

1. Keep test_mode on in **Config**, so every email goes to test_email.
2. Add a test employee to the **Employees** tab, using your own email as work_email.
3. Submit the form as that employee, then click Approve in the email.
4. Check that the request shows Approved and the balance has dropped.

## Go live

1. Publish Automation Error Alert first.
2. Set test_mode to false, then publish this workflow.
3. Share the Production URL from **Leave Form** with staff.
