# Reference: Domain 9 — AI Product Operations (First-Class OE Domain)

## Status: FIRST-CLASS OE DOMAIN (Added May 2026)
AI Product Operations covers the full operational lifecycle of AI **as a product feature** —
metrics, cost, model evaluation, token optimization, performance, and quality governance.

This is DISTINCT from Domain 8 (AIOps = AI for IT Operations).

| Domain 8: AIOps | Domain 9: AI Product Ops |
|-----------------|--------------------------|
| AI used TO RUN operations | AI used IN the product |
| Alert correlation, auto-remediation, RCA | LLM cost, token efficiency, model evals |
| Infrastructure intelligence | Product feature intelligence |
| MTTD, MTTR, noise reduction | Cost/token, hallucination rate, eval scores |

**Core Principle**: Every AI feature is a product operations discipline — if you cannot measure
the cost, quality, and performance of your AI features, you cannot run an AI product.

**Search-Verified 2026 Tools**: Braintrust, Langfuse, LangWatch, Helicone, Datadog LLM Obs,
W&B Weave, DeepEval, Arize AI, LangSmith, Portkey, Redis LangCache

---

## Domain 9: AI Product Operations — Full Function Table

### Section 1: AI Metrics & Measurement

| Function | Action | Key Deliverable | Primary Metrics |
|----------|--------|-----------------|-----------------|
| AI Feature KPI Definition | Define measurable KPIs for every AI-powered feature | AI KPI registry per feature | #AI-features-with-defined-KPIs, KPI coverage % (target 100%) |
| AI Quality Metrics | Track hallucination rate, accuracy, relevance, faithfulness per model/feature | Quality scorecard per feature | Hallucination rate % (target <5%), Answer relevance score, Faithfulness score, Context precision |
| AI Latency Metrics | Track P50/P95/P99 response times for all LLM calls | Latency SLO per model | P50 latency, P95 latency, P99 latency, Time-to-first-token (TTFT) |
| AI Adoption & Engagement | Measure how users actually use AI features | AI feature adoption funnel | AI feature DAU/MAU, Acceptance rate (AI suggestions accepted), AI session depth |
| AI Business Impact | Quantify business value delivered by AI features | AI ROI report per feature | Time saved/user, Task completion rate lift, Revenue attributed to AI features, NPS delta (AI vs non-AI users) |
| AI Error & Failure Metrics | Track AI-specific failures beyond traditional errors | AI failure taxonomy | AI error rate %, Refusal rate %, Timeout rate %, Retry rate %, Degraded response rate % |

**Recommended Procedure**: (1) Define KPIs for every AI feature at design time — not post-launch. (2) Instrument all LLM calls with metadata tags (feature, user, model). (3) Build AI metrics dashboard separate from infra metrics. (4) Weekly AI quality review. (5) Monthly AI ROI report to leadership.

**Recommended Tools**:
- `[Best-in-Class]` **Braintrust** — production LLM cost tracking, quality evals, per-trace attribution (2026 top rated)
- `[Best-in-Class]` **Langfuse** — open-source LLM observability, tracing, evals, cost tracking
- `[Open Source]` **LangWatch** — full LLM observability, evaluation, experimentation (open source option)
- `[Enterprise]` **Arize AI** — ML/LLM observability, model performance, drift detection at scale

---

### Section 2: AI Cost Management & Token Optimization

| Function | Action | Key Deliverable | Primary Metrics |
|----------|--------|-----------------|-----------------|
| Token Usage Tracking | Track input + output token consumption per feature, per user, per model | Token usage dashboard | Avg tokens/request, Input vs output token ratio, Token cost/feature, Token cost/customer |
| Cost Attribution | Map AI spend to specific features, user segments, and business value | AI cost attribution model | AI cost/feature, AI cost/customer, AI cost as % of COGS, AI cost/revenue unit |
| Token Optimization | Reduce token waste through prompt compression, caching, model routing | Token optimization report | Token reduction % (target 20-40% vs baseline), Cost savings $/qtr, Avg tokens/request trend |
| Semantic Caching | Implement semantic caching to avoid redundant LLM calls | Cache hit rate report | Cache hit rate % (target 40-70%), Cost avoided by caching $/qtr, Latency improvement from cache |
| Model Routing & Downtiering | Route simple tasks to cheaper models, complex tasks to powerful models | Model routing config | % requests routed to lower-cost models, Quality maintained %, Cost per request vs quality score |
| AI FinOps Governance | Monthly review and optimization of AI infrastructure spend | AI spend forecast, savings plan | AI spend vs budget %, MoM AI cost growth %, AI cost forecast accuracy, Break-even analysis |
| Cost Alerting | Automated alerts when AI costs exceed thresholds | Cost alert runbook | Alert coverage % (target 100% of AI features), Time to detect cost anomaly, $ prevented by alerts |

**Recommended Procedure — Token Optimization**: (1) Baseline current token count per feature. (2) Implement prompt compression (target 30% reduction). (3) Add semantic caching layer (Redis LangCache, target 40-70% hit rate). (4) Implement model router for task complexity classification. (5) Set cost budget alerts at 50%, 80%, 100% per feature. (6) Monthly cost optimization review. (7) Track cost/quality tradeoff — never optimize cost at the expense of >5% quality drop.

**Recommended Tools**:
- `[Best-in-Class]` **Braintrust** — per-trace/per-tool cost attribution, prompt experimentation vs real traces
- `[Best-in-Class]` **Helicone** — LLM cost tracking, rate limiting, caching, simple setup
- `[Open Source]` **Langfuse** — self-hostable, cost tracking, prompt versioning
- `[Open Source]` **Redis LangCache** — semantic caching, up to 70% LLM cost reduction (2026 verified)
- `[Budget]` **LangWatch** — cost monitoring + quality, open source first
- `[Enterprise]` **Portkey AI** — AI gateway with routing, caching, load balancing, cost controls
- `[Token Optimization]` **LLMLingua / LLMLingua-2 (Microsoft)** — prompt compression library, 30%+ token reduction

**Key Token Optimization Techniques** (embed in Procedure column):
1. **Prompt compression** — remove redundant context, use LLMLingua for 30% reduction
2. **Semantic caching** — cache similar queries; Redis LangCache cuts costs 70% for high-repeat deployments
3. **Model routing** — route simple tasks (classification, summarization) to smaller models
4. **Context window management** — truncate or summarize conversation history aggressively
5. **Output length control** — set max_tokens for each endpoint, monitor output token bloat
6. **Batching** — batch similar requests to reduce per-call overhead
7. **RAG optimization** — retrieve fewer, more relevant chunks; reduce context padding

---

### Section 3: Model Evaluation & Quality Assurance

| Function | Action | Key Deliverable | Primary Metrics |
|----------|--------|-----------------|-----------------|
| Automated Evals Framework | Run automated evaluations on every model version and prompt change | Eval pipeline in CI/CD | Eval coverage % (target 100% of AI features), Eval pass rate, Regression detection time |
| Ground Truth Dataset | Maintain curated benchmark datasets for each AI feature | Ground truth dataset per feature | Dataset size, Dataset freshness (updated quarterly), Human agreement rate % |
| Hallucination Detection | Systematic detection and measurement of hallucination across all AI features | Hallucination report | Hallucination rate % (target <5%), Detection coverage %, FP/FN rate for hallucination detector |
| Prompt Regression Testing | Detect quality degradation when prompts or models change | Prompt regression test suite | # prompt regressions detected, Time to detect regression, MTTR for prompt issues |
| A/B Testing for Models & Prompts | Systematic comparison of model versions, prompt variants | A/B test results, Winner selection criteria | Win rate %, Statistical significance threshold, Quality delta vs cost delta |
| Human-in-the-Loop Evaluation | Expert review for high-stakes AI outputs | Human eval queue | # human reviews/week, Human eval agreement with automated eval %, Escalation rate % |
| Model Versioning & Rollback | Track model versions in production, enable fast rollback | Model version registry | # model versions in production, Rollback time (target <30 min), Canary evaluation pass rate |
| Red-Teaming & Adversarial Testing | Systematic attempts to break AI quality and safety | Red-team report | # adversarial tests run/qtr, # vulnerabilities found, % remediated within SLA |

**Recommended Procedure — Model Evaluation**: (1) Build eval suite before shipping any AI feature. (2) Define pass/fail criteria per eval dimension (accuracy, relevance, safety, cost). (3) Run evals in CI pipeline on every prompt or model change. (4) Human review for lowest-scoring outputs. (5) A/B test any significant prompt or model change. (6) Quarterly ground truth refresh. (7) Red-team every major AI release.

**Recommended Tools**:
- `[Best-in-Class]` **Braintrust** — eval framework, ground truth management, CI integration, LLM judge
- `[Best-in-Class]` **W&B Weave** — evaluation + model registry + audit trail for compliance
- `[Open Source]` **DeepEval** — open-source LLM evaluation framework, 50+ eval metrics
- `[Open Source]` **Ragas** — RAG evaluation framework, context precision, faithfulness
- `[Budget]` **Langfuse** — self-hostable evals, prompt management, A/B testing
- `[Enterprise]` **Arize AI** — model evaluation, drift detection, A/B testing at scale
- `[Enterprise]` **Klu.ai** — centralized eval + prompt management + compliance audit

---

### Section 4: AI Performance Engineering

| Function | Action | Key Deliverable | Primary Metrics |
|----------|--------|-----------------|-----------------|
| Latency SLO Definition | Define latency SLOs for every AI endpoint | AI latency SLO registry | SLO compliance % (target 99%), TTFT (time-to-first-token), End-to-end AI response time |
| Streaming Optimization | Implement token streaming for perceived performance improvement | Streaming coverage | % of AI endpoints using streaming, User-perceived latency improvement |
| Inference Infrastructure | Optimize inference stack for cost-performance ratio | Infra optimization report | GPU/CPU utilization %, Inference cost per 1M tokens, Throughput (requests/sec) |
| Context Window Optimization | Minimize context size while preserving quality | Context efficiency score | Avg context size (tokens), Context utilization % (signal vs noise), Quality at reduced context |
| Concurrent Request Management | Handle high concurrency without latency degradation | Concurrency test results | Max concurrent requests at SLO, Latency at P99 under load, Queue depth at peak |
| Model Performance Benchmarking | Continuous benchmarking of model quality vs cost vs latency | Performance benchmark report | Quality score vs cost/token, Latency vs quality tradeoff curve, Cost efficiency index |

**Recommended Tools**:
- `[Best-in-Class]` **Datadog LLM Observability** — TTFT, latency percentiles, cost per request
- `[Best-in-Class]` **Langfuse** — trace-level latency analysis, streaming support
- `[Open Source]` **LiteLLM** — unified LLM gateway, model routing, load balancing
- `[Open Source]` **vLLM** — high-throughput LLM inference for self-hosted models
- `[Enterprise]` **Portkey AI** — AI gateway with load balancing, fallbacks, performance routing

---

### Section 5: AI Governance & Compliance

| Function | Action | Key Deliverable | Primary Metrics |
|----------|--------|-----------------|-----------------|
| Responsible AI Policy | Document and enforce responsible AI usage | Responsible AI policy, Compliance checklist | # policy exceptions/qtr, Compliance audit pass rate |
| Data Privacy in AI | Ensure PII is not exposed in AI pipelines | PII detection report | % AI requests PII-scanned, # PII leaks detected, MTTD for PII exposure |
| AI Audit Trail | Maintain complete log of AI decisions for compliance | AI audit log | Audit log coverage % (target 100%), Log retention compliance, # audit requests fulfilled |
| Regulatory Compliance (EU AI Act, etc.) | Track and comply with AI regulations | Compliance dashboard | # regulatory requirements mapped, % compliant, # open compliance gaps |
| Model Bias Assessment | Regular testing for demographic and domain bias | Bias report per model | Bias detection score, # bias issues found, % remediated |
| AI Security | Defend against prompt injection, jailbreaks, data leakage | Security test results | # prompt injection attempts detected, # blocked, Data leakage incidents/qtr |

**Recommended Tools**:
- `[Best-in-Class]` **Lakera Guard** — prompt injection defense, AI security gateway
- `[Best-in-Class]` **W&B Weave** — audit trail, compliance documentation, model provenance
- `[Open Source]` **Presidio (Microsoft)** — PII detection and anonymization for AI pipelines
- `[Enterprise]` **Klu.ai** — enterprise AI compliance, audit log, governance

---

## AI Product Ops Maturity Model

| Score | Level | Description | Target Phase |
|-------|-------|-------------|--------------|
| 1 | Initial | No AI metrics, costs unknown, no evals | Pre-Product |
| 2 | Developing | Basic token tracking, manual evals only | MVP |
| 3 | Defined | Automated evals, cost attribution, latency SLOs | Growth |
| 4 | Managed | Token optimization active, A/B testing, model routing | Scale |
| 5 | Optimizing | Full FinOps for AI, continuous evals in CI, red-teaming, compliance automation | Enterprise |

---

## 12 Non-Negotiable AI Product Ops KPIs

| # | KPI | Target | Critical Threshold |
|---|-----|--------|--------------------|
| 1 | AI Feature Eval Coverage | 100% | <60% = shipping blind |
| 2 | Hallucination Rate % | <5% | >15% = unusable |
| 3 | AI Cost/Feature ($/month) | Defined + budgeted | Unbudgeted = no control |
| 4 | Token Cost Reduction % (vs baseline) | 20-40% | 0% = no optimization |
| 5 | Semantic Cache Hit Rate | 40-70% | <20% = caching not working |
| 6 | AI Latency P95 (per endpoint) | Per-endpoint SLO | SLO breach >1%/week |
| 7 | Eval Pass Rate % (CI pipeline) | >95% | <80% = quality crisis |
| 8 | Model Routing Efficiency | >50% requests to lower-cost models | 0% = no routing |
| 9 | AI Feature Adoption Rate | Per-feature target | <10% DAU = feature failing |
| 10 | AI Error Rate % | <2% | >5% = production issue |
| 11 | Prompt Regression Detection Time | <24 hours | >72 hours = too slow |
| 12 | AI Cost as % of COGS | <15% (growth), <10% (scale) | >25% = unsustainable |

---

## Output Validation Checklist
- [ ] Domain 9 present as STANDALONE section in OE Scorecard (not merged with Domain 8)
- [ ] All 5 sections present with functions, KPIs, Procedure, Tools
- [ ] 12 KPIs tracked in KPI sub-table
- [ ] Token optimization techniques embedded in Procedure column
- [ ] Tool recommendations reflect 2026 search-verified rankings
- [ ] Maturity score (1-5) linked to OE summary formula
- [ ] Distinct color: Orange `#FF8C00` for Domain 9 section header
