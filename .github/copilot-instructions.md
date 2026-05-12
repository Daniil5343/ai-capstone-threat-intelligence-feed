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
[have to edit]
### [Table 1 Name, e.g., "Emails"]
| Field | Type | Written By | Notes |
|-------|------|-----------|-------|
| record_id | Autonumber | Auto | Primary key |
| created_at | Date+time | Auto | When record was added |
| status | Single Select | All | Values: unprocessed, analyzing, analyzed, error |
| source | Single Line | Ingestion | manual, webhook, scheduled |
| [field_name] | [type] | [component] | [notes] |
| [field_name] | [type] | [component] | [notes] |
| ... | ... | ... | ... |

## Conventions
[have to edit]
- Field names: snake_case (no spaces, no capitals)
- Status values: lowercase, consistent across tables
- Date fields end in _at (created_at, analyzed_at)
- Boolean fields use is_ prefix (is_flagged, is_reviewed)

## Current State
- **What's working:** Groq classification
- **What's in progress:** Flowise Cloud RAG, Web Scrapper
- **Known issues:** N/A
- **Next milestone:** Integrating all components

## Repository Structure
[have to edit]
