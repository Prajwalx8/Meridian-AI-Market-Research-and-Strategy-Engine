<div align="center">

# Architecture
### How Meridian AI Research Engine is structured

<img src="https://img.shields.io/badge/pattern-multi--agent_pipeline-534AB7?style=for-the-badge&labelColor=1a1a1a" />
<img src="https://img.shields.io/badge/frontend-React_%2B_Vite-646cff?style=for-the-badge&labelColor=1a1a1a" />
<img src="https://img.shields.io/badge/backend-FastAPI-009688?style=for-the-badge&labelColor=1a1a1a" />

</div>

## Design Principles
1. **Traceability first** — every important finding should connect back to evidence and sources.
2. **Specialized agents** — each stage has a focused responsibility.
3. **Structured outputs** — agents exchange predictable schemas.
4. **Fail fast** — weak or empty stage outputs are detected early.
5. **Independent deployment** — frontend and backend communicate through APIs.

## System Layers
| Layer | Responsibility |
|---|---|
| Frontend | Research input, dashboard, pipeline visualization, report viewer |
| Backend | API, orchestration, agent execution, business logic |
| Data Layer | Jobs, sources, evidence, validations, reports |

## Multi-Agent Pipeline
```mermaid
flowchart LR
    A[Research Query] --> B[Planning Agent]
    B --> C[Research Agent]
    C --> D[Evidence Extraction]
    D --> E[Validation Agent]
    E --> F[Citation Agent]
    F --> G[Report Agent]
    G --> H[Linking Agent]
    H --> I[Traceable Research Report]
```

## End-to-End Data Flow
```mermaid
sequenceDiagram
    participant U as User
    participant FE as Frontend
    participant API as FastAPI
    participant P as AI Pipeline
    participant DB as Database

    U->>FE: Submit research query
    FE->>API: Create research job
    API->>P: Execute agents
    P->>DB: Store artifacts
    P-->>API: Final report
    API-->>FE: Research result
    FE-->>U: Report + Evidence + Sources
```

## Agent Responsibilities
- **Planning:** Converts a broad question into research tasks.
- **Research:** Discovers relevant and credible sources.
- **Extraction:** Extracts structured evidence from source material.
- **Validation:** Evaluates evidence quality and confidence.
- **Citation:** Maps claims to supporting sources.
- **Report:** Synthesizes findings into a structured report.
- **Linking:** Connects report claims with evidence for traceability.

## State Management
Persistent state should include research jobs, tasks, sources, evidence, validation results, citations, and reports. Temporary execution state should remain inside the pipeline runtime unless progress persistence is explicitly required.
