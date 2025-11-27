# 🌩️ Meteorological Data Extraction Workflow – Make + OpenAI + Google Sheets

This repository documents a fully operational automation workflow designed to extract meteorological data from a free-form weather bulletin and populate a Google Sheet with structured values. The workflow is powered by OpenAI's Assistants API and implemented on the Make platform.

---

## 🧠 Overview

This pipeline allows you to:
1. Trigger the system manually via webhook (e.g. with Postman).
2. Fetch raw weather text from a Google Document.
3. Send the content to an OpenAI Assistant using `message an assistant`.
4. Parse the structured JSON returned by the Assistant.
5. Inject the structured weather data into a Google Sheet.

---

## 🔧 Technical Stack

- **Make (Integromat)**: scenario orchestration, modules for webhook, Docs, OpenAI, JSON, Sheets.
- **OpenAI Assistant (gpt-4-0613)**: text-to-JSON extraction using a custom system instruction.
- **Google Docs**: contains the raw weather bulletin.
- **Google Sheets**: receives the cleaned and parsed weather data.
- **Postman**: used to send test webhooks to simulate external calls.

---

## 🧩 Workflow Modules

1. **Manual Webhook Trigger**  
   Simulates incoming weather report trigger (e.g. from a forecasting system or operator).
2. **Google Docs: Get Document Content**  
   Retrieves the bulletin text from a specific Google Document.
3. **OpenAI Assistant (Message an Assistant)**  
   Sends the text to a GPT-4 assistant configured with precise system instructions.
4. **JSON Parser**  
   Parses the structured output into key-value pairs.
5. **Google Sheets: Add Row**  
   Stores the extracted weather parameters into a spreadsheet.

---

## 🔍 Assistant Setup

- **Model**: `gpt-4-0613`
- **Top P**: 0.69
- **Temperature**: 0.66


---

## ✅ Output Example (Google Sheet Fields)

| City     | Time (UTC) | Temp (°C) | Wind  | Humidity (%) | Pressure (hPa) | Visual Observations                                 | Meteorological Phenomena             | Comment                                                                 |
|----------|------------|-----------|-------|---------------|----------------|------------------------------------------------------|--------------------------------------|-------------------------------------------------------------------------|
| Avignon  | 9h         | 21        | calm  | 57            | 1010           | threatening cumulonimbus NW, congestus, cumulus     | cold drop, barometric swamp          | increased storm risk during the day based on visible vertical growth   |


---
## 📁 Repository Structure
```
Meteorological_Workflow/
├── README.md                 # Main documentation (English version)
├── README_fr.md              # French documentation
│
├── screenshots/              # Visual references for workflow and outputs
│   ├── Google_sheet_data.jpg       # Structured Google Sheet output
│   ├── OpenAI_platform.jpg         # OpenAI assistant configuration (model, temperature, top_p)
│   ├── Weather_comment.jpg         # Example of generated weather analysis
│   └── Workflow_Make_assistant_IA.jpg # Make.com workflow diagram (webhook → assistant → output)
│
└── system_instruction/       # Assistant system prompt and parsing setup
    └── system_instruction.txt     # Full system prompt (input parsing + formatting)
│
└── code/       # code and blueprints
    └── Integration Webhooks.blueprint.json     # Blueprint of the workflow


```
---

## 🎯 Purpose

This workflow is part of a broader project to automate environmental data interpretation using AI assistants. It serves as a prototype for:
- Low-friction **LLM integration in real-world weather pipelines**
- Use in **scientific education**, **operational meteorology**, or **citizen science**
- Future **AGI-compatible environmental parsing routines**

---

## 🧠 Author

**Jérôme Frasson (Jerome-X1)**  
Explorer of post-AGI cognition & ecological systems  
📫 jerome.frasson.vsi@gmail.com  
🔗 [GitHub – Jerome-X1]
---



---
