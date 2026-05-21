# Threat Intelligence Feed Dashboard

## Problem Statement
This project uses AI to analyze cybersecurity threats, extract indicators of compromise (IOCs), and evaluate their relevance. This information is all presented through a unified dashboard. 
Cyber threats are constantly evolving. New methods of exploiting software vulnerabilities emerge daily, making it increasingly difficult to stay ahead using traditional approaches alone. 
Through integrating AI, this system enables faster identification and prioritization of relevant threats. The most common defense method against these cyber threats is anti-virus software and backups. 
This project aims to enhance threat intelligence by providing deeper insight and context, and clear, actionable insights in real time.

## Architecture
![Architecture Diagram](https://github.com/Daniil5343/ai-capstone-threat-intelligence-feed/blob/a217211565a5476428349a0145334198d4e46ea9/docs/architecture.png.png)

## Components
- **Feed Collector**
- **AI Summarizer & IOC Examiner**
- **Relevance Scorer**
- **Integration, Testing & Presentation**

  
### [REQUIREMENTS] to run: [n8n account](https://n8n.io), [Groq Account/Credentials](https://Groq.com), [AirTable account/credentials](https://airtable.com), [SerpAPI](SerpAPI.com),[(optional) Slack Account](https://Slack.com),  

## How to Run
1. Go to the [Workflow directory](https://github.com/Daniil5343/ai-capstone-threat-intelligence-feed/tree/main/Workflow) and download the given JSON file
2. With your **n8n account**, go to your dashboard and press "Create Workflow"
3. Inside this new workflow navigate to the top left and locate the three vertical dots and press **"Import from file"**
4. Next, open the JSON file from your saved directory; if saved correctly all nodes should load 
5. Afterwards, Ensure that you have created n8n **credentials** for *Groq, SerpAPI, Airtable, and optionally Slack*
6. Locate the respective nodes from above and fill in with respective credits.
7. Assuming everything is filled in correctly, simply press execute or change the scheduling time and the workflow will run autonomously
   
## Config.
A1.To broaden/narrow search range simply open the initial javascript block in n8n and add/remove keywords as desired in the respective list, this ensures 
that the returned information can be as broad/small as needed.

   


