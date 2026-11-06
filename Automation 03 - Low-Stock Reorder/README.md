# Automation 03: Low-Stock Reorder

Every hour on weekdays, 8am to 6pm, checks stock levels and emails procurement a draft purchase order for low items. No AI is used.

## Files

- `Automation 03 - Low-Stock Reorder.json`: the n8n workflow
- `Inventory.csv`, `Vendors.csv`, `PO Drafts.csv`, `Exceptions.csv`: blank Google Sheet tabs

## After importing into n8n

This copy has private details removed, so fill these in first:

- Import the .json file into n8n.
- Create a Google Sheet with one tab per .csv file in this folder, named exactly as the file (for example, `Inventory.csv` becomes a tab called Inventory).
- Paste your Google Sheet ID over `PASTE_YOUR_GOOGLE_SHEET_ID` in all 6 Google Sheets nodes.
- Paste your email over `PASTE_YOUR_TEST_EMAIL` in **Config**.
- Connect your Google Sheets account and your Gmail account in **Email Procurement PO** and **Email Vendor Missing**.
- If you use Automation Error Alert, choose it as the Error Workflow in this workflow's settings.

## Set up

1. In **Config**, enter procurement_email.
2. Add your items to **Inventory** and your suppliers to **Vendors**. Leave alert_sent and last_alert blank.

## Test

1. Keep test_mode on in **Config**, so every email goes to test_email.
2. Add one low-stock item with a vendor and one without.
3. Click Execute Workflow.
4. Check for one draft PO and one missing-vendor alert.
5. Run it again. No new POs should appear.

## Go live

1. Publish Automation Error Alert first.
2. Set test_mode to false, then publish this workflow.
3. Keep qty_on_hand up to date, because the workflow only sees what is in the Sheet.
