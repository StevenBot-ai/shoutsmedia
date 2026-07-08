# Security Rules

## Secrets
- NEVER commit API keys, passwords, tokens, or credentials to the repo
- ALWAYS load sensitive values from environment variables (`.env`, never hardcoded in source)
- ALWAYS confirm `.env` and other secret files are listed in `.gitignore` before the first commit
- If a secret is ever committed, treat it as compromised: rotate it immediately, then scrub it from history

## Dependencies
- Review new dependencies before adding them — check maintenance status and known vulnerabilities
- Keep dependencies up to date and address security advisories promptly

## Input Handling
- Treat all external input (user input, API responses, file uploads) as untrusted
- Validate and sanitize input at system boundaries
- Use parameterized queries — never build SQL/NoSQL queries via string concatenation
- Nomination form submissions must be sanitized server-side before storage or email relay (Phase 2)

## Common Vulnerabilities to Avoid
- SQL/NoSQL injection
- Cross-site scripting (XSS) — especially in any user-submitted nomination content rendered to the page
- Cross-site request forgery (CSRF)
- Insecure direct object references
- Server-side request forgery (SSRF)

## If You Find a Problem
- If you discover exposed secrets or a security vulnerability, stop immediately and report it — do not silently patch and move on
