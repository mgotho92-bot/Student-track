# Student-track — Student Quiz Platform

This scaffold provides a minimal student quiz platform:

- Backend: Node.js + Express + Prisma (PostgreSQL)
- Frontend: React + Vite
- Features: create quizzes (nested questions + choices), list quizzes, take quizzes, submit answers and record submissions

Quick start (uses docker-compose for local Postgres)

1. Copy files into your repository.
2. Start Postgres:
   - docker-compose up -d
3. Backend:
   - cd backend
   - cp .env.example .env (update DATABASE_URL if needed)
   - npm install
   - npx prisma migrate dev --name init
   - npm run dev
4. Frontend:
   - cd frontend
   - npm install
   - cp .env.example .env (if you want to set VITE_API_URL)
   - npm run dev

API endpoints (examples)
- GET /api/quizzes
- GET /api/quizzes/:id
- POST /api/quizzes            (create quiz with nested questions & choices)
- POST /api/quizzes/:id/submit (submit answers and receive score)

Notes
- This scaffold uses Prisma with PostgreSQL. For quick testing you can use SQLite by adjusting prisma/schema.prisma datasource.
- Authentication is intentionally minimal (requests include userId). I can add JWT/email sign-in next.