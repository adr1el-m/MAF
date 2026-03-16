# Voice AI Medical Triage MVP (Hackathon)

Quick prototype using React + Express + Agora + Web Speech API + LLM analysis.

## Structure

- `frontend/` React + Tailwind + Agora Web SDK
- `backend/` Express API with `POST /analyzeSymptoms`

## 1) Backend setup

```bash
cd backend
cp .env.example .env
npm install
npm run dev
```

Default mode is `LLM_PROVIDER=mock` for free local demo.

To use a free LLM endpoint:

- Set `LLM_PROVIDER=groq` (or `openrouter`, `together`)
- Add `LLM_API_KEY`
- Optionally set `LLM_MODEL`

## 2) Frontend setup

```bash
cd frontend
cp .env.example .env
npm install
npm run dev
```

Set these in `frontend/.env` if available:

- `VITE_AGORA_APP_ID`
- `VITE_AGORA_CHANNEL`
- `VITE_AGORA_TOKEN` (optional for testing if your Agora project allows)
- `VITE_API_BASE_URL=http://localhost:4000`

If Agora values are missing, app still works using local microphone transcription only.

## MVP Flow

1. Click **Start Triage**
2. Speak symptoms in English/Tagalog/Taglish
3. Click **Analyze Symptoms**
4. View urgency + doctor summary + recommendation
5. Check **Doctor Queue** page for urgency-sorted list

## Notes

- This is a demo prototype, not a medical device.
- Web Speech API works best in Chrome-based browsers.
