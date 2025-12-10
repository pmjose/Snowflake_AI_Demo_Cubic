# <h1black>Build an AI Assistant for </h1black><h1blue>Cubic³ Connected Vehicle Ops</h1blue>

### <h1sub>Welcome to the Cubic³ Connected Vehicle AI Hands-On Lab!</h1sub>

Transform Cubic³’s global SDV connectivity operations with AI-powered analytics using **Snowflake Cortex AI**, **Snowflake Intelligence**, and **Audio AI**.

---

<img src="assets/architecture.png" alt="Cubic Connected Vehicle AI Architecture" width="900">

---

## <h1black>🎯 What You'll </h1black><h1blue>Build</h1blue>

In this hands-on lab, you'll deploy a complete **AI-powered connected vehicle operations and driver support platform** that includes:

### <h1sub>Core Capabilities</h1sub>

- **🌐 Connectivity Quality Analytics** - Track attach success, latency, packet loss, and throughput by OEM program, country, and MNO partner
- **📞 Driver Support Insights** - Transcribe and analyze driver support calls with AI_TRANSCRIBE and AI_SENTIMENT
- **🔍 Semantic Search** - Search transcripts, tickets, and product/runbook docs using natural language
- **💬 Natural Language Queries** - Ask questions in plain English and get instant insights
- **📊 Dashboards & KPIs** - Monitor network health, OTA campaign impact, and churn risk
- **🤖 AI Agent** - Conversational assistant with multi-source analysis tools
- **📈 ML Models** - Predict at-risk customers and surface regions needing partner upgrades

### <h1sub>Pre-Loaded Data (No Manual Uploads!)</h1sub>

✅ **25 Driver Support Call Recordings** - Pre-uploaded to `@AUDIO_STAGE`  
✅ **10,000+ Transcripts** - Already transcribed and sentiment scored  
✅ **5,000 Vehicle/Driver Profiles** - Account and device data  
✅ **1,000+ Support Tickets** - With sentiment and issue tags  
✅ **2,000+ Communications** - Emails, chats, SMS  
✅ **300+ Network/Connectivity Incidents** - Regional performance data  

---

## <h1black>🚀 Getting </h1black><h1blue>Started</h1blue>

### ⏱️ **Lab Duration**: 2-3 hours  
### 💰 **Cost**: Minimal (free trial works!)  
### 📚 **Prerequisites**: None - we'll guide you through everything!

### <h1sub>Quick Verification</h1sub>

Run these commands to verify your environment is ready:

```sql
-- Verify files in stages
LIST @AUDIO_STAGE;
LIST @DATA_STAGE;

-- Check database and schemas
SHOW SCHEMAS IN DATABASE TELCO_OPERATIONS_AI;

-- Verify role
SELECT CURRENT_ROLE();
```

---

## <h1black>📚 Lab </h1black><h1blue>Structure</h1blue>

This lab is organized into these sections:

1. **🎯 Introduction** (This page) - Overview and architecture
2. **📓 Run Notebooks** - Execute data processing and analysis notebooks
3. **🤖 Create Agents** - Build intelligent Cortex Agents
4. **🧠 Snowflake Intelligence** - Test your agent with natural language queries
5. **🎉 Conclusion** - Summary and next steps

---

## <h1black>🏗️ </h1black><h1blue>Architecture</h1blue>

<img src="assets/arch.png" alt="Cubic Connected Vehicle AI Architecture Diagram" width="1500">

---

## <h1black>📊 Data </h1black><h1blue>Overview</h1blue>

### <h1sub>Pre-Loaded Datasets</h1sub>

| Data Type | Records | Purpose |
|-----------|---------|---------|
| **Driver Support Call Recordings** | 25 | Audio files in @AUDIO_STAGE |
| **Call Transcripts** | 10,000+ | Pre-transcribed segments |
| **Vehicle/Driver Profiles** | 5,000 | Accounts & device info |
| **Support Tickets** | 1,000+ | Issues, resolutions, sentiment |
| **Network Performance** | 49,864 | Connectivity KPIs by region |
| **Infrastructure Capacity** | 1,500 | Bandwidth/utilization |
| **Customer Feedback** | 20,061 | Daily aggregated metrics |
| **CSAT Surveys** | 25 | Satisfaction scores |

### <h1sub>AI Processing Applied</h1sub>

- **AI_TRANSCRIBE**: Converts MP3 call recordings to text with speaker identification
- **AI_SENTIMENT**: Analyzes emotional tone of driver interactions
- **AI_PARSE_DOCUMENT**: Extracts text from Cubic³ product/runbook documentation
- **AI_TRANSLATE**: Translates content to multiple languages
- **AI_EXTRACT**: Structures unstructured data for analysis

---

## <h1black>🔍 What You'll </h1black><h1blue>Learn</h1blue>

### <h1sub>Technical Skills</h1sub>

- How to process audio files at scale with Cortex AI
- Building semantic search across operational communications and runbooks
- Creating natural language interfaces with Cortex Analyst
- Deploying intelligent agents with Snowflake Intelligence
- Analyzing unstructured data (audio, PDFs, text)
- Predicting churn/quality risk with ML models

### <h1sub>Business Value</h1sub>

- Reduce call review time by 90%+ with automated transcription
- Identify at-risk regions, OEM programs, and drivers before churn
- Optimize partner/MNO operations using correlated sentiment + network KPIs
- Accelerate OTA/feature rollouts with feedback loops
- Automate operational reporting and alerts

---

## <h1black>🎯 Use </h1black><h1blue>Cases</h1blue>

### <h1sub>Connected Vehicle Reliability</h1sub>
- Detect attach/latency issues by OEM program and country
- Flag regions needing partner upgrades or QoS tuning

### <h1sub>Driver Experience & Support</h1sub>
- Track sentiment in real-time
- Identify top drivers of support volume (eSIM, infotainment, roaming)
- Prioritize follow-ups for negative calls

### <h1sub>OTA & Feature Rollouts</h1sub>
- Measure ticket volume and sentiment before/after releases
- Spot geos where updates failed or degraded QoS

### <h1sub>Commercial & SLA Health</h1sub>
- Revenue and ARPU trends by OEM/model/country
- SLA compliance for streaming (StreamLocal³) or payments (FleetWallet³)

### <h1sub>Operations & Compliance</h1sub>
- Link network incidents to driver complaints
- Ensure privacy/PII redaction in transcripts and tickets

---

## <h1black>💡 Key </h1black><h1blue>Features</h1blue>

### <h1sub>All Data Pre-Loaded</h1sub>

Unlike traditional hands-on labs, **all data is already in Snowflake stages**:
- ✅ No manual file uploads required
- ✅ No waiting for transcription jobs
- ✅ Jump straight into analysis
- ✅ Focus on learning, not setup

### <h1sub>Production-Ready Patterns</h1sub>

Everything you build follows **Snowflake best practices**:
- ✅ Proper role-based access control
- ✅ Efficient warehouse auto-suspend
- ✅ Scalable stage organization
- ✅ Reusable SQL templates
- ✅ Automated deployment pipelines

---

## <h1black>🛠️ Technology </h1black><h1blue>Stack</h1blue>

### <h1sub>Snowflake Cortex AI</h1sub>
- **AI_TRANSCRIBE** - Speech-to-text conversion
- **AI_SENTIMENT** - Emotion detection
- **AI_PARSE_DOCUMENT** - PDF text extraction
- **AI_TRANSLATE** - Multi-language support
- **AI_EXTRACT** - Structured data extraction

### <h1sub>Cortex Search</h1sub>
- Semantic search across transcripts and tickets
- Vector similarity matching
- Hybrid search (keyword + semantic)

### <h1sub>Cortex Analyst</hsub>
- Natural language to SQL translation
- Semantic model definitions
- Business context understanding

### <h1sub>Snowflake Intelligence</h1sub>
- Multi-tool agent orchestration
- Conversational AI interface
- Automatic tool routing

### <h1sub>Snowflake Notebooks</h1sub>
- Python-based data processing
- Integrated AI function access
- Visualization and exploration

---

## <h1black>📱 </h1black><h1blue>Applications</h1blue>

You'll deploy these applications:

### <h1sub>Snowflake Notebooks</h1sub>
1. **Data Processing** - Loads and processes all data with AI
2. **Call Audio Analysis** - Explores transcriptions and sentiment
3. **Intelligence Lab** - Advanced AI/ML experimentation

### <h1sub>SnowMail Native App</h1sub>
- Gmail-style email viewer for operational communications
- Displays network alerts, driver support summaries, executive briefs
- Agent integration for automated email sending

---

## <h1black>🎓 Learning </h1black><h1blue>Path</h1blue>

This lab is designed for:

- **Data Engineers** - Process audio, PDFs, and text at scale
- **Data Analysts** - Build semantic models and search services
- **AI/ML Engineers** - Deploy intelligent agents and ML models
- **Business Users** - Explore natural language data interfaces

**No prior Snowflake experience required!** We'll guide you through each step.

---

## <h1black>📖 Additional </h1black><h1blue>Resources</h1blue>

- **Snowflake Documentation**: [docs.snowflake.com](https://docs.snowflake.com)
- **Cortex AI Functions**: [Cortex AI Documentation](https://docs.snowflake.com/en/user-guide/snowflake-cortex/llm-functions)
- **Snowflake Intelligence**: [Intelligence Guide](https://docs.snowflake.com/en/user-guide/snowflake-intelligence)
- **Cortex Search**: [Search Documentation](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-search)
- **Cortex Analyst**: [Analyst Guide](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-analyst)

---

## <h1black>🚦 </h1black><h1blue>Ready?</h1blue>

Everything is set up and ready to go! Click **Run Notebooks** in the navigation to start the lab.

**Let's build something amazing! 🚀**

---

## <h1black>ℹ️ About This </h1black><h1blue>Lab</h1blue>

- **Created by**: Snowflake Solutions Engineering
- **Industry**: Connected Vehicle & IoT
- **Use Case**: Cubic³ SDV connectivity ops & driver experience
- **Technologies**: Cortex AI, Snowflake Intelligence, Document AI, Audio AI
- **Deployment**: Automated via DataOps.live pipeline
- **Data**: Synthetic Cubic³-inspired connected vehicle support data

---

**Questions or Issues?** Contact support@snowflake.com or visit the #telco-ai-lab Slack channel.

