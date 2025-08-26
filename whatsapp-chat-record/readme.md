# WhatsApp Chat Workflows — Quick README

This repo includes 3 small n8n workflows to manage WhatsApp chats:

1. **Inbound Logger**  
   - Logs *incoming* WhatsApp messages  
   - Saves to **Google Sheets** + **Supabase**  

2. **Outbound Logger**  
   - Logs *outgoing* WhatsApp messages  
   - Saves to **Google Sheets** + **Supabase**  

3. **Chat Context Fetcher** (this file)  
   - Reads past chat from Supabase by `phone_number`  
   - Builds a clean context string for AI/CS use  
   - Example output:  
     ```
     [client] 2024-08-01 10:15：Hi
     [helios] 2024-08-01 10:16：Hello
     ```

---

## Setup

- Replace placeholders:
  - `YOUR_WEBHOOK_PATH`  
  - `YOUR_GOOGLE_SHEET_ID` / `YOUR_SHEET_GID`  
- Bind credentials in n8n:
  - Google Sheets  
  - Supabase  
  - (Optional) WhatsApp provider API token

---

## Why use

- **Inbound/Outbound** → auto record every message, no copy-paste  
- **Fetcher** → quick conversation history for agents/LLMs  

Together they save hours per day and create a consistent chat log pipeline. 🚀
