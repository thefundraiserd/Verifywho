# VerifyWho - Current Package (MVP backend)

This ZIP contains the current VerifyWho backend code (FastAPI) and assets available right now.

## Contents
- app/main.py — FastAPI backend with lookup and message-check endpoints.
- requirements.txt — Python dependencies.
- .env.example — environment variable template.
- logo.png — logo image if present.

## Quick local run (for testing)
1. Create a Python 3.10+ virtual environment:
   ```
   python -m venv venv
   source venv/bin/activate   # macOS/Linux
   venv\Scripts\activate      # Windows
   ```
2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Set your OpenAI key in the environment:
   ```
   export OPENAI_API_KEY="sk-..."
   ```
   or on Windows:
   ```
   set OPENAI_API_KEY=sk-...
   ```
4. Run the app:
   ```
   uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
   ```
5. Open `http://localhost:8000/docs` to see and test the endpoints (`/lookup` and `/check-message`).

## Deploying to Render (simple)
1. Push this repo to GitHub.
2. Create a new Web Service on Render and connect to the GitHub repo.
3. Set the start command to:
   ```
   uvicorn app.main:app --host 0.0.0.0 --port ${PORT:-10000}
   ```
4. Add environment variables on Render:
   - `OPENAI_API_KEY` = your key
5. Deploy. Render will provide a public URL.

## Notes
- This package is the current starting point. Frontend, admin UI, and database persistence are not included in this ZIP yet.
- I can produce a full repo (frontend + admin UI) next—tell me if you want that.

