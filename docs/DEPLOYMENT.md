<div align="center">

# Deployment Guide
### Deploying Meridian AI Research Engine

<img src="https://img.shields.io/badge/frontend-Vercel-000000?style=for-the-badge&labelColor=1a1a1a" />
<img src="https://img.shields.io/badge/backend-FastAPI-009688?style=for-the-badge&labelColor=1a1a1a" />

</div>

## Overview
Meridian can be deployed as independently managed frontend and backend services. The frontend communicates with the backend through the configured production API URL.

## 1. Prepare Environment Variables
Example backend variables:
```env
GOOGLE_API_KEY=
TAVILY_API_KEY=
SUPABASE_URL=
SUPABASE_KEY=
CORS_ORIGINS=
```

Example frontend variables:
```env
VITE_API_BASE_URL=
VITE_SUPABASE_URL=
VITE_SUPABASE_ANON_KEY=
```

## 2. Deploy Backend
Deploy the FastAPI service to a Python-compatible platform.

Typical command:
```bash
uvicorn backend.main:app --host 0.0.0.0 --port $PORT
```

Verify:
```text
GET /health
```

## 3. Deploy Frontend
Deploy the React/Vite application to Vercel or another static hosting provider.

Build command:
```bash
npm run build
```

## 4. Configure CORS
Add the deployed frontend URL to:
```env
CORS_ORIGINS=https://your-frontend-domain.com
```

## 5. Verify Production
Check:
- Authentication
- Research job creation
- Agent pipeline execution
- Source retrieval
- Evidence traceability
- Final report rendering
- Error handling

## Deployment Checklist
- [ ] Production environment variables configured
- [ ] Secrets not exposed to frontend
- [ ] Backend health endpoint working
- [ ] Frontend points to production API
- [ ] CORS configured
- [ ] Database migrations applied
- [ ] End-to-end research workflow tested
