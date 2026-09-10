# Exotics Member Security Baseline — v4.3.2

This document defines the security baseline for the future Member, Newsletter, Reading History, 7-Day Login and Gacha services.

## ISO/IEC 27001 alignment

The implementation is designed to support an ISO/IEC 27001:2022-aligned security baseline. This is not a certification or a claim of organizational compliance. Formal compliance requires an ISMS, risk assessment, policies, evidence, controls, audits and continual improvement.

## Mandatory controls

- HTTPS/TLS for all production traffic.
- Server-side email validation and normalization.
- Email verification before Member ACTIVE state.
- Domain selection in the UI; custom domains validated server-side.
- No passwords in the initial member flow; prefer passwordless magic link/OTP.
- OTP expiry, one-time use, attempt limits and request rate limits.
- Secure, HttpOnly, SameSite cookies for authenticated sessions.
- No authentication tokens in localStorage.
- Rate limiting and anti-bot controls on signup, verification and login.
- Generic authentication errors to reduce account enumeration.
- Member ID as the internal identifier; do not use email as a database foreign key.
- Encryption in transit and at rest for member/PII data.
- Least-privilege RBAC for member, editorial and administrative access.
- MFA for administrative access.
- Audit logs for security-sensitive actions without unnecessary PII.
- Data retention and deletion procedures.
- Encrypted backups and tested recovery procedures.
- Security headers including CSP, HSTS, Referrer-Policy, X-Content-Type-Options and Permissions-Policy at the web server/CDN layer.
- Dependency and supply-chain vulnerability scanning.
- Server-side authorization for reading history, streak, XP, eligibility and rewards.
- Server-side cryptographically secure randomness for Gacha.
- Idempotency/transaction protection to prevent duplicate spins or rewards.
- Never trust client-provided streak, XP, read-completion or reward state.

## Data boundary

Google Sheets remains read-only editorial source data. Member/PII data must be stored in a separate protected member service/database. The public browser must never write editorial data to Google Sheets.

## Current static build limitation

The static prototype cannot enforce server-side authentication, authorization, rate limiting, cryptographic randomness, database encryption or audit controls by itself. The local newsletter gate and streak state are UI/demo mechanisms only and must not be treated as production security controls.
