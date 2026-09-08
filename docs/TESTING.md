<div align="center">

# Testing Guide
### Testing Meridian AI Research Engine

</div>

## Testing Strategy
Testing should cover:
1. Individual agents
2. Pipeline integration
3. API behavior
4. Frontend interactions
5. End-to-end traceability

## Unit Tests
Test isolated behavior such as:
- Query validation
- Task generation
- Source parsing
- Evidence extraction schemas
- Confidence calculations
- Citation linking

## Integration Tests
Verify:
```text
Planner → Research → Extraction → Validation → Citation → Report → Linking
```

Check that outputs from one stage are valid inputs for the next.

## API Tests
Test:
- Valid requests
- Missing fields
- Invalid job IDs
- Unauthorized access
- Ownership restrictions
- Successful report retrieval

## End-to-End Test
1. Submit a realistic research query.
2. Confirm a research job is created.
3. Verify pipeline stages complete.
4. Inspect sources and evidence.
5. Verify validation results.
6. Open the final report.
7. Confirm claims are traceable to sources.

## Failure Testing
Test:
- Empty search results
- Invalid model response
- API timeout
- Missing environment variables
- Database errors
- Partial pipeline failures

## Suggested Commands
Use your repository's configured test commands, for example:
```bash
pytest
npm run test
npm run lint
```

## Pre-Release Checklist
- [ ] Backend tests pass
- [ ] Frontend checks pass
- [ ] API endpoints verified
- [ ] End-to-end research tested
- [ ] Traceability verified
- [ ] No secrets in logs or commits
