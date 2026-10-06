# Hi, I'm Swaroop Rangle 👋

**DevOps Engineer at [Faclon Labs](https://faclon.com), Mumbai** — I run the cloud
infrastructure behind an industrial IoT platform: Kubernetes on AWS and Azure,
Terraform and Ansible, GitOps with ArgoCD, and the observability stack that
tells us when something is wrong before a customer does. Lately also the
infrastructure for ML and LLM workloads.

- 🔭 Working on: [pulse](https://github.com/swaroop002/pulse), a telemetry platform with its own storage engine, and [berth](https://github.com/swaroop002/berth), the control plane that provisions environments (and pulse tenants) for teams
- 🛠️ Also: an [SRE assistant](https://github.com/swaroop002/infra-agent) that answers on-call questions from live telemetry, with evidence
- 🌱 Learned Go by [building the tools](https://github.com/swaroop002/go-for-devops) I kept wishing I had
- ☁️ AWS Certified Solutions Architect – Associate
- 📫 [swar.rang212@gmail.com](mailto:swar.rang212@gmail.com) · [LinkedIn](https://www.linkedin.com/in/swaroop-rangle/) · [Portfolio](https://swaroop-portfolio-ten.vercel.app/)

## What I've done in production

- **Cut AWS compute cost by ~40% (~$3k/month)** by migrating EC2 workloads from x86 to Graviton (ARM).
- **Event-driven autoscaling** with KEDA and the Cluster Autoscaler: 6 → 48 pods across 8 nodes, absorbing 10–40k-message bursts on RabbitMQ.
- **Deployments from 25–30 minutes to 5–10** with CI/CD pipelines (GitHub Actions, Jenkins, GitLab CI) and SonarQube/Snyk gates.
- **One observability stack for 40+ VMs and 2 Kubernetes clusters** — Prometheus, Grafana, Loki, Grafana Alloy — plus on-call, incident response and postmortems.
- **Self-service dev environments** for 60–70 engineers; **20+ operational workflows** automated in Python; **20+ Python microservices** in production.
- **70% faster queries** after migrating to Aurora PostgreSQL.
- **ML/LLM infrastructure**: MLflow, Airflow/Dagster pipelines, GPU model serving with Triton, LangGraph + RAG (Qdrant, Langfuse), internal MCP servers, self-hosted LLMs with Ollama.

## Toolbox

| | |
|---|---|
| **Cloud** | AWS (EKS, EC2/Graviton, S3, IAM, VPC, Route 53, CloudFront, ELB, Aurora, CloudWatch), Azure (AKS, VMSS, Entra ID, Blob), GCP (fundamentals) |
| **Containers & orchestration** | Kubernetes, Helm, ArgoCD, KEDA, Karpenter, Docker |
| **Infrastructure as code** | Terraform, Ansible |
| **CI/CD & DevSecOps** | GitHub Actions, Jenkins, GitLab CI, SonarQube, Snyk |
| **Observability** | Prometheus, Grafana, Loki, Grafana Alloy |
| **Languages** | Python, Bash, SQL, Go |
| **Data, ML & LLM infra** | MLflow, Airflow, Dagster, Triton, LangGraph, Qdrant, Langfuse, MCP, Ollama |
| **Networking & Linux** | Nginx, HAProxy, Cloudflare, Pritunl/OpenVPN, DNS/TLS, Linux |
| **Messaging & databases** | RabbitMQ, MQTT, PostgreSQL, MongoDB, Redis, MySQL |

## Featured projects

| Project | What it is |
|---|---|
| [**pulse**](https://github.com/swaroop002/pulse) | Multi-tenant telemetry platform, written from the storage engine up: group-committed write-ahead log, sharded in-memory head, immutable Gorilla-compressed blocks with compaction and cold tiering, admission control (429, not timeouts), and a Prometheus-compatible query API so Grafana reads it with no plugin. **153k samples/s with fsync on every write**; crash test recovers every acknowledged sample. ADRs for each decision, fuzzed formats, `go test -race` throughout. |
| [**berth**](https://github.com/swaroop002/berth) | Environment control plane: declare an environment (size, disk, hostname, authenticated route, telemetry tenant, TTL) and a reconciler makes it exist, repairs drift, tears it down in order and expires it. Team-scoped tokens, an in-process route gateway that authenticates and proxies, cost per environment and team, Prometheus metrics. Kubernetes-shaped objects, so the same type can become a CRD. Generalises the provisioning platform I ran at work. |
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
| [event-driven-infra-provisioning-platform](https://github.com/swaroop002/event-driven-infra-provisioning-platform) | Self-service AWS environments for 60–70 engineers through a Python API and RabbitMQ-driven workers |
| [event-driven-k8s-autoscaling](https://github.com/swaroop002/event-driven-k8s-autoscaling) | KEDA on RabbitMQ queue depth: 6 → 48 pods, 10K–40K-message bursts |
| [gitops-deployment-platform](https://github.com/swaroop002/gitops-deployment-platform) | Helm + ArgoCD: auditable releases, one-command rollbacks |
| [secure-multiarch-cicd](https://github.com/swaroop002/secure-multiarch-cicd) | Jenkins with SonarQube/Snyk gates and native ARM + x86 builds; 25–30 → 5–10 min |
| [dev-datascience-environment-automation](https://github.com/swaroop002/dev-datascience-environment-automation) | Ansible-provisioned MLflow/Airflow/JupyterLab/VS Code Server environments in minutes |
| [centralized-monitoring-logging](https://github.com/swaroop002/centralized-monitoring-logging) | Prometheus, Grafana and Loki across 40+ VMs and 2 clusters |
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
