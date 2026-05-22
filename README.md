# BeForma Workout Plan API

Personalized workout plan generator with 50 English exercises and local images.

## Tech Stack

- **Framework**: Python 3.11 + FastAPI
- **Server**: Uvicorn (ASGI)
- **Deployment**: Docker on Railway

## API Endpoints

| Method | Path | Description |
|--------|------|-------------|
| GET | `/` | API info |
| GET | `/health` | Health check |
| GET | `/api/v1/workout/exercises` | List all exercises |
| POST | `/api/v1/workout/generate-plan` | Generate workout plan |

## Local Development

```bash
cd beforma_workout_plan_api_package_50
pip install -r requirements.txt
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

Open: http://127.0.0.1:8000/docs

## Railway Deployment

This repository is configured for one-click Railway deployment:

1. Connect this GitHub repo in Railway
2. Railway will auto-detect the `Dockerfile` at the repo root
3. The app binds to the `PORT` environment variable provided by Railway
4. Health check endpoint: `/health`

### Environment Variables (optional)

| Variable | Default | Description |
|----------|---------|-------------|
| `PORT` | `8080` | Server port (set by Railway automatically) |
| `BEFORMA_API_KEY` | _(empty)_ | API key for authentication (optional) |
| `ALLOWED_ORIGINS` | `*` | CORS allowed origins (comma-separated) |

## Sample Request

```json
{
  "age": 24,
  "weight_kg": 78,
  "activity_level": "moderately_active",
  "primary_goal": "lose_weight",
  "injuries": ["knee"],
  "experience_level": "beginner",
  "equipment": "gym",
  "days_per_week": 4
}
```