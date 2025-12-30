# Sortalizer: Privacy & Data Governance (2025)

**Project Status:** Limited Risk AI System (EU AI Act)  
**Legal Entity:** Creative Mayhem (SME Status)  
**Retention Policy:** Ephemeral (24-hour metadata wipe)

---

## 1. Privacy-by-Design Checklist (Internal)
*This section documents the Technical and Organizational Measures (TOMs) required by GDPR Art. 25.*

* **Data Minimization:** No raw images are permanently stored. Images are processed in volatile memory to extract item features and are discarded immediately after analysis.
* **Purpose Limitation:** Data is processed solely for the "item identification and valuation" service. We do not use user-uploaded images for secondary AI model training.
* **Self-Service Erasure:** Users maintain absolute control via a "Delete All Data" button in the dashboard, which triggers a cascading purge of their metadata and analysis history.
* **Security of Processing:** All API interactions use TLS 1.3. Service keys for OpenAI and Tavily are stored as encrypted environment secrets, never hardcoded.

---

## 2. Sub-Processor Disclosure (DPA Appendix)
*Required under GDPR Art. 28 and the AI Act's transparency mandates.*

| Entity Name | Location | Purpose of Processing | Safeguards |
| :--- | :--- | :--- | :--- |
| **OpenAI, LLC** | USA / EU (Azure) | AI model inference for item identification and descriptions. | Standard Contractual Clauses (SCCs). |
| **Tavily Search** | USA | Real-time marketplace data retrieval (Sources). | Data minimized to search queries only. |
| **Lemon Squeezy** | USA | Merchant of Record (Payments/Tax). | PCI-DSS Compliance. |
| **Hetzner Online** | Germany (EU) | Primary Web Hosting & Database. | Fully GDPR compliant, EU-local. |

---

## 3. AI Act Transparency Shield
*These policies protect Creative Mayhem from "Prohibited Practices" (Art. 5) violations.*

* **Biometric Prohibition:** Sortalizer does not perform facial recognition, emotion recognition, or biometric categorization. Any faces present in uploaded images are ignored by the processing logic.
* **No Prohibited Scraping:** We do not utilize databases created through untargeted scraping of facial images from the internet or CCTV footage.
* **Machine-Readable Marking:** Every synthetic output is tagged with `data-ai-generated="true"` and `schema.org/ItemList` metadata for automated detection.

---

## 4. ToS / DPA Legal Language
*Include this paragraph in your public Terms of Service.*

> "By using Sortalizer, you authorize Creative Mayhem to engage OpenAI and Tavily as sub-processors for the purpose of item analysis. We have entered into Data Processing Addendums with these providers to ensure your data is processed according to EU standards. You acknowledge that while we summarize marketplace data, the final responsibility for verifying the accuracy of these 'unfiltered' results remains with the human user.".
