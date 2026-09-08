<div align="center">

# Contributing to Meridian

<img src="https://img.shields.io/badge/PRs-welcome-2e7d32?style=for-the-badge&labelColor=1a1a1a" />

</div>

## Before You Start
- Review the existing architecture and documentation.
- Keep changes focused on one feature or issue.
- Never commit secrets, API keys, or `.env` files.
- Update documentation when behavior changes.

## Local Setup
1. Fork and clone the repository.
2. Create the required environment files.
3. Install backend dependencies.
4. Install frontend dependencies.
5. Configure required API keys and database credentials.
6. Run frontend and backend locally.
7. Execute a sample research query before making changes.

## Branching
Use descriptive prefixes:
- `feat/`
- `fix/`
- `docs/`
- `refactor/`
- `test/`
- `chore/`

Example:
```text
feat/add-source-confidence-score
```

## Commit Messages
Use Conventional Commit style:
```text
<type>(<scope>): <short summary>
```

Examples:
```text
feat(pipeline): add validation retry logic
fix(api): handle invalid research job id
docs(architecture): update agent data flow
```

## Pull Requests
Before opening a PR:
- [ ] Code runs locally.
- [ ] Relevant tests pass.
- [ ] No secrets are included.
- [ ] Documentation is updated.
- [ ] UI changes include screenshots where useful.
- [ ] New API behavior is reflected in `API.md`.

## Where Changes Go
| Change | Suggested Area |
|---|---|
| Agent logic | AI pipeline / agents |
| API endpoint | Backend API routes |
| Database schema | Migrations |
| UI page | Frontend pages/components |
| Deployment | `DEPLOYMENT.md` |
| Testing | `TESTING.md` |

## Reporting Bugs
Include expected behavior, actual behavior, reproduction steps, logs with secrets removed, and screenshots when applicable.

## Proposing Features
Describe the user problem first, then explain the proposed solution and expected impact.
