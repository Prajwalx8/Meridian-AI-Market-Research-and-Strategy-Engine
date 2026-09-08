<div align="center">

# Security Policy
### Security practices for Meridian AI Research Engine

</div>

## Supported Security Areas
Security improvements are relevant to:
- Authentication
- API authorization
- Secret management
- Database access
- CORS configuration
- Dependency vulnerabilities

## Reporting a Vulnerability
Do not publish sensitive vulnerabilities, API keys, tokens, or exploit details in public issues.

Provide:
1. A description of the vulnerability
2. Affected component
3. Reproduction steps
4. Potential impact
5. Suggested mitigation, if available

## Secret Management
Never commit:
```text
.env
API keys
service-role keys
access tokens
database passwords
private certificates
```

Use environment variables and deployment platform secret managers.

## Authentication and Authorization
- Verify tokens server-side.
- Check ownership before returning job-scoped data.
- Apply least-privilege access.
- Keep elevated database credentials on the backend only.

## Frontend Security
The frontend should never contain privileged credentials. Public configuration values must not provide unrestricted database or backend access.

## CORS
Production APIs should only accept approved origins.

## Dependency Security
Regularly review dependencies and update vulnerable packages.

## Security Checklist
- [ ] No secrets committed
- [ ] Authentication enabled where required
- [ ] Authorization checks applied
- [ ] Production CORS restricted
- [ ] Dependencies reviewed
- [ ] Error messages do not expose secrets
