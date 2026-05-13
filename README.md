# n8n-chatwoot-followup-bot

Automated follow-up bot that runs daily at 19h, finds open Chatwoot conversations tagged as **obo**, sends a re-engagement message, waits, then removes the tag.

## How it works

1. **Schedule Trigger** — fires every day at 19h
2. Paginates through all open Chatwoot conversations (up to 8,000)
3. Filters only conversations with the obo label
4. Sends a follow-up message: *"Can you get back to me before the proposal expires?"*
5. Waits 10s between messages to avoid rate limits
6. Removes the obo label after sending

## Stack

- [n8n](https://n8n.io) — workflow automation
- [Chatwoot](https://chatwoot.com) — customer support / WhatsApp messaging
- JavaScript (Code nodes)

## Setup

1. Import workflow.json into your n8n instance
2. Set your Chatwoot credentials:
   - YOUR_CHATWOOT_INSTANCE → your Chatwoot URL
   - YOUR_CHATWOOT_API_TOKEN → your API token
3. Activate the workflow