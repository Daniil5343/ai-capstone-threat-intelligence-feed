# Capstone Project Context

## Project
- **Name:** Threat Intelligence Feed 
- **Team:** Shiva (Orchestration), Allision (AI Analysis) & Daniel (Data Ingestion & Integration)
- **What it does:** Uses AI to streamline threat intelligence by identifying and priortizing indictors of compromise through a unified dashboard. By providing real-time, actionable insights, the system enhances traditional defense methods like antivirus software to keep pace with rapidly evolving cyber threats.
- **Project type:** Threat Intelligence Hub

## Architecture
- **Ingestion:** Groq-LLM agent calls SerpAPI to return recently found cybersecurity oriented vulnerabilities
- **AI Core:** Groq-LLM summarizes the threat by highlighting the affected software and the matched tech stack. It assigns a severity label (High/Medium, Low), relevance score (1.0-10.0) and proposes a remediate action. 
- **Specialist:** n8n workflow notifies Senior Engineers for a high-confidence threat (confidence >= 8) and Junior Engineers for a low-confidence threat (confidence >= 4 but <= 7).
- **Integration:** Results Dashboard, Error Dashboard

## Tech Stack
- n8n Cloud (workflow automation)
- Groq API (LLM inference — llama-3.3-70b-versatile)
- Serp API
- Airtable (shared database — 1 table)
- GitHub (repo, documentation, portfolio)
- Slack (alerts)

## Airtable Schema
### Threat Intelligence Feed Dashboard
| Field | Type | Written By | Notes |
|-------|------|-----------|-------|
| Company_Name | Long Text | Feed Collector | Where the threat was received |
| Tech_Stack | Long Text | AI Summarizer & IOC Extractor | technologies affected by the threat |
| Threat_Summary | Long Text | AI Summarizer & IOC Extractor | Values: unprocessed, analyzing, analyzed, error |
| Affected_Softwares |Long Text | AI Summarizer & IOC Extractor | softwares the threat targeted |
| Attack_Type | Long Text | AI Summarizer & IOC Extractor | Description of the attack |
| Severity | Long Text | Relevance Scorer | Values: High & Low |
| Remediation_Action | Long Text | AI Summarizer & IOC Extractor | Recommended Action |
| Relevance_Score | Number | Relevance Scorer | Values: 1.0 to 10.0 |
| Date | Date | Auto | Updates as the threat is proccessed | 

## Conventions
- Field names: Camel_Case (no spaces instead underscores, capitals)
- Status values: lowercase, consistent across tables
- Date fields: date (YYYY-MM-DD)  time (24 hr format)

