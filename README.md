# PocketSmart AI

A complete FastAPI + Jinja2 + SQLite + Gemini recommendation assistant for Home Interior, Party Planning, and Jewelry recommendations.

## Implementation choices

The supplied document mixes Flask/FastAPI and refers to Gemini 1.5 Flash Pro. This implementation standardizes on FastAPI and Google's current GenAI Python SDK. `GEMINI_MODEL` is configurable. If no Gemini API key is configured, deterministic local recommendations are returned so the application still works end-to-end.

Retailer integrations are implemented as a local catalog adapter with platform search links rather than unofficial scraping.

## Quick start

```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate
pip install -r requirements.txt
copy .env.example .env
# macOS/Linux: cp .env.example .env
uvicorn app.main:app --reload
```

Open http://127.0.0.1:8000

## Gemini

Put your Gemini API key in `.env` as `GEMINI_API_KEY=...`, choose a currently available model in `GEMINI_MODEL`, then restart the server.

## Tests

`pytest -q`

## Useful URLs

- `/` home
- `/login`, `/register`, `/dashboard`, `/history`
- `/planner/home`, `/planner/party`, `/planner/jewelry`
- `/docs` FastAPI API documentation
- `/health`
