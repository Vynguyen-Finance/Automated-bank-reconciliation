# Automated Bank Reconciliation Tool (FDI Corporate Standard)

## 📌 Project Overview
In financial operations, manual bank reconciliation is often a time-consuming and error-prone process. This project delivers an automated solution using **Python and Pandas** to streamline the matching process between the General Ledger (GL) and Bank Statements, reducing processing time from hours to seconds while ensuring 100% data integrity.

The tool is specifically customized for **FDI corporate standards**, generating an elegant, executive-ready summary dashboard alongside granular detail sheets with standard accounting formats.

---

## ⚙️ Core Matching Logic & Features
* **Smart Date-Window Matching:** Automatically pairs transactions with identical amounts if their transaction dates fall within a configurable $\pm3$-day window (to account for weekend or interbank processing delays).
* **Automated Data Segregation:** Instantly segregates data into 3 clear categories:
  * *GL Unmatched:* Errors on the accounting books (e.g., double-postings).
  * *Bank Unmatched:* Unrecorded banking activities (e.g., bank service fees, interest).
  * *Matched Items:* Successfully reconciled records.
* **Corporate Styling Automation:** Utilizing `openpyxl`, the final output is automatically formatted with a classic Navy corporate theme, proper column widths (auto-fit), and standard accounting number formats (e.g., negative numbers wrapped in parentheses: `(3,000,000)`).

---

## 📊 Sample Management Summary Dashboard
The generated report includes an executive summary tab designed for CFOs and Finance Managers to track variances at a glance:

| Financial Items | Amount (VND) | Status / Action Required |
| :--- | :--- | :--- |
| **1. Total Unmatched Items from General Ledger (GL)** | (3,000,000) | Requires reversal entry on ERP (SAP/Oracle) |
| **2. Total Unmatched Items from Bank Statement** | (55,000) | Record as bank financial expense |
| **Status / Conclusion** | **Pending Review** | Audit trail details available in separate tabs |

---

## 🛠️ Tech Stack & Libraries
* **Language:** Python 3
* **Environment:** Google Colab / Jupyter Notebook
* **Key Libraries:** * `pandas` & `numpy` (Data cleaning and matching logic)
  * `openpyxl` (Excel automation and styling)

---

## 🚀 Future Enhancements (End-to-End Automation)
This Python core engine can be seamlessly integrated with **Power Automate Desktop** to create a fully hands-free routine:
1. **Power Automate** schedules daily/monthly bots to log into ERP (SAP) and Corporate Internet Banking to extract raw statements.
2. The bot triggers this **Python Script** in the background to execute the matching logic.
3. The finalized FDI-standard Excel report is automatically emailed to the Finance Manager or dropped into a shared Microsoft Teams channel.
