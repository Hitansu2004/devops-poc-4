# POC 4: Security + Code Quality Pipeline (GitHub Actions)

## Overview
A DevSecOps pipeline using GitHub Actions that automatically scans for code quality issues, security vulnerabilities, and dependency risks on every push.

| Security Tool | Purpose |
|--------------|---------|
| **SonarCloud** | Code quality, coverage, code smells |
| **CodeQL** | SAST — detects SQL injection, XSS, etc. |
| **OWASP Dependency Check** | CVE scanning of all npm/Maven dependencies |

## Pipeline Behaviour
- Push to `main` → triggers all 4 security scans automatically
- **Fails build** if OWASP finds CVSS ≥ 7 vulnerability
- **OWASP HTML report** uploaded as downloadable artifact on every run
- **CodeQL alerts** visible in GitHub → Security → Code Scanning

## GitHub Secrets Required
| Secret | Value |
|--------|-------|
| `SONAR_TOKEN` | Your SonarCloud token |
