# AuraAI

AI Agent application with real-time streaming chat — Flutter frontend + FastAPI backend.

## Prerequisites

- Flutter SDK ^3.7.2
- Python >= 3.12
- PostgreSQL
- [uv](https://docs.astral.sh/uv/getting-started/installation/)

## Backend Setup

```bash
cd backend
cp .env.example .env
# Fill in your values in .env (DATABASE_URL, SECRET_KEY, DEEPSEEK_API_KEY)

uv sync
uv run scripts/init_db.py
uv run scripts/init_config.py

python main.py        # Development
python main.py prod   # Production (Gunicorn)
```

## Frontend Setup

```bash
# From project root
flutter pub get
flutter gen-l10n
flutter run           # Run on device/emulator
flutter build web --wasm  # Build for web
```

## Docker (Full Stack)

```bash
cp backend/.env.example backend/.env
# Edit backend/.env with your values

docker compose up -d
```

## Environment Variables

| Key | Description |
|-----|-------------|
| `DATABASE_URL` | PostgreSQL connection URL |
| `SECRET_KEY` | JWT secret key |
| `DEEPSEEK_API_KEY` | DeepSeek API key |
| `BACKEND_CORS_ORIGINS` | Allowed CORS origins |

## API Docs

```
http://127.0.0.1:8000/docs
```
