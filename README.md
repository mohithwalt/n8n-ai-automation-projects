# n8n Automation Projects

A collection of three end-to-end automation workflows built using [n8n](https://n8n.io/), an open-source workflow automation tool. These projects were built over the course of a hands-on learning sprint, covering AI agents, API integrations, OAuth authentication, webhook tunneling, and multi-step conditional logic.

## Projects

### 1. AI Research Chatbot (Telegram) 📁 [`AI research chatbot.json`](./AI%20research%20chatbot.json)
A Telegram bot that answers user questions by researching the web in real time.
- **Trigger:** Telegram message
- **Flow:** User question → AI Agent reformulates query → Second AI Agent researches using SerpAPI → Final answer sent back via Telegram
- **Stack:** n8n, Groq (Llama 3.3 70B), SerpAPI, Telegram Bot API
- ![image alt](https://github.com/mohithwalt/n8n-ai-automation-projects/blob/ffb78241dc4607bfeeead4cb2e0e9dafe355751d/Screenshot%20(198).png)
- ![image alt](https://github.com/mohithwalt/n8n-ai-automation-projects/blob/41cb4943d8893ecee9d78f6025632c0f7b86f8f1/Screenshot%20(199).png)


### 2. AI Hiring Agent 📁 [`AI Hiring Agent.json`](./AI%20Hiring%20Agent.json)
An automated resume screening pipeline that evaluates job applicants and logs results.
- **Trigger:** Google Form submission
- **Flow:** Resume (PDF) → Extract text → AI Agent scores candidate → Information Extractor structures the output → Sends rejection/acceptance email via Gmail → Logs result to Google Sheets
- **Stack:** n8n, Groq, Gmail API, Google Sheets API, Google Drive API

- ![image alt](https://github.com/mohithwalt/n8n-ai-automation-projects/blob/41cb4943d8893ecee9d78f6025632c0f7b86f8f1/Screenshot%20(200).png)
- ![iamge alt](https://github.com/mohithwalt/n8n-ai-automation-projects/blob/41cb4943d8893ecee9d78f6025632c0f7b86f8f1/Screenshot%20(201).png)

### 3. AI Email Assistant 📁 [`AI EMAIL assistant.json`](./AI%20EMAIL%20assistant.json)

An intelligent inbox automation that reads incoming emails, summarizes them, classifies urgency, and routes notifications accordingly.
- **Trigger:** New Gmail message
- **Flow:** Email received → AI analyzes subject/body → Classifies urgency & category → Routes to Slack alert (if High/Medium urgency) or logs quietly (if Low) → Labels email in Gmail → Appends record to Google Sheets
- **Stack:** n8n, Groq, Gmail API, Slack API, Google Sheets API
- [image alt](https://github.com/mohithwalt/n8n-ai-automation-projects/blob/41cb4943d8893ecee9d78f6025632c0f7b86f8f1/Screenshot%20(205).png)
- ![iamge alt](https://github.com/mohithwalt/n8n-ai-automation-projects/blob/41cb4943d8893ecee9d78f6025632c0f7b86f8f1/Screenshot%20(206).png)
- ![iamge alt](https://github.com/mohithwalt/n8n-ai-automation-projects/blob/41cb4943d8893ecee9d78f6025632c0f7b86f8f1/Screenshot%20(207).png)
- ![iamge alt](https://github.com/mohithwalt/n8n-ai-automation-projects/blob/41cb4943d8893ecee9d78f6025632c0f7b86f8f1/Screenshot%20(208).png)
- ![iamge alt](https://github.com/mohithwalt/n8n-ai-automation-projects/blob/41cb4943d8893ecee9d78f6025632c0f7b86f8f1/Screenshot%20(209).png)

## Tech Stack Summary

- **Automation platform:** n8n (self-hosted via Docker)
- **LLM providers:** Groq (Llama 3.3 70B), Google Gemini
- **Tunneling:** Cloudflare Tunnel (for local webhook exposure during development)
- **Integrations:** Gmail API, Google Sheets API, Google Drive API, Slack API, Telegram Bot API, SerpAPI

## What I Learned

- Setting up OAuth2 credentials and redirect URIs across multiple Google Cloud APIs
- Debugging LLM output parsing (handling malformed JSON responses from AI models)
- Working with Gmail's nested header structure to extract sender/subject data
- Conditional branching logic based on AI-classified data
- Exposing a local development environment securely via Cloudflare Tunnel
- Managing multiple API credentials and rate limits across different LLM providers

## How to Use

1. Import any `.json` file into your own n8n instance (Workflows → Import from File)
2. Reconnect the credentials for each service used (Gmail, Slack, Telegram, Groq, etc. — these are not included in the exported files for security)
3. Activate the workflow

