# DeepRead Web App

A deployable web UI for [DeepRead](https://www.deepread.tech) — AI-native document processing with 97%+ accuracy.

## Deploy on Railway

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/template/deepread)

After deploying, set `DEEPREAD_API_KEY` as an environment variable. Get a free key (2,000 pages/month, no credit card) at [deepread.tech/dashboard](https://www.deepread.tech/dashboard).

## What DeepRead Does

DeepRead is a complete document AI platform with four capabilities, one API:

- **OCR & Structured Extraction** — Extract text or typed JSON fields from PDFs and images with confidence scoring and human-in-the-loop flags
- **PDF Form Filling** — Fill blank PDF forms with AI vision (works on scanned, non-editable forms — no AcroForm required)
- **PII Redaction** — Detect and redact 14 types of PII (names, SSNs, credit cards, medical records, etc.) with irreversible black bars, built for HIPAA/GDPR redaction workflows
- **Bring Your Own Key (BYOK)** — Connect your own OpenAI, Google, or OpenRouter API key — pay zero DeepRead LLM costs, page quota skipped entirely

## What This Web App Does

Three modes via simple drag-and-drop UI:

- **OCR Extract** — Upload PDF/image, get extracted text
- **Structured JSON** — Define a schema, get typed fields with confidence scores
- **PII Redact** — Remove 14 PII types with irreversible black bars

## Local Development

```bash
git clone https://github.com/deepread-tech/deepread-webapp.git
cd deepread-webapp
pip install -r requirements.txt
export DEEPREAD_API_KEY=sk_live_your_key
python app.py
# Open http://localhost:8080
```

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `DEEPREAD_API_KEY` | Yes | Get free at [deepread.tech/dashboard](https://www.deepread.tech/dashboard) |
| `PORT` | No | Defaults to 8080 (Railway sets this automatically) |

## Stack

- Python 3.10+
- Flask (web framework)
- Gunicorn (production server)
- Requests (HTTP client for DeepRead API)

## Endpoints

- `GET /` — Upload UI
- `POST /extract` — Process document (returns DeepRead API response)
- `GET /health` — Health check (used by Railway)

## More from DeepRead

- **Examples**: [github.com/deepread-tech/deepread-demo](https://github.com/deepread-tech/deepread-demo) — Python, Node.js, cURL examples for OCR, structured extraction, form fill, PII redaction
- **n8n Node**: [n8n-nodes-deepread](https://www.npmjs.com/package/n8n-nodes-deepread) — drag-and-drop in n8n workflows
- **Claude Code**: `/plugin install deepread@claude-community`
- **Universal (50+ AI agents)**: `npx skills add deepread-tech/skills`

## License

MIT
