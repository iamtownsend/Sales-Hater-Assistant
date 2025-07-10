# Sales-Hater-Assistant
A PowerAutomate and PowerBI setup to track things Non-Sales People Have to Track

# Sales Hater Assistant

Automate your prospect follow-ups, summary reports, and deal-stage alerts—no premium connectors required. Built entirely with Office 365 E3 tools (Power Automate, Power Apps for O365, Excel/SharePoint, Power BI Free).

---

## 🔧 Prerequisites

- **Office 365 E3 license** (Power Automate Free, Power Apps for O365, Excel Online, Power BI Free)  
- **OneDrive for Business** (cloud-only)  
- **Power BI Desktop** (latest version)

---

## 📂 Repository Structure
Sales-Hater-Assistant/
├─ flows/
│ ├─ OverdueNextActionReminders.zip
│ ├─ ProspectsSummaryEmail.zip
│ └─ DealStageChangeAlerts.zip
├─ excel/
│ ├─ Thisprospects_mvp.xlsx ← Prospect table + ErrorLog sheet
│ └─ ThreeYearSampleSales.xlsx ← 3-year sample data with seasonality
├─ powerbi/
│ └─ SalesHaterReport.pbix ← Interactive dashboard & drill-through
└─ README.md ← This document


---

## ⚙️ Setup & Installation

1. **Upload Excel files**  
   - In OneDrive for Business, create a folder called `SALES HATER ASSISTANT`  
   - Upload `Thisprospects_mvp.xlsx` and `ThreeYearSampleSales.xlsx` into it

2. **Import Power Automate flows**  
   - Go to [Power Automate → My flows → Cloud flows → Import]  
   - Select each `.zip` in the `flows/` folder and import as **Create as new**  
   - During import, rebind the OneDrive connection to your tenant  
   - After import, open each flow and verify:
     - **Recurrence** schedule  
     - **Main** scope contains your Excel → filter → notification steps  
     - **ErrorHandling** scope logs failures into the **ErrorLog** table in `Thisprospects_mvp.xlsx`

3. **Configure Power BI report**  
   - Open `powerbi/SalesHaterReport.pbix` in Power BI Desktop  
   - In **Transform data**, update the Excel source paths to your OneDrive URLs:  
     - `https://<your-tenant>.sharepoint.com/personal/<you>/_layouts/15/onedrive.aspx?.../SALES%20HATER%20ASSISTANT/Thisprospects_mvp.xlsx`  
   - Save and **Publish** to Power BI Service (optional)  

---

## 🚀 Usage

- **Flows** run on their scheduled cadence:
  - **Overdue Next-Action Reminders**: mobile push when a Next Action is overdue  
  - **Prospects Summary Email**: weekly summary of calls, emails, meetings, deals moved, pipeline value  
  - **Deal-Stage Change Alerts**: push on every stage advancement
- **Error logging**: any flow failure writes a row to **ErrorLog** in your `Thisprospects_mvp.xlsx` Excel sheet  
- **Power BI Dashboard**:
  - **Cards**: key KPIs (Deals Moved, Total Meetings, Calls, Emails, Pipeline)  
  - **Charts**: Count by Deal Stage & Pipeline Value donut  
  - **Drill-through**: right-click (or header icon) on a bar to open the **Detail** page showing row-level data  

---

## 🛠 Customization

- **Follow-up cadence**: edit the **Recurrence** triggers in each flow  
- **Deal Stages**: modify the **Deal Stage** choices in your Excel table (Lead → Qualified → Proposal → Closed)  
- **KPI measures**: open the PBIX and adjust DAX in the **Modeling** pane  
- **ErrorLog fields**: extend the Excel sheet with extra columns and update the **ErrorHandling** scope mapping  

---

## 🔗 Connect with Me

**Eric T. Schmidt**  
- LinkedIn: https://linkedin.com/in/erictschmidt  
- GitHub: https://github.com/erictschmidt 
- GitLab: https://gitlab.com/erictschmidt

---

## 📄 License

This project is released under the [MIT License](LICENSE).  

---

> Built with ❤️ by Eric T. Schmidt – empowering non-sales people to hate sales friction less.  

