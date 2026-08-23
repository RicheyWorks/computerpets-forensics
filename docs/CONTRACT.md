# Forensics contract

Do not implement against folklore. Implement against this file.

## Identity

- Product: **Forensics**
- Repo: `computerpets-forensics`
- Category: Utility Tools
- Idea: Log Analyzer
- Port / surface: `CLI`

## Must

- Stay canon with 210 species. No illegal hybrids. No swapped voices.
- Treat the desktop overlay as the main quest. This organ is optional until wired.
- Fail soft: the overlay keeps walking if this service is down, unless this *is* the overlay.
- No PII in public artifacts (Steam id, wallet, home path, webcam frames).

## Data

Crash(kind=java|gpu|overlay, fingerprint) · Redaction(home, token, steamId) · Report(md, severity)

## Surface

- CLI: forensics parse ./logs
- CLI: forensics fingerprint — cluster crashes
- POST /v1/ingest — optional CI hook

## Neighbors

- computerpets-bounty
- computerpets-patcher
- computerpets-telemetry
- computerpets-stampede

## Failure doctrine

Unknown format → keep raw in an appendix. PII regex miss → default strip user profile paths. Never upload without --share.

## Stack

Python 3.12 · CLI · Java hs_err / GPU crash parsers · Electron/Node overlay logs · redaction
