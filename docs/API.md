<div align="center">

# API Reference
### Meridian AI Research Engine Backend

<img src="https://img.shields.io/badge/base_url-%2Fapi-185FA5?style=for-the-badge&labelColor=1a1a1a" />
<img src="https://img.shields.io/badge/docs-FastAPI_Swagger-009688?style=for-the-badge&labelColor=1a1a1a" />

</div>

## Overview
This document describes the API contract for the Meridian AI Research Engine. The backend accepts a research query, orchestrates the multi-agent pipeline, stores intermediate artifacts, and returns a traceable research report.

## Base URL
| Environment | URL |
|---|---|
| Local | `http://localhost:8000` |
| Production | Set through your deployed backend URL |

## Service Routes
| Method | Route | Purpose |
|---|---|---|
| `GET` | `/` | API metadata |
| `GET` | `/health` | Health check |

## Research Routes
### Create Research Job
```http
POST /api/research
```

```json
{
  "query": "Analyze the competitive landscape of the EV market"
}
```

### Get Research Jobs
```http
GET /api/research
```

### Get Research Job
```http
GET /api/research/{job_id}
```

## Traceability Routes
| Method | Route | Returns |
|---|---|---|
| `GET` | `/api/research/{job_id}/tasks` | Research plan |
| `GET` | `/api/research/{job_id}/sources` | Retrieved sources |
| `GET` | `/api/research/{job_id}/evidence` | Extracted evidence |
| `GET` | `/api/research/{job_id}/validations` | Validation results |
| `GET` | `/api/research/{job_id}/report` | Final report |

## Error Responses
| Status | Meaning |
|---|---|
| `400` | Invalid request |
| `401` | Authentication required |
| `403` | Access denied |
| `404` | Resource not found |
| `422` | Validation error |
| `500` | Internal server error |

## Interactive Documentation
When running locally, FastAPI documentation is available at:
- `/docs`
- `/redoc`
