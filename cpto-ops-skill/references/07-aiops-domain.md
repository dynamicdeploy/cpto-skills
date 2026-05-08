# Reference: Domain 8 — AIOps & Intelligent Operations (First-Class OE Metric)

## Status: FIRST-CLASS OE DOMAIN
AIOps is **Domain 8** in the Operational Excellence framework — numbered, scored, measured, and
tracked identically to Domains 1–7. It is NOT a sub-section of Infrastructure. It is NOT optional.
It is a standalone domain with its own functions, deliverables, KPIs, score (1–5), and quarterly trend row.

**Core Principle**: AI-driven operations is the 2026 standard — if you are not using AI to detect,
correlate, and remediate operational issues, you are operating below the industry baseline.

**Search-Verified Tools** (G2 Spring 2026 Report + Gartner Peer Insights 2026):
Top AIOps platforms by category: Dynatrace Davis AI, BigPanda, IBM Instana, ServiceNow ITOM,
New Relic AI, Datadog Watchdog, Atera IT Autopilot, PagerDuty AIOps, OpenObserve, Sherlocks.ai

---

## Why AIOps Is Domain 8 (Not a Sub-topic of Infra)

Traditional SRE and infrastructure monitoring is reactive. AIOps transforms operations to:
- **Predictive**: Detect anomalies before they become incidents
- **Correlative**: Link alerts across distributed systems to single root causes (alert noise reduction target: 80%+)
- **Autonomous**: Auto-remediate known failure patterns without human intervention
- **Intelligent**: Continuously learn from operational history via ML

These capabilities are distinct from standard observability (Domain 4) and require dedicated
measurement, tooling, and maturity scoring.

---

## Domain 8: AIOps & Intelligent Operations — Full Function Table

| Function | Action | Key Deliverable | Primary Metrics |
|----------|--------|-----------------|-----------------|
| Intelligent Alert Correlation | Use ML to correlate and deduplicate alerts across all systems | Alert correlation ruleset, Noise reduction report | Alert noise reduction % (target 80%+), MTTA, #correlated-events/week |
| Predictive Anomaly Detection | Apply ML to detect anomalies before user impact | Anomaly detection model, Prediction accuracy report | #anomalies-detected-before-user-impact, False positive rate %, MTTD |
| Automated Root Cause Analysis | Use AI to identify root cause without manual triage | AI-generated RCA reports, Runbook auto-trigger | MTTR, RCA accuracy %, #incidents-with-auto-RCA |
| Auto-Remediation & Self-Healing | Automate resolution of known failure patterns | Auto-remediation runbooks, Self-healing coverage | %incidents-auto-remediated (target 40%+), #runbooks-automated |
| Capacity & Performance Forecasting | Predict infrastructure needs using ML | Capacity forecast model, Cost avoidance report | Forecast accuracy %, #capacity-incidents-prevented, Cost avoidance $/qtr |
| AIOps Observability & LLM Monitoring | Monitor AI/ML systems alongside traditional infra | AI observability dashboard, LLM performance report | LLM latency P50/P95/P99, Token cost/request, Hallucination rate %, Model drift score |
| AIOps FinOps & Cost Intelligence | Apply AI to optimize cloud and operational costs | Cost intelligence report, Savings recommendations | Cloud cost/customer, AI-driven savings $/qtr, Cost anomaly detection % |
| AIOps Incident Intelligence | Use AI to improve incident comms and post-incident learning | AI incident summaries, PIR automation | #PIRs-on-time, Time-to-draft-summary, Repeat incident rate % |
| AIOps Maturity Governance | Measure and improve AIOps program maturity | AIOps maturity scorecard, Quarterly improvement plan | AIOps maturity score (1-5), %tasks-AI-assisted, #manual-interventions/week |

---

## Recommended Procedures & Tools Per Function

### 1. Intelligent Alert Correlation
**Procedure**: (1) Baseline current alert volume. (2) Implement ML correlation engine. (3) Set noise reduction SLO of 80%+. (4) Weekly review of correlated vs raw alert ratio. (5) Tune false-positive rate monthly.
**Tools**:
- `[Best-in-Class]` **Dynatrace Davis AI** — causal AI, auto-correlation, topology-aware (G2 Leader 2026)
- `[Best-in-Class]` **BigPanda** — event correlation for large enterprises, multi-source ingestion
- `[Open Source]` **OpenObserve** — petabyte-scale full-fidelity telemetry, no data sampling
- `[Enterprise]` **IBM Instana** — real-time observability with AI-driven root cause (G2 Top Rated 2026)

### 2. Predictive Anomaly Detection
**Procedure**: (1) Instrument all services with full telemetry. (2) Train baseline models on 90 days of data. (3) Deploy anomaly detection per service. (4) Set alert thresholds from model output. (5) Review prediction accuracy monthly.
**Tools**:
- `[Best-in-Class]` **Datadog Watchdog** — AI anomaly detection built-in, zero config (G2 Leader 2026)
- `[Best-in-Class]` **New Relic AI** — NRQL anomaly baselines, applied intelligence
- `[Open Source]` **Grafana ML** — anomaly detection plugin for Grafana Cloud
- `[Enterprise]` **Dynatrace Davis** — unsupervised anomaly detection at petabyte scale

### 3. Automated Root Cause Analysis
**Procedure**: (1) Map full service dependency graph. (2) Configure AI RCA tool with topology. (3) Run AI-RCA for every Sev1/Sev2 incident. (4) Compare AI-RCA accuracy vs human RCA weekly. (5) Expand coverage quarterly.
**Tools**:
- `[Best-in-Class]` **Dynatrace Davis AI** — automated topology-aware RCA, industry gold standard
- `[Best-in-Class]` **Sherlocks.ai** — AI SRE, 24/7 RCA automation, MTTR reduction by 10x (2026)
- `[Open Source]` **OpenTelemetry + Jaeger** — distributed tracing for manual + semi-automated RCA
- `[Enterprise]` **ServiceNow ITOM** — IT Operations Management with AI-assisted RCA + ticketing

### 4. Auto-Remediation & Self-Healing
**Procedure**: (1) Identify top 10 recurring incident patterns. (2) Build automated runbooks for each. (3) Automate runbook execution for matching alerts. (4) Review and expand coverage quarterly. (5) Track labor cost saved.
**Tools**:
- `[Best-in-Class]` **PagerDuty AIOps** — auto-remediation workflows, event intelligence
- `[Best-in-Class]` **Atera IT Autopilot** — AI-powered 24/7 autonomous IT resolution (G2 Top Pick 2026)
- `[Open Source]` **Ansible + AWX** — runbook automation, open source, highly extensible
- `[Enterprise]` **ServiceNow ITOM Predictive AIOps** — enterprise auto-remediation at scale

### 5. Capacity & Performance Forecasting
**Procedure**: (1) Export 6 months of utilization data. (2) Train forecasting model (CPU, memory, storage, traffic). (3) Set auto-scaling triggers from model output. (4) Review forecast vs actual monthly. (5) Link to FinOps savings.
**Tools**:
- `[Best-in-Class]` **Datadog Forecast** — built-in capacity forecasting, integrates with auto-scaling
- `[Best-in-Class]` **AWS Compute Optimizer / GCP Recommender** — cloud-native right-sizing AI
- `[Open Source]` **Prophet (Meta)** — time-series forecasting library, highly accurate
- `[Enterprise]` **Turbonomic (IBM)** — full-stack resource optimization, AI-driven actions

### 6. AIOps Observability & LLM Monitoring
**Procedure**: (1) Instrument all LLM calls with OpenTelemetry. (2) Set latency and cost SLOs per model. (3) Track hallucination rate via evals pipeline. (4) Alert on model drift. (5) Review AI + infra health in unified dashboard weekly.
**Tools**:
- `[Best-in-Class]` **Datadog LLM Observability** — production LLM monitoring, token tracking, cost
- `[Best-in-Class]` **Langfuse** — open-source LLM observability, tracing, evals (2026 top rated)
- `[Open Source]` **OpenObserve + OpenLIT** — OpenTelemetry-native LLM tracing, full fidelity
- `[Enterprise]` **Arize AI** — ML observability, model monitoring, drift detection, explainability

### 7. AIOps FinOps & Cost Intelligence
**Procedure**: (1) Tag all cloud resources by feature and customer. (2) Enable AI cost anomaly alerts. (3) Apply AI optimization recommendations monthly. (4) Track cost/unit-of-value trend. (5) Quarterly FinOps review with engineering leadership.
**Tools**:
- `[Best-in-Class]` **CloudZero** — AI-powered cloud cost intelligence, per-feature cost allocation
- `[Best-in-Class]` **Harness CCM** — cloud cost management with AI recommendations + savings automation
- `[Open Source]` **OpenCost (CNCF)** — Kubernetes cost monitoring, open standard
- `[Enterprise]` **Apptio Cloudability** — enterprise FinOps with AI insights + CFO reporting

### 8. AIOps Incident Intelligence
**Procedure**: (1) Integrate AI summarization into incident workflow. (2) Auto-draft timeline from alerts + logs. (3) Generate PIR template from incident data. (4) Track repeat incidents by root cause cluster. (5) Feed learnings back into runbook automation.
**Tools**:
- `[Best-in-Class]` **PagerDuty AI** — incident summarization, auto-postmortems, status pages
- `[Best-in-Class]` **Incident.io** — incident management with AI timeline, Slack-native (2026 top rated)
- `[Open Source]` **Rootly** — open-source incident management with postmortem templates
- `[Enterprise]` **ServiceNow Incident Management** — full ITSM with AI-assist + CMDB integration

### 9. AIOps Maturity Governance
**Procedure**: (1) Run AIOps maturity assessment quarterly using this scorecard. (2) Set maturity target by phase (Growth: 3.0, Scale: 4.0, Enterprise: 5.0). (3) Assign named AIOps owner. (4) Track 10 KPIs quarterly. (5) Publish scorecard to leadership in QBR.
**Tools**:
- `[Framework]` **This CPTO-Ops AIOps Domain Scorecard** — primary measurement tool
- `[Framework]` **DORA + SPACE metrics** — overlaid with AIOps KPIs for engineering correlation
- `[Open Source]` **Grafana Dashboards** — custom AIOps maturity KPI dashboard
- `[Enterprise]` **Dynatrace Business Analytics** — exec-level AIOps reporting and business impact

---

## The 10 Non-Negotiable AIOps KPIs

| # | KPI | Healthy Target | Critical Threshold | Owner |
|---|-----|----------------|--------------------|-------|
| 1 | Alert Noise Reduction % | 80%+ | <50% = not working | SRE Lead |
| 2 | MTTD (Mean Time to Detect) | <5 min | >30 min = critical gap | SRE Lead |
| 3 | MTTR (Mean Time to Resolve) | <30 min (Sev1) | >2 hrs = critical | Engineering Lead |
| 4 | MTTA (Mean Time to Acknowledge) | <5 min | >15 min = process gap | On-call Lead |
| 5 | Auto-Remediation Rate % | 40%+ (year 2) | 0% = no automation | Platform Eng |
| 6 | False Positive Alert Rate % | <10% | >30% = trust broken | SRE Lead |
| 7 | AI-RCA Accuracy % | >85% | <60% = unusable | SRE Lead |
| 8 | Repeat Incident Rate % | <10% | >30% = learning failure | Eng Manager |
| 9 | AIOps Cost Savings $/qtr | Positive ROI | Negative ROI = review tools | FinOps / CPTO |
| 10 | AI Observability Coverage % | 100% | <60% = blind spots | Platform Eng |

---

## AIOps Maturity Model

| Score | Level | Description | Capability | Target Phase |
|-------|-------|-------------|-----------|--------------|
| 1 | Initial | Reactive, manual triage, alert storms | No AI in operations | Pre-Product |
| 2 | Developing | Basic monitoring, some alert rules | Simple thresholds, basic dashboards | MVP |
| 3 | Defined | Consistent observability, AI tools starting | ML anomaly detection, basic correlation | Growth |
| 4 | Managed | AI-driven operations, measured outcomes | Auto-RCA, 80%+ noise reduction, some auto-remediation | Scale |
| 5 | Optimizing | Fully autonomous intelligent operations | Self-healing, predictive, cost-optimized, AI observing AI | Enterprise |

---

## AIOps Tool Stack by Company Phase

### Startup / MVP (Budget < $50K/yr)
- **Datadog** (pay-as-you-grow, Watchdog included) + **Grafana Cloud free tier**
- **PagerDuty** team plan for incident management
- **GitHub Actions** for basic runbook automation
- **OpenObserve** for cost-effective telemetry storage

### Growth ($50K–$500K/yr ops budget)
- **Datadog** full stack + **Datadog LLM Observability**
- **PagerDuty AIOps** for alert correlation
- **CloudZero** or **Harness CCM** for FinOps
- **Incident.io** for incident management
- **Langfuse** for LLM observability

### Enterprise ($500K+/yr ops budget)
- **Dynatrace** (Davis AI) — full platform AIOps, G2 Leader 2026
- **ServiceNow ITOM** — enterprise ITSM + AIOps
- **IBM Instana** — real-time observability, G2 Top Rated 2026
- **Turbonomic** — full-stack resource optimization
- **Arize AI** — ML/LLM observability at scale

---

## Output Validation Checklist
- [ ] Domain 8 present as STANDALONE section in OE Scorecard (not under Domain 4)
- [ ] All 9 functions present with Action, Deliverable, KPI
- [ ] Recommended Procedure column populated (green fill) per function
- [ ] Recommended Tools column populated (purple fill) with 4 tiers per function
- [ ] 10 AIOps KPIs tracked in KPI sub-table
- [ ] AIOps maturity score (1–5) formula-linked to OE summary row
- [ ] Quarterly trend row for Domain 8 in the trend tracker
- [ ] Tool recommendations reflect 2026 G2/Gartner rankings
- [ ] Phase-appropriate tool tier called out based on user's company stage
