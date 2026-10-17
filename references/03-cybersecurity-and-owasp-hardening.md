# Cybersecurity & OWASP Web Application Hardening

## 1. OWASP Top 10 Core Defenses

| Vulnerability | Threat Vector | Primary Defense |
|---|---|---|
| **A01: Broken Access Control** | Unauthorized data access / IDOR | Enforce authorization checks at controller/handler level. Never trust client-supplied IDs. Verify `req.user.id == resource.owner_id`. |
| **A02: Cryptographic Failures** | Plaintext secrets / weak ciphers | Use Argon2id or bcrypt (cost >= 12) for passwords. Enforce TLS 1.3 in transit and AES-256-GCM at rest. Zero hardcoded keys. |
| **A03: Injection** | SQLi, Command Injection, NoSQLi | Always use parameterized queries (prepared statements). Never concatenate user strings into SQL or shell commands. |
| **A04: Insecure Design** | Architectural oversights | Threat model before implementation. Limit rate limits on sensitive endpoints (auth, password reset, payment). |
| **A05: Security Misconfiguration** | Default credentials / exposed stacks | Strip stack traces from production responses. Disable directory listing. Configure restrictive CORS headers. |
| **A06: Vulnerable Dependencies** | Outdated packages / CVEs | Run automated dependency audits (`npm audit`, `pip check`). Pin explicit package versions. |
| **A07: Identification & Auth Failures** | Credential stuffing / brute force | Enforce rate limiting (e.g. 5 failed attempts per IP/minute), multi-factor authentication (MFA), and secure session cookies (`HttpOnly`, `Secure`, `SameSite=Strict`). |
| **A08: Software & Data Integrity** | Tampered payloads / insecure deserialization | Sign sensitive webhooks with HMAC-SHA256 signatures. Validate schemas strictly before parsing. |
| **A09: Logging & Monitoring Failures** | Undetected breaches | Log all authentication events, privilege escalations, and input validation failures. Never log passwords, tokens, or PII. |
| **A10: Server-Side Request Forgery (SSRF)** | Fetching internal metadata / cloud IPs | Maintain a strict protocol and host allowlist for outgoing requests. Block `169.254.169.254`, `localhost`, and internal IP subnets (`10.0.0.0/8`, `192.168.0.0/16`). |

---

## 2. API Security Protocol
- **Input Validation**: Use runtime validation libraries (Zod, Pydantic) to reject unexpected fields or malformed inputs.
- **Rate Limiting**: Implement token-bucket or sliding-window rate limiting on all public API endpoints.
- **CORS Configuration**: Explicitly whitelist authorized origins instead of wildcard `*`.
