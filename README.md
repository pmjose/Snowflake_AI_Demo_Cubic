# Build an AI Assistant for Software-Defined Vehicles (Cubic³)

<p align="center">
  <strong>Connected vehicle and IoT operations intelligence, powered by Snowflake Cortex AI</strong>
</p>

<p align="center">
  <a href="#quick-start">Quick Start</a> •
  <a href="#features">Features</a> •
  <a href="#architecture">Architecture</a> •
  <a href="#local-testing">Local Testing</a> •
  <a href="#exec-questions-to-try-cubic">Exec Questions & Prompts</a>
</p>

---

## 🎯 Overview

This project adapts the demo to **Cubic³ (formerly Cubic Telecom)**—the software-defined vehicle (SDV) connectivity platform that powers 17M+ vehicles across **190+ countries** through hundreds of mobile network partnerships. Backed by a €473M SoftBank investment (51% stake, Dec 2023), Cubic³ delivers compliant, secure, and analytics-rich connectivity for automotive OEMs, agriculture machinery, and other high-value mobile assets.  

We use **Snowflake Cortex AI**, **Snowflake Intelligence**, and **Cortex Analyst** to show how Cubic³ teams could:
- Monitor global connectivity KPIs (latency, throughput, attach success, roaming performance) by OEM, country, and vehicle program
- Investigate driver support interactions and correlate sentiment with network issues or OTA rollout quality
- Summarize Cubic³ product updates (e.g., Explore³ insights, DriverConnect³ experience metrics, StreamLocal³ adoption) and operational runbooks

### What You Get

**Core Data Platform**:
- **📊 20+ Dimension & Fact Tables** - Connectivity, finance, marketing, sales, HR data
- **📄 60+ Business Documents** - Product briefs, runbooks, policies, playbooks (PDF/DOCX/MD)
- **🎙️ 25 Driver Support Calls** - Audio files for transcription and sentiment
- **📧 Email Previews** - Sample operational communications

**AI & ML Tools**:
- **🔍 6 Search Services** - Connectivity ops, finance, HR, marketing, sales, strategy
- **📈 4 Semantic Views** - Connectivity/finance/sales/HR datamarts
- **🤖 1 AI Agent** - Cubic³ Connected Vehicle Agent with 12 tools
- **💻 Streamlit Apps** - Cortex Agent interface
- **📓 Snowflake Notebooks** - Data processing & analysis workflows

---

## 🚀 Quick Start

### Prerequisites

- Snowflake account with ACCOUNTADMIN access
- Python 3.8+ installed
- Snowflake CLI (`snowflake-cli-labs`)

### Installation

```bash
# 1. Install Snowflake CLI
pip install snowflake-cli-labs

# 2. Clone repository
git clone <repository-url>
cd Snowflake_AI_Demo_Cubic

# 3. Configure Snowflake connection
snow connection add --connection-name telco-local

# 4. Run the pipeline
cd local-testing
./run_pipeline.sh
```

### What Gets Deployed

```
✅ Database: TELCO_OPERATIONS_AI
✅ Warehouse: TELCO_DEMO_WH
✅ Role: TELCO_ANALYST_ROLE (with CORTEX_USER)
✅ 20+ tables with demo data
✅ 6 Cortex Search Services
✅ 4 Cortex Analyst Semantic Views
✅ 1 Snowflake Intelligence Agent
✅ Streamlit Applications
```

**Deployment time**: ~10 minutes

---

## ✨ Features

### 🔍 Cortex Search Services (6)

Semantic search across Cubic³ business documents and operational runbooks:

| Service | Purpose | Content |
|---------|---------|---------|
| **Search Finance Docs** | Financial reports, policies, contracts | PDFs, DOCX, MD |
| **Search HR Docs** | Employee handbook, guidelines | PDFs, DOCX, MD |
| **Search Marketing Docs** | Campaigns, strategies, analysis | PDFs, DOCX, MD |
| **Search Sales Docs** | Playbooks, OEM success briefs | PDFs, DOCX, MD |
| **Search Strategy Docs** | Board presentations, market analysis | MD files |
| **Search Network/Connectivity Docs** | Connectivity ops, runbooks | MD files |

### 📊 Cortex Analyst Semantic Views (4)

Natural language SQL queries across operational and business datamarts:

| Semantic View | Data Domain |
|---------------|-------------|
| **FINANCE_SEMANTIC_VIEW** | Revenue, expenses, vendor spend, transactions |
| **SALES_SEMANTIC_VIEW** | OEM programs, products, customers, regions |
| **MARKETING_SEMANTIC_VIEW** | Campaigns, channels, leads, ROI |
| **HR_SEMANTIC_VIEW** | Employees, departments, salaries, attrition |

### 🤖 Cubic³ Connected Vehicle Agent

**12 integrated tools**:
- 4 Cortex Analyst tools (query datamarts)
- 6 Cortex Search tools (search internal docs)
- 1 Web scraper tool
- 1 Email sending tool

**Sample questions**:
- "Compare roaming attach success and latency by OEM program and country."
- "Summarize Explore³ insights for data consumption by model and region."
- "Which driver support calls mention infotainment or eSIM activation issues?"
- "How did OTA campaign success correlate with ticket volume in the last 14 days?"
- "What contract or SLA guidance applies to in-car video streaming (StreamLocal³)?"

---

## 🏗 Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│               CUBIC³ CONNECTED VEHICLE INTELLIGENCE                 │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  Data Sources           AI Processing         Semantic Layer       │
│  ────────────           ──────────────        ──────────────       │
│  • CSV Files            • Cortex Search       • 4 Semantic Views   │
│  • PDFs/DOCX/MD         • Cortex Analyst      • Natural Language   │
│  • Audio Files          • AI Functions        • Text-to-SQL        │
│                                                                     │
│  ┌────────────────────────────────────────────────────────────────┐│
│  │                 SNOWFLAKE INTELLIGENCE                         ││
│  ├────────────────────────────────────────────────────────────────┤│
│  │  Cubic³ Connected Vehicle Agent: 12 Tools | Multi-Modal | API ││
│  └────────────────────────────────────────────────────────────────┘│
│                                                                     │
│  ┌────────────────────────────────────────────────────────────────┐│
│  │                    APPLICATIONS                                ││
│  ├────────────────────────────────────────────────────────────────┤│
│  │  Streamlit Apps  |  Snowflake Notebooks  |  REST API          ││
│  └────────────────────────────────────────────────────────────────┘│
└─────────────────────────────────────────────────────────────────────┘
```

---

## 🧪 Local Testing

### Pipeline Steps

The local testing pipeline runs 7 steps:

| Step | Name | Description |
|------|------|-------------|
| 1 | Configure Account | Create roles, warehouse, database, schemas, stages |
| 2 | Upload Files | Upload CSV data and documents to stages |
| 3 | Data Foundation | Create tables and load data |
| 4 | Deploy Search | Create 6 Cortex Search services |
| 5 | Deploy Analyst | Create 4 semantic views (owned by ACCOUNTADMIN) |
| 6 | Deploy Applications | Create agent, procedures, Streamlit apps |
| 7 | Run Notebooks | Execute data processing notebooks |

### Running the Pipeline

```bash
cd local-testing

# List all steps
./run_pipeline.sh --list

# Run full pipeline
./run_pipeline.sh

# Run specific step
./run_pipeline.sh --step 1

# Start from specific step
./run_pipeline.sh --start-from 3

# Dry run (preview only)
./run_pipeline.sh --dry-run
```

### Connection Setup

1. **Configure connection**:
```bash
snow connection add --connection-name telco-local
```

2. **Test connection**:
```bash
snow connection test -c telco-local
```

3. **Required settings**:
   - Account: Your Snowflake account locator
   - User: User with ACCOUNTADMIN access
   - Role: ACCOUNTADMIN
   - Warehouse: Any available warehouse

---

## 📁 Project Structure

```
build-an-ai-assistant-for-telco/
├── full-ci.yml                    # DataOps pipeline definition
├── README.md                      # This file
│
├── dataops/event/
│   ├── variables.yml              # Pipeline variables
│   ├── DATA/
│   │   ├── demo_data/             # 20 CSV files (dimensions, facts)
│   │   └── unstructured_docs/     # PDFs, DOCX, MD by department
│   │       ├── finance/
│   │       ├── hr/
│   │       ├── marketing/
│   │       ├── sales/
│   │       ├── strategy/
│   │       └── network/
│   │
│   ├── analyst/                   # Semantic model YAML files
│   ├── notebooks/                 # Snowflake notebooks
│   ├── streamlit/                 # Streamlit applications
│   │
│   └── *.template.sql             # SQL deployment templates
│       ├── telco_configure_account.template.sql
│       ├── telco_upload_files.template.sql
│       ├── telco_data_foundation.template.sql
│       ├── telco_deploy_search.template.sql
│       ├── telco_deploy_analyst.template.sql
│       ├── telco_deploy_applications.template.sql
│       └── telco_run_notebooks.template.sql
│
├── local-testing/
│   ├── run_pipeline.py            # Python pipeline runner
│   ├── run_pipeline.sh            # Shell wrapper
│   ├── config.toml.example        # Connection config example
│   ├── create_service_user.sql    # Service user setup
│   └── README.md                  # Local testing guide
│
└── pipelines/                     # DataOps pipeline includes
```

---

## 🎯 Use Cases

### Executive Dashboard
- Natural language queries across connectivity, finance, and ops data
- "What is connectivity uptime and attach success by OEM program?"
- "Show driver support sentiment trends by country"

### Document Search
- Semantic search across 60+ Cubic³ product and operations documents
- "What does our SLA say about in-car streaming?"
- "Where is the VoLTE/VoNR roaming troubleshooting runbook?"

### Sales & Partner Analysis
- OEM and region performance by product bundle
- "Top regions by data consumption and ARPU"
- "Which OEM programs have the highest attach failure rate?"

### Network & Field Ops
- "Which markets show high latency or packet loss?"
- "Where did OTA updates spike support tickets last week?"

### Exec Questions to Try (Cubic³)
- "Compare roaming attach success and latency by OEM program and country."
- "Summarize Explore³ insights for data consumption by model and region."
- "What’s the revenue and margin mix by OEM, model, and country?"
- "Which driver calls mention eSIM activation or infotainment failures?"
- "Where should we prioritize new MNO partnerships based on usage growth?"

---

## 🔧 Configuration

### Variables (dataops/event/variables.yml)

Key configuration options:

```yaml
variables:
  EVENT_DATABASE: "TELCO_OPERATIONS_AI"
  EVENT_SCHEMA: "DEFAULT_SCHEMA"
  EVENT_WAREHOUSE: "TELCO_DEMO_WH"
  EVENT_ATTENDEE_ROLE: "TELCO_ANALYST_ROLE"
```

### Customization

- Edit `variables.yml` to change database/schema names
- Add data to `DATA/demo_data/` for new tables
- Add documents to `DATA/unstructured_docs/` for search

---

## 🐛 Troubleshooting

### Connection Issues

```bash
# Test connection
snow connection test -c telco-local

# List connections
snow connection list
```

### Permission Errors

Ensure your user has ACCOUNTADMIN role:
```sql
GRANT ROLE ACCOUNTADMIN TO USER <your_user>;
```

### Template Rendering

Check rendered SQL in `local-testing/.rendered/` directory.

---

## 📝 License

This project is provided for educational and demonstration purposes.

**Data Notes**:
- All data is synthetic/generated for demonstration
- Connectivity facts and prompts are Cubic³-aligned (global SDV connectivity, multi-country roaming, OEM programs) and for demo only
- Currency: amounts in semantic views/facts are in EUR
- Use only for learning Snowflake Cortex AI capabilities

**To refresh Snowflake with the latest demo data** (requires Snowflake CLI):
1) From a machine with `snow` configured:  
```bash
cd local-testing
./run_pipeline.sh --step 2 --step 3 --step 5 --step 6
```  
- Step 2: Upload updated CSVs and documents (Cubic³ docs)  
- Step 3: Data foundation (creates/loads tables like connectivity KPIs, region coverage, activation lead time, sales/finance/marketing/HR facts with EUR currency)  
- Step 5: Deploy semantic views  
- Step 6: Deploy applications/agent (Cubic³ agent + search services)

2) Validate post-deploy (optional):
```sql
SELECT * FROM network_performance LIMIT 5;
SELECT DISTINCT currency FROM sales_fact;
SELECT DISTINCT region_name FROM region_coverage;
SELECT DISTINCT vertical FROM sf_accounts;
```

---

<p align="center">
  <strong>Built with ❄️ Snowflake Cortex AI</strong>
</p>
