# Capstone Project Context

## Project
- **Name:** Threat Intelligence Feed 
- **Team:** Shiva (Orchestration), Allision (AI Analysis) & Daniel (Data Ingestion & Integration)
- **What it does:** Uses AI to streamline threat intelligence by identifying and priortizing indictors of compromise through a unified dashboard. By providing real-time, actionable insights, the system enhances traditional defense methods like antivirus software to keep pace with rapidly evolving cyber threats.
- **Project type:** Threat Intelligence Hub

## Architecture
[have to edit]
- **Ingestion:** n8n scrapes data from the web and writes the threats to an Airtable table with status='unprocessed'.
- **AI Core:** == + Groq threat classification via n8n, writing resutls back to Airtable. Flowise RAG chain for detailed analysis.
- **Specialist:** n8n workflow creates Alert records for high-confidence threats (confidence > 0.9).
- **Integration:** Dashboard views for monitoring.

## Tech Stack
[have to edit]
- n8n Cloud (workflow automation)
- Flowise Cloud (LLM chains — RAG chatbot, analysis chains)
- Groq API (LLM inference — llama-3.3-70b-versatile)
- Hugging Face Inference API (sentiment analysis, ==, ==)
- Airtable (shared database — 1 table)
- GitHub (repo, documentation, portfolio)

## Airtable Schema
[have to adjust the field names]
### [Table 1 Name, e.g., "Emails"]
| Field | Type | Written By | Notes |
|-------|------|-----------|-------|
| Company_Name | Long Text | Feed Collector | Where the threat was received |
| Tech_Stack | Long Text | AI Summarizer & IOC Extractor | technologies affected by the threat |
| Threat_Summary | Long Text | AI Summarizer & IOC Extractor | Values: unprocessed, analyzing, analyzed, error |
| Affected_Softwares |Long Text | AI Summarizer & IOC Extractor | softwares the threat targeted |
| Attack_Type | Long Text | AI Summarizer & IOC Extractor | Description of the attack |
| Severity | Long Text | Relevance Scorer | Values: High & Low |
| remediation_action | Long Text | AI Summarizer & IOC Extractor | Recommended Action |
| relevance_score | Number | Relevance Scorer | Values: 1.0 to 10.0 |
| Date | Date | Auto | Updates as the threat is proccessed |
| ... | ... | ... | ... |

## Conventions
[have to edit]
- Field names: Snake_Case (no spaces instead underscores, capitals)
- Status values: lowercase, consistent across tables
- Date fields: date  time

## Current State
- **What's working:** Groq classification
- **What's in progress:** Flowise Cloud RAG, Web Scrapper
- **Known issues:** N/A
- **Next milestone:** Integrating all components

## Repository Structure
[have to edit]
