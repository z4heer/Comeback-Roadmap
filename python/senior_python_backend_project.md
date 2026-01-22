# Senior Capstone Project: Resilient Order Fulfillment Platform (Python Backend)

Project summary
- Build a production-quality, resilient Order Fulfillment backend service that handles order intake, payment processing (simulated), inventory reservation, async fulfillment tasks, and exposes a stable API for clients. The system must be observable, test-covered, deployable via containers and IaC, and safe for retries (idempotent). This project exercises architecture, APIs, DB design, concurrency, async processing, performance, monitoring, security, and deployment.

Goals / learning outcomes
- Design a scalable API and data model for order lifecycle.  
- Implement synchronous and asynchronous flows (fast API responses, background workers).  
- Demonstrate transactional integrity, idempotency, and retry safety.  
- Implement observability (metrics, logs, traces) and health probes.  
- Create CI/CD pipeline, container images, Helm/K8s manifests or Compose for infra, and IaC for cloud resources.  
- Perform performance testing and basic chaos tests (simulated failures / retries).  
- Produce artifacts: ADRs, API OpenAPI spec, runbook, postmortem, test reports, monitoring dashboards.

Tech stack (recommended)
- Python backend: FastAPI (or Django REST Framework if preferred)  
- DB: PostgreSQL (schema + indexes + migrations via Alembic)  
- ORM: SQLAlchemy (or Django ORM)  
- Async worker: Celery or RQ with Redis as broker/result store (or use asyncio + background tasks)  
- Caching/queues: Redis  
- Auth: OAuth2/JWT (or session if needed)  
- Containerization: Docker, Docker Compose for local, Helm/K8s manifests for deployment  
- CI/CD: GitHub Actions (or GitLab CI)  
- IaC: Terraform for cloud infra (RDS, VPC, ECR, cluster)  
- Monitoring: Prometheus metrics, Grafana dashboards, OpenTelemetry traces  
- Testing: Pytest (unit + integration), pytest-cov, Postman collections for manual API checks  
- Load testing: k6 or locust  
- Linter/Formatter: black, flake8, isort

High-level features (minimal viable)
1. Orders API (POST /orders, GET /orders/{id}, GET /orders?status=)  
   - Request validation, schema, OpenAPI spec
2. Payment simulation endpoint (side-effecting), idempotent via idempotency-key header  
3. Inventory service (reserve/release), consistent via DB transactions  
4. Background worker to process fulfillment (retry/backoff, dead-letter handling)  
5. Webhook or event pub/sub simulation for downstream notifications  
6. Health endpoints (/health/live, /health/ready) and metrics (/metrics)  
7. Authentication: JWT-based auth for APIs, role-based checks for admin endpoints
8. Observability: structured logs, traces, metrics for key SLOs (latency, error rate, queue length)
9. Deployment: Docker images, Kubernetes manifests or Helm chart, Terraform infra definitions
10. Runbook + incident checklist + postmortem template

Deliverables / artifacts to produce (evidence for portfolio)
- README with setup and architecture overview (arch diagram)  
- ADRs (design decisions: DB choice, idempotency approach, worker model)  
- OpenAPI spec (openapi.yaml) and API examples (Postman collection)  
- Database schema, ER diagram, migration scripts (alembic)  
- Source code with unit & integration tests, coverage report  
- CI pipeline file (.github/workflows/ci.yml) and build artifact (Dockerfile)  
- Deployment manifests (k8s/helm) and Terraform scripts for infra  
- Observability dashboards (Grafana JSON) + sample Prometheus rules  
- Runbook.md, incident playbook and postmortem.md (if you run a simulated incident)  
- Performance report (k6/locust), profiling/heap dump and remediation notes  
- Final report: lessons learned, trade-offs, and resume-ready summary

Acceptance criteria / success metrics
- All API endpoints documented in OpenAPI and passing schema validation.  
- Unit test coverage >= 75% for core business logic.  
- Integration tests that run in CI using ephemeral test DBs (containerized).  
- Worker processes handle retries and do not produce duplicates (idempotency verified).  
- Deployment scripts can spin up a minimal environment locally (Compose) and in cloud (Terraform + Helm).  
- Metrics: 95th percentile latency under target (e.g., <200ms for simple endpoints) in baseline load tests.  
- Runbook and monitoring configured so an on-call engineer can diagnose and recover basic failures.

Stretch goals (senior-level)
- Implement leader election for scheduled tasks.  
- Multi-region failover simulation and graceful degradation.  
- Fine-grained RBAC and audit log for admin operations.  
- Use OpenTelemetry for end-to-end traces and create a performance heatmap.  
- Add canary deployments and feature flags for rollout testing.

Evaluation checklist (self-check)
- [ ] API contract stable and versioned  
- [ ] DB: indexes for common queries, explain analyzed for slow queries  
- [ ] Transactions used where invariants must hold, with minimal lock contention  
- [ ] Worker pool tuned and monitored (queue depth, worker count)  
- [ ] Logs structured and avoid PII; correlation IDs present across services  
- [ ] Secrets managed via Vault/KMS (no secrets in repo)  
- [ ] CI enforces lint, tests, and basic security scans (bandit/snyk)  
- [ ] Recreate production-like environment locally via Compose or minikube

Evidence to include in portfolio
- Link to repo, OpenAPI screenshot, architecture diagram, performance graphs, a short video walkthrough (2–5 minutes) showing API flow + logs + metrics + deployment run.

Estimated effort (senior)
- 8–12 weeks (part-time 10–20 hours/week) or 4–6 weeks (full-time sprint) depending on scope and stretch goals.
