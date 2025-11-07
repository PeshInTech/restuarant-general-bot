AI Chatbot — n8n + Supabase RAG
https://customcx-leads-chatbot.netlify.app/

Lightweight, production-ready example that shows how to build an AI-powered chatbot orchestrated from n8n with a Supabase RAG (retrieval-augmented generation) backend. Designed to be embedded on any website (static or dynamic) via a small client snippet.

Overview

This mini-project demonstrates a simple, modular architecture:

Frontend: tiny embeddable widget (HTML + JS) you can drop into any site.

Orchestration & business logic: n8n workflows handle incoming messages, document retrieval, prompt construction, and calls to LLM APIs.

Vector DB + metadata + RAG: Supabase (Postgres + pgvector) stores documents/embeddings and serves relevant context for each user query.

LLM: your preferred LLM (OpenAI, Anthropic, Mistral, local model, etc.) called from n8n.

Use this repo as a template for demoing or running a lightweight RAG chatbot integrated into your existing app/website.

Features

RAG using Supabase vector search.

n8n workflows to:

Accept chat messages (HTTP webhook).

Query Supabase for relevant context.

Build a prompt and call an LLM.

Post-process and return answer to client.

Minimal embeddable client script (works on any website).

Easy to extend: add auth, analytics, conversation logs, multi-lingual support, etc.

Quick Demo (what you get)

n8n webhook endpoint: receives user messages.

n8n calls Supabase to run a vector similarity search.

n8n composes system + retrieved context + user query and calls LLM.

Response returned to widget which displays it in the chat UI.

/
├─ README.md
├─ frontend/
│  ├─ widget.html
│  └─ widget.js
├─ n8n-workflows/
│  └─ chatbot-workflow.json
├─ supabase/
│  └─ schema.sql
├─ docs/
│  └─ prompt-presets.md
└─ LICENSE
