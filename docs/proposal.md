# [Threat Intelligence Feed Dashboard]

## Team Members

|    Name   |  Role/Component  | GitHub Username |
|-----------|------------------|-----------------|
|   Shiva   |   Orchestration  |   @Shiva-Ram20  |
|  Allison  |    AI Analysis   |  @10AllisonF22  |
|   Daniel  |  Data Ingestion  |    @Danil5343   |

## Problem Statement
This project uses AI to analyze cybersecurity threats, extract indicators of compromise (IOCs), and evaluate their relevance. This information is all presented through a unified dashboard. Cyber threats are constantly evolving. New methods of exploiting software vulnerabilities emerge daily, making it increasingly difficult to stay ahead using traditional approaches alone. Through integrating AI, this system enables faster identification and prioritization of relevant threats. The most common defense method against these cyber threats is anti-virus software and backups. This project aims to enhance threat intelligence by providing deeper insight and context, and clear, actionable insights in real time.

## Target Users
Security analysts at mid to large organizations who handle 200+ alerts daily and require a system that intelligently filters and prioritizes threats, enabling them to focus on the most critical and relevant risks.

## Architecture

![Architecture Diagram](https://github.com/Daniil5343/ai-capstone-threat-intelligence-feed/blob/aa961938aad30891d5d1d5ae425f1900614d3f4a/docs/architecture.png)



## Component Breakdown

### Component 1: Feed Collector (Daniel)
- **Description:** [Calls on Groq API  and SerpAPI, Groq agent (llama model) uses SerpAPI to perform a google search and returns relevant data related to malicious activity in terms of security. Can be adjusted to search independently.]
- **Tools:** [n8n, Airtable, Hugging Face, SerpAPI, GroqAPI]
- **Input:** [GoogleSearches]
- **Output:** [Formatted JSON]
- **Standalone demo:** [The AI will perform a search and return relevant data re-formatted to JSON]

### Component 2: AI Summarizer & IOC Extractor (Allison)
- **Description:** Summarize threats and Examine Indicators or compromise
- **Tools:** n8n, HF API, Flowise & Airtable
- **Input:** Data is JSON, CSVwhich goes through the Feed Collector, is processed by Flowise, and stored in Airtable 
- **Output:** Summary and structured IOC indicators 
- **Standalone demo:** Using the Flowise chain connected to Hugging face, each threat entry is summarized and extracted IOCs are structured on Airtable to have an easy to view table.

### Component 3: Relevance Scorer (Shiva)
- **Description:** Defines the technology stack & relevance of each threat
- **Tools:** n8n, Airtable & Groq
- **Input:** data from feed collector
- **Output:** tech stack & Groq analysis
- **Standalone demo:** Sample data -> receive tech stack & Groq analysis

### Component 4: Integration, Testing & Presentation (All Group Members) 
- **Description:** Combining components & presenting them working together 
- **Tools:** 2 Airtables, n8n, GitHub & draw.io
- **Input:** data from feed collector
- **Output:** results dashboard with the pipeline status, error monitor & results feed
- **Standalone demo:** Tested with combined workflow

## Data Sources 

- **Primary data:** Web-scraped data? Intelligence websites ?
- **Sample data:** Will find Data that would seem to be malicious in nature or 
- **Data format:** JSON


## AI Capabilities 

|      Capability     |           Purpose          |                                    Model/API                                   |
|---------------------|----------------------------|--------------------------------------------------------------------------------|
| Text Classification | Detect suspicious language | https://huggingface.co/cybersectony/phishing-email-detection-distilbert_v2.4.1 |
| Text Classification |     Enriches the threat    |      https://huggingface.co/mrm8488/bert-tiny-finetuned-sms-spam-detection     |


## Success Criteria 

1. System correctly classifies 8 out of 10 threats
2. Data pipeline processes all records within 2 minutes
3. Dashboard displays all enriched records with filtering
4. All 4 components integrate and exchange data correctly
5. Each component has its own README with setup instructions


## Timeline

|  Week |                       Milestone                       |
|-------|-------------------------------------------------------|
|   3   | Project proposal + architecture diagram + GitHub repo |
|  4-6  |  Build individual components, test with sample data   |
|  7-9  |   Add LLM/agent capabilities, refine AI processing    |
| 10-12 |       Integration, error handling, dashboard/UI       |
| 13-14 |          Polish, documentation, demo preparation      |
|  15   |                  Final presentation                   |
