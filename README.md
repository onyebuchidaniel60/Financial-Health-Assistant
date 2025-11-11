# 🧠 Financial Health Assistant (n8n Workflow)

This workflow automates **financial report generation and delivery** using **AI analysis** and **Google Workspace integration**.

---

## 📊 Overview

The **Financial Health Assistant** is an AI-driven automation that:

1. Fetches key financial data (Income Statement, Cash Flow Summary, Balance Sheet) from Google Sheets.
2. Combines and processes the data into a structured JSON format.
3. Uses an AI agent powered by **Google Gemini** to analyze the business’s financial performance.
4. References two Google Docs:
   - A **Report Template** defining structure and sections.
   - A **Company Overview** document providing context and history.
5. Generates a professional financial report using the template.
6. Sends the report automatically to a designated **Slack channel**.

---

## 🧩 Key Components

| Node | Function |
|------|-----------|
| **Google Sheets (3 nodes)** | Pulls financial data: Income Statement, Cash Flow, and Balance Sheet. |
| **Merge Node** | Combines data streams into one unified dataset. |
| **Code Node (JavaScript)** | Structures data into JSON (incomeStatement, cashFlow, balanceSheet). |
| **LangChain Agent Node** | Acts as the AI financial analyst using Google Gemini as the language model. |
| **Google Docs Tool (2 nodes)** | Fetches the report template and company overview documents. |
| **Slack Node** | Sends the final financial report as a message to the workspace channel. |
| **Cron Trigger** | Runs the workflow automatically (every hour, daily, or manually). |

---

## ⚙️ Setup Instructions

1. **Clone the Repository**
2. **Import the Workflow into n8n**
Open your n8n editor.

Click Import Workflow.

Select the Financial Health Assistant.json file.

3. **Set Up Required Credentials**

Configure the following integrations:

Google Sheets OAuth2 API – for accessing financial data spreadsheets.

Google Docs OAuth2 API – for reading the report template and company overview documents.

Slack OAuth2 API – for posting the final report message.

Google Gemini / PaLM API – as the AI model for financial analysis.

4. **Update Document and Sheet IDs**

Replace all sample Google Sheet and Google Docs URLs with your own document links.

5. **Configure the Slack Node**

Choose your target Slack channel or workspace.

Map the AI Agent node’s output to the Slack message text.

6. **Activate the Workflow**

**You can**:

Turn it on manually, or

Use the Cron Trigger node to schedule automatic runs (e.g., hourly, daily, or weekly).

### 🧠 How It Works (Flow Summary)

The workflow starts with a Cron Trigger.

Google Sheets nodes retrieve the company’s financial data.

The Merge Node consolidates the three datasets.

A Code Node formats the data into structured JSON.

The LangChain AI Agent processes:

The Report Template (Google Docs) for structure.

The Company Overview (Google Docs) for context.

The Google Gemini model for data analysis and narrative generation.

The resulting financial report is posted automatically to Slack.

### 🧾 Example Use Case

For a small business:

Monthly income and expenses are stored in Google Sheets.

A manager needs a clean financial report summarizing performance.

This workflow:

Pulls the latest data automatically.

Analyzes the numbers using AI.

Generates a human-readable financial summary.

Sends it to Slack for easy sharing — with zero manual effort.

### 🧩 Dependencies

n8n v1.75 or later

Google Workspace (Sheets + Docs)

Slack App with chat:write permission

Google Gemini API key

### 📎 Repository Contents

 Financial Health Assistant.json
 
 README.md 



### 🧰 Example Integration

Google Sheets Data

Financial data is pulled from sheets such as:

Income Statement (Monthly)

Cash Flow Summary (Quarterly)

Balance Sheet (End of Year)

Google Docs Files

Template Document: Defines report structure and sections.

Company Overview Document: Provides business history and operational context.

### 📬 Output

The AI-generated financial report is sent directly to your selected **Slack** channel — ready for internal review, client updates, or record-keeping.

### 🏗️ Future Improvements

Store generated reports automatically in Google Docs.

Add Notion integration for archiving reports.

Include charts and visual KPIs in the generated output.

**Author**: Onyebuchi Nnamani
**License**: MIT
