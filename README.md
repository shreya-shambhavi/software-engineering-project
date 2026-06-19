# AI Agent for Academic Guidance

A concise AI-powered academic assistant for students and instructors. This repository contains the backend and frontend components that provide:

- Context-aware AI chatbot (RAG) for academic help
- Course management (enroll, drop, list)
- Notes, transcripts, and resource access
- Course-specific chatrooms and messaging

This project was developed as part of an academic software engineering program.

## Features

- AI chatbot using retrieval-augmented generation (Gemini + ChromaDB)
- Course enrollment and management APIs
- Notes and transcript ingestion (PDF → embeddings)
- Real-time chatrooms per course
- Simple student dashboard with progress tracking

## Tech Stack

- Frontend: React, Tailwind CSS
- Backend: Python, Flask, Flask-RESTful
- Database: SQLite (development)
- Vector DB: ChromaDB for embeddings
- GenAI: Google Gemini (API)

## Quickstart

Prerequisites:

- Python 3.10+ and pip
- Node.js 16+ and npm

1) Clone the repository

```bash
git clone https://github.com/your-org/ai-agent-for-academic-guidance.git
cd ai-agent-for-academic-guidance
```

2) Backend (Windows example)

```powershell
python -m venv .venv
.\\.venv\\Scripts\\Activate.ps1
cd backend
pip install -r requirements.txt
# (optional) initialize embeddings/index
python pdf_embeddings.py
python run.py
# Backend runs at http://localhost:5000/
```

3) Frontend

```bash
cd frontend
npm install
npm run dev
# Frontend runs at http://localhost:5173/
```

Notes:
- Adjust commands for macOS/Linux virtualenv activation: `source .venv/bin/activate`.
- Ensure API keys for Gemini (or other LLM) are set as environment variables before starting the backend.

## API (Overview)

Authentication

- POST /api/v1/signup/ — Create a new user
- POST /api/v1/login/ — Login
- POST /api/v1/logout/ — Logout
- GET /api/v1/user/ — Current user

Courses

- GET /api/v1/courses/ — Get enrolled courses
- GET /api/v1/all-courses/ — List all courses
- POST /api/v1/courses/add — Enroll in course(s)
- POST /api/v1/courses/drop — Drop course(s)
- POST /api/v1/courses/change — Replace enrolled courses

Notes

- POST /api/v1/notes/ — Create note
- GET /api/v1/notes/ — List notes
- PUT /api/v1/notes/{noteId} — Update note
- DELETE /api/v1/notes/{noteId} — Delete note

Chatrooms & Messaging

- GET /api/v1/chatrooms/ — List chatrooms
- GET /api/v1/chatrooms/{courseId} — Course chatroom
- POST /api/v1/messages/ — Send message

AI Chat

- POST /v1/chat/ — Query the AI assistant (uses Gemini + ChromaDB context)

## Development

- Run backend tests: `pytest` (from the `backend` folder)
- Linting/formatting: follow project Python and JS standards
- Use environment variables for secrets and API keys

## Contributing

Contributions are welcome. Please open issues or PRs and follow the repo's contribution guidelines.

## License & Contact

This project is provided for academic purposes. Specify a license if you plan to publish.

Questions? Open an issue or contact the maintainers.