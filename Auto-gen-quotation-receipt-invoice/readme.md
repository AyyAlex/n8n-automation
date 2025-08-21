# Auto-Generate Sub-Workflows (n8n)

This folder contains multiple **Auto-Generate** workflows: they copy from a **Google Docs template** and replace **placeholders** with JSON field values.  
These workflows are designed as **sub-workflows**, best used by your **AI Agent / main workflow** through the **Execute Workflow** node.

> ✅ Typical use case:  
> AI Agent receives a request → Main workflow prepares input → `Execute Workflow` triggers one of these sub-workflows → Creates and updates a document in Google Drive → Returns file information (ID, link, filename…)

---

## 📁 Included Workflows (Examples)
- `auto-generate-quotation.json` — Generate quotation documents  
- `auto-generate-invoice.json` — Generate invoices  
- `auto-generate-receipt.json` — Generate receipts  

> Structure is similar: **Copy Google Doc → Replace placeholders → (Optional) Export DOCX/PDF → Return file info**

---

## 🔌 Requirements
- n8n (latest recommended)  
- Google Drive / Google Docs credentials connected in n8n  
- Google Docs templates prepared with placeholders (e.g. `client_name`, `date_date`, `total_amount`…)

---

## 📥 Import & Setup
1. Download `workflows/*.json`  
2. In n8n → **Workflows → Import → From File**  
3. Open the workflow and:  
   - Connect your Google Drive/Docs credentials (credentials are removed in this repo)  
   - Replace `YOUR_GOOGLE_DOC_ID` and `YOUR_GOOGLE_FOLDER_ID` with your own IDs  
4. (Optional) Rename the workflow for easier use when called by your main flow  

---

## 🧩 How to Call as a Sub-Workflow
Use the **Execute Workflow** node in your **main flow**, passing inputs such as:

```json
{
  "phone_number": "SAMPLE_PHONE",
  "client_name": "SAMPLE_CLIENT",
  "product_name": "T-shirt",
  "fabric_and_product_details": "26s 180g White Basic Tee",
  "printing_details": "Front & Back Embroidery 30cm",
  "unit_price": 48.5,
  "qty": 100,
  "deposit_payment": 4000,
  "currentDate": "2025-08-20T00:00:00.000Z"
}
