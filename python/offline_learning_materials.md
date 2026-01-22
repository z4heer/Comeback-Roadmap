# Offline Learning Materials — Python Backend Senior Track

Purpose: Curated printable books, PDFs, cheat-sheets, and templates you can download and print for offline study. Grouped by topic and prioritized for senior-level backend work.

Core books & long-form references (print / PDF)
- "Designing Data-Intensive Applications" — Martin Kleppmann  
  - Why: Systems design patterns, consistency, partitioning, replication. Essential for senior design decisions.
- "Site Reliability Engineering" (Google SRE book)  
  - Why: Runbooks, incident response, SLOs, monitoring.
- "High Performance Browser Networking" (for HTTP internals) — Ilya Grigorik  
  - Why: Deep HTTP/TCP/latency knowledge.
- "Database Internals" — Alex Petrov  
  - Why: Storage engines, indexing, compaction, and IO performance.
- "Production-Ready Microservices" — Susan J. Fowler (or similar)  
  - Why: Operational patterns for services.
- "Fluent Python" — Luciano Ramalho  
  - Why: Advanced Python idioms and performance.
- "Python Cookbook" — David Beazley & Brian K. Jones  
  - Why: Useful recipes for common Python problems.
- "The Art of Monitoring" — James Turnbull  
  - Why: Practical monitoring and observability techniques.

Python backend-specific references (printable docs)
- FastAPI official docs (download/print relevant sections)  
- SQLAlchemy + Alembic docs (core patterns and best practices)  
- Celery docs (worker patterns, retries, routing) OR RQ docs  
- OpenAPI/Swagger specification (reference)  
- OpenTelemetry / Prometheus / Grafana docs (instrumentation guides)

Cheat-sheets & quick references (printable)
- Python standard library quick reference  
- SQL cheat-sheet: joins, indexes, explain plan tips  
- HTTP & REST cheat-sheet: status codes, headers, content-types, caching headers  
- Git cheat-sheet (branching, rebase, cherry-pick)  
- Docker & kubectl quick commands cheat-sheet  
- SQLAlchemy ORM / Alembic commands cheat-sheet  
- Prometheus metrics types and common instrumentation patterns

Printable templates (Markdown templates to fill and print)
- ADR template (Architecture Decision Record)  
- PRD & feature brief template  
- OpenAPI stub (skeleton)  
- Runbook / incident playbook template  
- Postmortem template (Root cause, timeline, action items)  
- Release checklist template  
- Test plan & integration test checklist

Offline exercises & labs (printable lab instructions)
- Lab: Design an API and write an OpenAPI spec + contract tests (Postman/Pact).  
- Lab: Implement an idempotent POST with idempotency key, create tests that retry; capture logs/metrics.  
- Lab: Add background worker with retry/backoff, simulate failures and DLQ handling.  
- Lab: Simulate high allocation and produce a heap dump; practice analysing memory leak (step-by-step).  
- Lab: Run load test (k6) and produce a simple performance report; tune DB indexes based on EXPLAIN.  
- Lab: Deploy app via Docker Compose, then to minikube; practice creating a Helm chart.

Printable study checklists (one-page)
- API readiness checklist (contract, validation, pagination, rate-limiting)  
- Observability checklist (logs, metrics, traces, alerts)  
- Security checklist (secrets, auth, tokens, TLS, OWASP top-10)  
- Production readiness checklist (health checks, backups, metrics, SLOs, rollbacks)

Offline tools & notes to download (recommendations)
- Local environment: Docker Desktop, minikube, docker-compose  
- Postman or Insomnia (exported collections)  
- k6 or locust test plans (export to local files)  
- Prometheus + Grafana compose files and example dashboards (JSON)  
- Example Terraform module templates for RDS/ECR/EKS (store offline)

Printable learning packs (what to print per week)
- Week 1: API design + data modeling pack (OpenAPI stub, ERD printouts, SQL cheat-sheet)  
- Week 2: Concurrency & async pack (Celery cheats, threadpool/async cheats, code examples)  
- Week 3: Testing & CI pack (unit/integration checklist, pytest patterns, CI YAML example)  
- Week 4: Observability & ops pack (runbook template, Prometheus/Grafana cheat)  
- Week 5: Deployment & infra pack (Dockerfile checklist, k8s manifests, Terraform examples)  
- Week 6: Performance & security pack (load test guide, security checklist, GC/profiling cheats)

Where to get or convert to offline PDFs
- O’Reilly books (download via account for offline use if licensed).  
- Official docs often have printable HTML pages or PDF exports (FastAPI, SQLAlchemy, Celery, OpenTelemetry). Use wget or website ‘print to PDF’.  
- Generate cheat-sheets and templates from the included Markdown files.

Recommended printable filenames (repo)
- README.md (project overview)  
- ARCHITECTURE.md + architecture.svg  
- openapi.yaml  
- ADRs/0001-auth-model.md  
- migrations/ (alembic)  
- runbook.md  
- monitoring/grafana-dashboard.json  
- tests/coverage-report.html

Citation & licensing note
- Respect book/publisher licenses—only download/print materials you are licensed to use. For open-source docs, prefer the official pages and include the document source/URL in your printed pack.
