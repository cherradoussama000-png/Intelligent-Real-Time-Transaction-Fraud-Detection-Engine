# Intelligent-Real-Time-Transaction-Fraud-Detection-Engine
# Intelligent Real-Time Transaction Fraud Detection Engine

**A modern fraud monitoring prototype built with n8n + GPT-4**

This project demonstrates an end-to-end, real-time fraud detection system that processes incoming financial transactions, analyzes them with AI, applies hybrid scoring, and automates risk-based actions (hold, alert, log).


## Features

- **Live webhook ingestion** – receives transactions instantly from payment gateways  
- **IP geolocation & proxy detection** – enriches data with location, VPN/proxy flags  
- **GPT-4 behavioral analysis** – structured risk scoring with explainable output  
- **Hybrid scoring engine** – combines AI intelligence with deterministic rules for accuracy & cost control  
- **Smart branching logic**  
  - Low risk → silent logging  
  - High risk → HTTP hold attempt + Gmail alert + detailed incident report  
- **Fully configurable** – thresholds, alert emails, Sheet IDs via one central node  
- **Audit-friendly logging** – every decision recorded in Google Sheets

## Tech Stack

- n8n (core automation & workflow orchestration)  
- OpenAI GPT-4 (advanced behavioral fraud intelligence)  
- HTTP Request nodes (IP enrichment + hold action)  
- Gmail (real-time alerts)  
- Google Sheets (incident logging & audit trail)  
- JavaScript Code node (hybrid scoring & data normalization)

## What this project demonstrates

- Building real-time event-driven systems with webhooks  
- Integrating AI (GPT-4) into business-critical workflows  
- Combining machine learning with deterministic rules for reliable decisioning  
- Prompt engineering for consistent structured output & reduced false positives  
- Debugging & hardening complex n8n workflows (type coercion, nested JSON parsing, etc.)  
- End-to-end fintech automation: ingestion → analysis → action → logging

## Setup Instructions

1. Import the workflow  
   → n8n → Workflows → … → Import from File → select `fraud-detection-workflow.json`

2. Configure credentials  
   - OpenAI API key (GPT-4 access required)  
   - Gmail OAuth2 (for sending alerts)  
   - Google Sheets OAuth2 (for logging)

3. Set configuration values  
   - Open "Workflow Configuration" node  
   - `highRiskThreshold`: recommended 70–80  
   - `fraudTeamEmail`: your alert email  
   - `incidentSheetId`: your Google Sheet ID (create a new one)

4. Test with sample payloads  
   → See `EXAMPLES.md` or use Postman to POST to the webhook URL
