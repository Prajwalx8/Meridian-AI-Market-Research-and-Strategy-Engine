<div align="center">

# Evaluation & Reliability
### Measuring the quality of Meridian research outputs

</div>

## Goals
Meridian should produce research that is:
- Relevant
- Evidence-backed
- Traceable
- Consistent
- Transparent about uncertainty

## Evaluation Dimensions
| Dimension | Question |
|---|---|
| Planning Quality | Are research tasks relevant to the query? |
| Source Quality | Are sources credible and useful? |
| Evidence Quality | Does extracted evidence support the claim? |
| Validation | Is confidence assigned consistently? |
| Citation Accuracy | Does each citation support the linked claim? |
| Report Quality | Is the final synthesis coherent and complete? |

## Reliability Mechanisms
### 1. Structured Agent Outputs
Each stage should return predictable fields to reduce downstream ambiguity.

### 2. Stage-Level Validation
Validate outputs before sending them to the next agent.

### 3. Fail-Fast Behavior
If a critical stage produces unusable results after retries, mark the job as failed rather than generating unsupported content.

### 4. Evidence Traceability
Maintain links:
```text
Report Claim → Citation → Evidence → Source
```

### 5. Retry Strategy
Transient model or network failures can be retried with bounded attempts and clear error logging.

## Suggested Metrics
- Research completion rate
- Average pipeline duration
- Sources per job
- Evidence items per source
- Citation coverage
- Validation confidence distribution
- Failed stage rate
- Unsupported claim rate

## Manual Evaluation Checklist
- [ ] Research tasks cover the original question
- [ ] Sources are relevant
- [ ] Evidence is grounded in sources
- [ ] Claims have supporting citations
- [ ] Uncertainty is visible
- [ ] Final report answers the user query
