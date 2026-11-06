# Automation Error Alert

Sends a Telegram message when Automation 01 to 05 fails, with the workflow name, failed node, error and a link to the run.

## Files

- `Automation Error Alert.json`: the n8n workflow

## After importing into n8n

This copy has private details removed, so fill these in first:

- Import the .json file into n8n.
- Paste your chat ID over `PASTE_YOUR_TELEGRAM_CHAT_ID` in **Send Failure Alert**.
- Select your Telegram credential in **Send Failure Alert**.

## Set up

1. Publish this workflow. An unpublished error workflow cannot run.

## Test

1. Error alerts run only for published workflows, not for test runs. To check it, publish a workflow, make it fail on purpose, and look for the Telegram message.
