# n8n Workflows

My n8n automation workflows, with one folder per workflow. None of them use AI.

## Workflows

| Workflow | What it does |
|---|---|
| [Automation 01: Leave Application](<Automation 01 - Leave Application/README.md>) | Checks leave requests and asks the manager to approve |
| [Automation 02: Invoice Reminders](<Automation 02 - Invoice Reminders/README.md>) | Sends staged reminders for overdue invoices |
| [Automation 03: Low-Stock Reorder](<Automation 03 - Low-Stock Reorder/README.md>) | Emails a draft purchase order when stock runs low |
| [Automation 04: Lead Capture and Routing](<Automation 04 - Lead Routing/README.md>) | Logs enquiries and assigns each one to a rep |
| [Automation 05: Feedback Logging and Escalation](<Automation 05 - Feedback Register/README.md>) | Logs feedback and escalates low ratings |
| [Automation Error Alert](<Automation Error Alert/README.md>) | Sends a Telegram alert when a workflow fails |

## What each folder contains

- The workflow as a .json file, ready to import into n8n
- A README with set-up and test steps
- Blank .csv templates for the Google Sheet tabs, with column headings only

Automation Error Alert has no spreadsheet, so its folder has no .csv files.

## Before you use these files

Private details have been removed from the .json files. The README in each folder lists what to fill in after importing. Set up Automation Error Alert first, because the other workflows use it to report failures.

## Licence

Shared under the MIT licence. See the LICENSE file.
