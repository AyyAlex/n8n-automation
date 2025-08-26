# 🚀 Automation Workflows

This file contains two production-ready **n8n automation workflows** that support business operations:

1. **AI SEO Page Analysis** – Automatically pulls data from Google Search Console and generates AI-driven SEO insights and reports.  
2. **Quotation Automation** – Generates client quotations automatically, formats them into PDFs, and sends them via WhatsApp or Email.

---

## 📊 Workflow 1: AI SEO Page Analysis

### Overview
- Automatically queries **Google Search Console API** for multiple time ranges:
  - Last 1 month
  - Previous month
  - 3 months ago
  - 6 months ago
  - Same month last year
- Aggregates SEO metrics: **Impressions, Clicks, CTR, Average Position**.
- Uses **OpenAI GPT-5** and **DeepSeek** to create a detailed SEO report, including:
  - Best / worst performing pages
  - Hidden opportunities
  - Seasonal trends
  - Competitor insights
  - Actionable recommendations (quick wins, medium-term, long-term)
- Sends the report automatically through **Wassenger (WhatsApp API)**.

### Key Nodes
- `Schedule Trigger` → Run monthly  
- `HTTP Request` → Fetch GSC data  
- `Set / Merge / Summarize` → Process results  
- `AI Agent (OpenAI/DeepSeek)` → Generate SEO report (English or Chinese output)  
- `Wassenger` → Send to WhatsApp  

---

## 💼 Workflow 2: Quotation Automation

### Overview
- Accepts client input (product, quantity, printing/embroidery options).  
- Automatically calculates quotation (supports formulas, price adjustments, multi-currency).  
- Generates a **PDF quotation** including company logo, product details, and pricing.  
- Sends quotation via:
  - **Email Node** → Direct to client email  
  - **Wassenger Node** → WhatsApp instant delivery  

### Key Nodes
- `Webhook / Form Trigger` → Receive client request  
- `Code` → Calculate total price  
- `Google Docs / PDF Generator` → Create formatted quotation  
- `Email / Wassenger` → Send to client  

---

## ⚙️ Requirements
- **n8n** (>=1.60 recommended)  
- **Google Search Console API** (OAuth2)  
- **OpenAI API key** / **DeepSeek API key**  
- **Wassenger API key** (WhatsApp integration)  
- **SMTP credentials** (if using Email delivery)  

---



## 🔑 How to Use
1. Import the JSON workflow(s) into your n8n instance.  
2. Configure credentials:
   - Google OAuth2 (connect to Search Console)  
   - OpenAI / DeepSeek API key  
   - Wassenger API key  
   - SMTP (optional, for email delivery)  
3. Run the workflow(s) with test data.  
4. Enable scheduling for production use.  

---

## 📈 Future Improvements
- Export SEO reports to **Google Docs** or **Notion**.  
- Sync quotations automatically to **Supabase / Google Drive**.  
- Add a real-time dashboard (Grafana / Metabase) for monitoring.  

---

