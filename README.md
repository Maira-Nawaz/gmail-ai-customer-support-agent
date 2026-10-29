# AI-Powered Gmail Customer Support Agent

An n8n workflow that helps automate incoming customer-support emails by classifying messages, retrieving relevant information from a knowledge base, and preparing or sending a contextual reply through Gmail.

## Business problem

Support teams often receive repetitive questions that require agents to search FAQs or internal documentation before replying. Manually triaging every email can slow response times and make it harder to keep responses consistent.

## Solution

This workflow connects Gmail with an AI classification and retrieval flow. Support-related messages can be routed to an AI agent, which searches a connected knowledge base for relevant context and generates a response. Gmail labels help organize the conversation.

## Workflow overview

1. **Knowledge-base ingestion:** A Google Drive trigger detects updated files, downloads them, processes their content, creates embeddings, and stores vectors in a vector database.
2. **Email trigger:** Gmail detects an incoming message.
3. **Classification:** A text classifier routes customer-support emails separately from other messages.
4. **Retrieval and response generation:** The AI agent uses the connected knowledge base to find relevant context and formulate a response.
5. **Gmail actions:** The workflow labels the message and replies through Gmail, according to the configured logic.

[`screenshots/workflow-overview.png`](https://github.com/Maira-Nawaz/gmail-ai-customer-support-agent/blob/main/workflow-overview.png)

## Tools and integrations

- n8n
- Gmail Trigger and Gmail actions
- Google Drive Trigger and file download
- AI text classification
- AI Agent and chat model
- Embeddings and vector-store retrieval
- Knowledge-base document loading and text splitting

**Important:** The exact model and vector-store providers depend on the exported workflow configuration. Update this section to match the final JSON before publishing.

## Repository contents

- `screenshots/workflow-overview.png` — screenshot of the workflow
- `workflow/` — place the sanitized n8n workflow JSON export here

## Setup

1. Import the workflow JSON into n8n.
2. Connect your own Gmail and Google Drive credentials.
3. Configure the chat model, embeddings, and vector store used in the workflow.
4. Add or update the knowledge-base documents.
5. Test with sample emails before enabling automatic replies.
6. Review the prompts, classification rules, Gmail labels, and error handling for your use case.

## Security and privacy

- Never commit API keys, OAuth tokens, passwords, or credential exports.
- Replace sensitive values with placeholders before publishing the JSON.
- Do not include real customer emails, personal information, internal company documents, or confidential screenshots.
- Test with synthetic or approved sample data.
- For client work, share only the assets the client has authorized you to publish.

## Attribution

This project is based on the n8n community template **“Automated customer support with GPT-4 knowledge base agent for Gmail”** by **Yasser Sami**. The published template description credits the original creator. Add a link to the original template and describe your own modifications clearly.

Original template: https://n8n.io/workflows/

## What I customized

Replace this section with the changes you personally made, for example:
- model/provider configuration
- knowledge-base ingestion and retrieval setup
- classification categories and prompts
- reply tone and response constraints
- Gmail labels, routing, and error handling
- client-specific requirements (only if approved for public disclosure)

## Status

Update this after testing: `Prototype` / `Tested with sample data` / `Client-deployed` (choose the accurate status).
