# AI Shopping Assistant

An agentic product-search assistant with a dual-mode retrieval router: exact product-code lookups hit the database directly, everything else goes through semantic RAG search, over a catalog that updates itself.

**Demo video:** https://youtu.be/POsvx4is3UU

## What it does

- Answers customer product questions over a Supabase Vector catalog
- Routes queries by intent: regex-detected product codes get an exact row lookup; natural-language questions get semantic retrieval
- Keeps the catalog current: a pipeline watches a Drive folder, chunks and embeds each new or changed file automatically
- Returns paginated results for large matches

## Workflows

| File | Role |
|---|---|
| `chat-agent.json` | The conversational agent with the dual-mode retrieval router |
| `kb-ingestion.json` | Self-updating catalog pipeline (watch folder, chunk, embed, upsert) |

## Stack

n8n, Supabase Vector, OpenAI (chat + embeddings), RAG, Telegram.

## Import and setup

1. Import both JSONs into n8n.
2. Create credentials: OpenAI, Supabase, Telegram. Credential references are name-only placeholders.
3. Point the ingestion workflow at your own catalog folder and Supabase project.

## Note on redaction

All credentials, webhook IDs, and file IDs have been replaced with self-describing placeholders. The workflow logic is exactly what runs in the demo.

---

Built by [Moamen Elsharkawy](https://www.linkedin.com/in/moamen--elsharkawy/), AI Automation Engineer. More builds: [portfolio](https://www.notion.so/Moamen-Elsharkawy-AI-Automation-Specialist-c201df9dd81482998591011f978b1bda) | [GitHub profile](https://github.com/Moamen-Elsharkawy)
