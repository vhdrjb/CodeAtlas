# Mode: Infrastructure

**Purpose**: Analyze the deployment, operations, and infrastructure aspects of a project.

---

## Objective

The Infrastructure mode examines how a project is built, tested, deployed, and operated. It answers the question: "How does this project go from source code to a running system?" This mode is essential for DevOps engineers, SREs, and anyone responsible for deploying or maintaining the project.

Infrastructure analysis goes beyond listing tools. It evaluates the maturity of the deployment pipeline, the robustness of the operational setup, and the project's readiness for production workloads. It identifies gaps in monitoring, security hardening, and disaster recovery that could affect reliability.

---

## Analysis Scope

- **Build System**: How the project is compiled, bundled, or assembled — build tool configuration, scripts, and artifact generation.
- **Dependency Management**: How dependencies are declared, locked, and updated — package managers, lock files, and vulnerability scanning.
- **CI/CD Pipeline**: Continuous integration and deployment configuration — test execution, build triggers, deployment stages, and environment promotions.
- **Containerization**: Docker, container orchestration, and image management — Dockerfiles, docker-compose, Kubernetes manifests, Helm charts.
- **Environment Configuration**: How different environments (dev, staging, production) are managed — environment variables, config files, secrets management.
- **Database Management**: Migrations, schema versioning, seeding, backup strategies — migration files, ORM configurations, and database tooling.
- **Monitoring and Observability**: Logging, metrics, tracing, and alerting setup — log aggregation, APM integration, health check endpoints.
- **Security Practices**: Authentication, authorization, secrets handling, dependency scanning, and security headers.
- **Hosting and Deployment**: Where and how the application is deployed — cloud provider, serverless setup, CDN, domain configuration.

---

## Expected Inputs

- Infrastructure definition files: Dockerfile, docker-compose.yml, Kubernetes manifests, Terraform, CloudFormation, or Pulumi files.
- CI/CD configuration: .github/workflows/, .gitlab-ci.yml, Jenkinsfile, .circleci/, or equivalent.
- Build scripts and package manager configurations.
- Environment files: .env.example, .env.local, config/ directories.
- Any monitoring or logging configuration files.

---

## Expected Outputs

1. **Build Pipeline** — How the project is built, including key commands and artifacts produced.
2. **CI/CD Assessment** — Pipeline maturity, stages, test execution, and deployment automation.
3. **Container and Orchestration** — Container setup, orchestration strategy, and environment management.
4. **Environment Management** — How configurations vary across environments and how secrets are handled.
5. **Database Operations** — Migration strategy, schema management, and backup approach.
6. **Observability** — Logging, monitoring, and alerting coverage.
7. **Security Posture** — Authentication, authorization, secrets management, and vulnerability scanning.
8. **Deployment Architecture** — How the system is deployed and where it runs.
9. **Infrastructure Gaps** — Missing or incomplete operational capabilities.

---

## Token Optimization Strategy

- Focus on what exists and what is missing, not on explaining common tools (e.g., do not explain what Docker is).
- Use a maturity scale (not started, basic, intermediate, advanced) for each infrastructure dimension.
- List configuration files by path rather than quoting their contents.
- When gaps are identified, state the gap and its impact in one line rather than a long explanation.
- If analysis level is `quick`, limit output to sections 1, 2, 8, and 9.

---

## Recommended Template

`templates/architecture-summary.md`

---

## Recommended Combinations

| Audience | Purpose | Why It Works |
|----------|---------|--------------|
| Developer | Improve | Developer identifies infrastructure gaps to address. |
| Developer | Understand | New team member learns the deployment workflow. |
| Executive | Review | Non-technical assessment of operational readiness. |
| AI Agent | Understand | AI agent understands the build and deploy process before making changes. |