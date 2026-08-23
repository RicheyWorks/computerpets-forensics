# Forensics

**Log Analyzer** — Dev tool to parse Java, GPU, and overlay crash logs into a Bounty-ready report.

Part of the [ComputerPets](https://github.com/RicheyWorks/computerpets) ecosystem. Index: [computerpets-ecosystem](https://github.com/RicheyWorks/computerpets-ecosystem).

> Status: **design scaffold**. This repository ships the contract, README, and layout so implementation can start without renaming the organ later.

## Why it exists

Desktop + Spring + CUDA means ugly stacks. Forensics turns a folder of logs into a severity, a fingerprint, and a redacted gist.

The flagship overlay already puts a living sticker on the real desktop (Rui first, 210 kinds). Forensics does not replace that. It is one organ.

## Stack

Python 3.12 · CLI · Java hs_err / GPU crash parsers · Electron/Node overlay logs · redaction

GroupId / namespace: `com.enterprisepet.forensics`  
Default listen: `CLI`

## Talks to

- computerpets-bounty
- computerpets-patcher
- computerpets-telemetry
- computerpets-stampede

## Contract

### Data

`Crash(kind=java|gpu|overlay, fingerprint) · Redaction(home, token, steamId) · Report(md, severity)`

### Surface

- CLI: forensics parse ./logs
- CLI: forensics fingerprint — cluster crashes
- POST /v1/ingest — optional CI hook

### Failure doctrine

Unknown format → keep raw in an appendix. PII regex miss → default strip user profile paths. Never upload without --share.

## Layout

```
computerpets-forensics/
  README.md           this file
  LICENSE             MIT
  docs/CONTRACT.md    the same contract, frozen for implementers
  src/                implementation lands here
```

## Run (Windows)

PowerShell, from this folder, after the flagship helpers (Git, Node LTS 22+, JDK 21 as needed):

```powershell
python -m venv .venv; pip install -e .; forensics parse .\logs
```

You do not need this service to meet Rui. The [flagship start-here](https://github.com/RicheyWorks/computerpets/blob/main/docs/START-HERE.md) is still the first pet.

## Ecosystem

| Organ | Repo |
| --- | --- |
| Flagship desktop + Spring | [RicheyWorks/computerpets](https://github.com/RicheyWorks/computerpets) |
| This organ | [RicheyWorks/computerpets-forensics](https://github.com/RicheyWorks/computerpets-forensics) |
| Full map | [RicheyWorks/computerpets-ecosystem](https://github.com/RicheyWorks/computerpets-ecosystem) |

## License

MIT. See [LICENSE](LICENSE).

---

*Two hundred ten living kinds. Keep them so a line does not go quiet.*
