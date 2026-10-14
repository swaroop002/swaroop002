# Hi, I'm Swaroop Rangle 👋

**DevOps Engineer at [Faclon Labs](https://faclon.com), Mumbai** — since late 2024
the one DevOps / AI-infrastructure engineer behind the data-science side of an
industrial IoT platform: 40–50 services on Kubernetes across AWS, Azure and
on-prem, the CI/CD that ships them, the RabbitMQ/MQTT messaging layer they talk
over, a multi-cloud compute provisioner, and the observability stack that tells
us when something is wrong before a customer does. Lately also the
infrastructure for ML and LLM workloads.

- 🔭 Working on: [pulse](https://github.com/swaroop002/pulse), a telemetry platform with its own storage engine, and [berth](https://github.com/swaroop002/berth), the control plane that provisions environments (and pulse tenants) for teams
- 🛠️ Also: an [SRE assistant](https://github.com/swaroop002/infra-agent) that answers on-call questions from live telemetry, with evidence
- 🌱 Learned Go by [building the tools](https://github.com/swaroop002/go-for-devops) I kept wishing I had
- ☁️ AWS Certified Solutions Architect – Associate
- 📫 [swar.rang212@gmail.com](mailto:swar.rang212@gmail.com) · [LinkedIn](https://www.linkedin.com/in/swaroop-rangle/) · [Portfolio](https://swaroop-portfolio-ten.vercel.app/)

## What I've done in production

- **CI/CD from zero**: Jenkins pipelines for 20–30 repositories with tests, coverage, SonarQube/Snyk gates and native ARM64 + AMD64 images; release time **25–30 minutes → 5–10**. CI commits the image tag into the Helm repo, so every release is a Git commit.
- **Cut AWS compute cost by ~40% (~$3k/month)** by moving EC2 workloads from x86 to Graviton (ARM).
- **Event-driven autoscaling** with KEDA on queue depth: **6 → 48 pods** across 8 nodes, polled every 15 s, absorbing 10–40k-message bursts; the scaling signal comes from a queue-length API I wrote.
- **Zero-downtime migration to a 3-node RabbitMQ cluster**; designed the RabbitMQ and MQTT client classes of the expression engine that serves **150–200 requests/min** at peak, and removed auto-ack so a dying worker never loses a request.
- **Proposed and prototyped the Polars rewrite** of that engine: **~40% faster responses**, measured from request timings in Loki.
- **Compute Module**: a multi-cloud (AWS + Azure) VM provisioner — **25 large VMs** in production, each with 12 self-service tools installed by Ansible, DNS, TLS and auth automated; also installed on-prem for customers.
- **An internal deployment platform** and a VS Code extension in front of it: 7 app runtimes under PM2 and nginx, live logs, TTL clean-up — **80–120 users**, cloud and on-prem.
- **One observability stack for 40+ VMs and the clusters** — Prometheus, Grafana, Loki, Grafana Alloy — plus a logging library and the Loki ingestion pipeline behind it; on-call, incident response and postmortems.
- **5 Helm charts** own the data-science estate (EKS, AKS, on-prem variants); **20+ Python microservices** containerised; **20+ operational workflows** automated in Python; self-service environments for **60–70 engineers**.
- **ML/LLM infrastructure**: MLflow, Airflow/Dagster pipelines, GPU model serving with Triton, LangGraph + RAG (Qdrant, Langfuse), internal MCP servers, self-hosted LLMs with Ollama.
- **70% faster queries** after migrating to Aurora PostgreSQL (earlier internship).

## Toolbox

| | |
|---|---|
| **Cloud** | AWS (EKS, EC2/Graviton, S3, IAM, VPC, Route 53, ALB/ELB, CloudFront, Aurora, CloudWatch), Azure (AKS, VMs, VMSS, Entra ID, Blob), GCP (fundamentals) |
| **Containers & orchestration** | Kubernetes, Helm, ArgoCD, KEDA, Karpenter, Docker (Buildx multi-arch), PM2 |
| **Infrastructure as code** | Terraform, Ansible |
| **CI/CD & DevSecOps** | Jenkins, GitHub Actions, GitLab CI, SonarQube, Snyk, pytest |
| **Observability** | Prometheus, Grafana, Loki, Grafana Alloy / Promtail |
| **Languages** | Python, Bash, SQL, Go, TypeScript |
| **Data, ML & LLM infra** | Polars, MLflow, Airflow, Dagster, Celery, Triton, LangGraph, Qdrant, Langfuse, MCP, Ollama |
| **Networking & Linux** | Nginx, HAProxy, Cloudflare, Pritunl/OpenVPN, DNS/TLS, Linux |
| **Messaging & databases** | RabbitMQ (clustered, quorum queues), MQTT, PostgreSQL, MongoDB, Redis, MySQL |

## Featured projects

| Project | What it is |
|---|---|
| [**pulse**](https://github.com/swaroop002/pulse) | Multi-tenant telemetry platform, written from the storage engine up: group-committed write-ahead log, sharded in-memory head, immutable Gorilla-compressed blocks with compaction and cold tiering, admission control (429, not timeouts), and a Prometheus-compatible query API so Grafana reads it with no plugin. **153k samples/s with fsync on every write**; crash test recovers every acknowledged sample. ADRs for each decision, fuzzed formats, `go test -race` throughout. |
| [**berth**](https://github.com/swaroop002/berth) | Environment control plane: declare an environment (size, disk, hostname, authenticated route, telemetry tenant, TTL) and a reconciler makes it exist, repairs drift, tears it down in order and expires it. Team-scoped tokens, an in-process route gateway that authenticates and proxies, cost per environment and team, Prometheus metrics. Kubernetes-shaped objects, so the same type can become a CRD. Generalises the provisioning platform I run at work. |
| [**infra-agent**](https://github.com/swaroop002/infra-agent) | Read-only SRE assistant: ask in plain English (web UI or Microsoft Teams), get answers from Prometheus, Loki, Grafana alerting, OnCall and AWS/Azure/GCP inventories, with the exact queries shown. LangGraph + FastAPI, demo mode, 87 offline tests. |
| [**go-for-devops**](https://github.com/swaroop002/go-for-devops) | How I learned Go: 20 lessons, 14 advanced phases and 9 working projects — log analyser, service monitor, node exporter, durable job queue, reverse proxy, Kubernetes operator, container runtime, Terraform-like deploy tool, Raft key-value store. All build and pass tests. |
| [**mnist-mlflow-serving**](https://github.com/swaroop002/mnist-mlflow-serving) | A small end-to-end MLOps loop: CNN trained and autologged to MLflow, served from the model registry behind a Flask API, tested by drawing digits in the browser. |
| [Real-time-Order-Processing-on-AWS](https://github.com/swaroop002/Real-time-Order-Processing-on-AWS) | Streaming order pipeline on Kinesis, Lambda, DynamoDB and S3. |
| [Visualizing-Real-time-Server-Logs](https://github.com/swaroop002/Visualizing-Real-time-Server-Logs) | Live server-log dashboards with Kinesis, Lambda and OpenSearch. |
| [Product-Recommender-On-EMR](https://github.com/swaroop002/Product-Recommender-On-EMR) | Recommendation job on Amazon EMR fed by Kinesis Firehose and S3. |

## Work at Faclon Labs — architecture write-ups

The code is my employer's, so these repos hold the design, the system diagram and the outcomes of each project, not the implementation.

| Write-up | In one line |
|---|---|
| [event-driven-infra-provisioning-platform](https://github.com/swaroop002/event-driven-infra-provisioning-platform) | Compute Module: multi-cloud (AWS + Azure) per-tenant VMs with 12 Ansible-installed tools, DNS/TLS/auth automated — 25 large VMs in production, on-prem too |
| [messaging-layer-rabbitmq-cluster](https://github.com/swaroop002/messaging-layer-rabbitmq-cluster) | The expression engine's RabbitMQ/MQTT connectors, a zero-downtime move to a 3-node cluster, and the Polars rewrite that made it ~40% faster |
| [event-driven-k8s-autoscaling](https://github.com/swaroop002/event-driven-k8s-autoscaling) | KEDA on queue depth via a custom metrics API: 6 → 48 pods, 15 s polling, asymmetric scale policies, EKS and AKS |
| [secure-multiarch-cicd](https://github.com/swaroop002/secure-multiarch-cicd) | CI/CD from zero for 20–30 repos: tests, SonarQube/Snyk gates, native ARM64 + AMD64 images, GitOps tag bumps; 25–30 → 5–10 min |
| [gitops-deployment-platform](https://github.com/swaroop002/gitops-deployment-platform) | 5 Helm charts + ArgoCD across EKS, AKS and on-prem: auditable releases, one-command rollbacks |
| [internal-deployment-platform](https://github.com/swaroop002/internal-deployment-platform) | Deployment platform + VS Code extension: 7 runtimes under PM2/nginx, live logs, TTLs — 80–120 users |
| [dev-datascience-environment-automation](https://github.com/swaroop002/dev-datascience-environment-automation) | Ansible-provisioned MLflow/Airflow/JupyterLab/VS Code Server environments in minutes |
| [centralized-monitoring-logging](https://github.com/swaroop002/centralized-monitoring-logging) | Prometheus, Grafana and Loki across 40+ VMs and the clusters, plus the logging library and Loki ingestion pipeline |
| [aws-graviton-migration](https://github.com/swaroop002/aws-graviton-migration) | x86 → Graviton with multi-arch images; ~40% / ~$3K per month saved |
| [secure-service-exposure-network-access](https://github.com/swaroop002/secure-service-exposure-network-access) | Nginx/HAProxy front door on 443, Pritunl/OpenVPN, IAM and network controls |

I also run a private, local-only job-search assistant that scores postings and
tailors resumes against a fact-checked profile — not published, because it holds
my own data.

## Background

- **M.Sc. Computer Science**, Mithibai College, University of Mumbai (2022–2024) — CGPA 8.35
- **B.Sc. Computer Science**, Bhavans College, University of Mumbai (2019–2022) — CGPA 9.62
- Before Faclon: DevOps Engineer intern at Viamagus (2024), Data Engineer intern at Mactores (2023–24)
- **AWS Certified Solutions Architect – Associate** · #30DaysOnGoogleCloud

<p>
  <img src="https://github-readme-stats.vercel.app/api?username=swaroop002&show_icons=true&theme=default&hide_border=true&rank_icon=github" alt="GitHub stats" height="160">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=swaroop002&layout=compact&hide_border=true&langs_count=8" alt="Top languages" height="160">
</p>
