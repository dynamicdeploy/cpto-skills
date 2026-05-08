# Reference: Domain 10 — AI-First Development Excellence (First-Class OE Domain)

## Status: FIRST-CLASS OE DOMAIN (Added May 2026)
AI-First Development Excellence measures how well an engineering organization has adopted AI-augmented
development practices — including productivity gains, maturity, tooling, and the quality of AI-assisted
code — as an operational excellence metric.

This is DISTINCT from Domain 8 (AIOps) and Domain 9 (AI Product Ops):

| Domain 8: AIOps | Domain 9: AI Product Ops | Domain 10: AI-First Dev |
|-----------------|--------------------------|-------------------------|
| AI running your infrastructure | AI features in your product | AI in your dev workflow |
| Alert correlation, RCA | LLM cost, model evals | Dev productivity, code quality |
| MTTD, MTTR | Hallucination rate, token cost | AI code share, PR cycle time, ROI |

**Core Principle**: In 2026, 92% of developers use AI tools and 41% of all code is AI-generated.
Engineering organizations that don't measure AI development maturity are flying blind on their
most significant productivity and quality lever.

**Search-Verified 2026 Data**:
- Elite teams: 80%+ weekly active AI tool usage, 60-75% AI-assisted code share, <8hr PR cycle time
- Industry average: 41% AI-generated code, 25-39% reported productivity gain
- Healthy ROI on AI coding tools: 2.5-3.5x average, 4-6x top quartile
- AI code inflation risk: high AI code volume without quality gates → technical debt surge
- The "AI Productivity Paradox": individual speed ↑ but company delivery velocity flat without measurement

**Search-Verified 2026 Tools**: Exceeds AI, Faros AI, Swarmia, Jellyfish, Axify, Pensero.ai,
Larridin, GitHub Copilot Analytics, Cursor, Claude Code, Cody (Sourcegraph), Amazon Q Developer

---

## Domain 10: AI-First Development Excellence — Full Function Table

### Section 1: AI Development Adoption & Maturity

| Function | Action | Key Deliverable | Primary Metrics |
|----------|--------|-----------------|-----------------|
| AI Tool Adoption Tracking | Measure adoption of AI coding tools across the engineering org | AI adoption dashboard | AI tool WAU (Weekly Active Usage) %, AI tool DAU %, % engineers using AI daily (target 80%+) |
| AI Maturity Assessment | Assess the organization's AI-first development maturity (1-5) | AI dev maturity scorecard | Maturity score (1-5), Maturity by team, YoY maturity improvement |
| AI Toolchain Governance | Define the approved AI tool stack, usage policies, security review | AI toolchain policy | # approved tools, % engineers on approved stack, Policy compliance % |
| AI Skill Development | Train engineers on effective AI-augmented development | Training completion, Skill scores | % engineers trained, Training NPS, Skill assessment score, Time-to-proficiency |
| AI Code Culture | Build norms for responsible, high-quality AI-assisted development | AI coding standards document | # AI coding guidelines adopted, PR review AI quality check %, Engineer AI satisfaction score |

**Recommended Procedure**: (1) Survey AI tool usage monthly — report WAU, DAU, tool distribution. (2) Run AI maturity assessment quarterly. (3) Define approved toolchain and security review process. (4) Mandate AI skills training for all engineers (minimum 8 hrs/qtr). (5) Publish AI coding standards — when to use AI, how to review AI code, what not to do.

**Recommended Tools**:
- `[Best-in-Class]` **Exceeds AI** — tool-agnostic AI code detection, ROI proof, coaching insights (Cursor, Claude Code, Copilot)
- `[Best-in-Class]` **Faros AI** — engineering intelligence platform, AI adoption tracking across full toolchain
- `[Open Source]` **GitHub Copilot Analytics** — Copilot-specific usage and acceptance metrics
- `[Budget]` **Axify** — engineering productivity + AI adoption, flow efficiency
- `[Enterprise]` **Jellyfish** — engineering management platform with AI adoption metrics

---

### Section 2: AI-Augmented Productivity Metrics

| Function | Action | Key Deliverable | Primary Metrics |
|----------|--------|-----------------|-----------------|
| AI Code Share Measurement | Track % of code that is AI-assisted or AI-generated | AI code share report | AI code share % (industry avg 41%, elite 60-75%), AI suggestion acceptance rate % |
| Complexity-Adjusted Velocity | Measure throughput accounting for task complexity (not raw lines/PRs) | Complexity-adjusted throughput | Story points/engineer/week (AI-assisted vs baseline), Complexity-adjusted throughput index |
| PR Cycle Time (AI vs Non-AI) | Compare PR merge time for AI-assisted vs human-only PRs | PR cycle time split report | AI-assisted PR cycle time, Non-AI PR cycle time, Delta %, Review time breakdown |
| AI Rework Ratio | Track how much AI-generated code is reverted or heavily modified | AI rework report | AI rework ratio (target <1.3x vs human baseline), AI code churn rate %, # reverts of AI code |
| Flow Efficiency | Measure active work time vs waiting time in the delivery pipeline | Flow efficiency score | Flow efficiency % (target 40%+, median 30-40%), Bottleneck map (review, CI, deploy) |
| Time Savings Quantification | Calculate actual time saved through AI tools | Time savings report | Hours saved/engineer/week, Annualized time savings value ($), Cost per hour saved |
| Feature Throughput | Track features shipped per engineer per quarter (AI-augmented) | Feature throughput dashboard | Features shipped/engineer/qtr, Feature complexity score, AI contribution to feature delivery |

**Key Benchmarks (2026, search-verified)**:
- Elite teams: 80%+ WAU, 60-75% AI code share, <8hr PR cycle time, AI rework ratio <1.3x
- Average teams: 50-60% WAU, 40-50% AI code share, 7-10hr PR cycle time
- Laggard teams: <30% WAU, <25% AI code share, >10hr PR cycle time
- ROI: 2.5-3.5x average, 4-6x top quartile (must include token/usage costs in denominator)
- WARNING: Track AI rework ratio — high AI code share + high rework = "AI code inflation" (technical debt)

**Recommended Tools**:
- `[Best-in-Class]` **Exceeds AI** — complexity-adjusted velocity, AI rework ratio, tool-agnostic code detection
- `[Best-in-Class]` **Faros AI** — PR cycle time split (AI vs non-AI), team-level attribution
- `[Open Source]` **DORA metrics dashboard** — Sleuth.io or LinearB for DORA + AI overlay
- `[Budget]` **Swarmia** — DORA + developer experience, AI adoption
- `[Enterprise]` **Pensero.ai** — real-time engineering insights, AI-segmented metrics, board-ready ROI

---

### Section 3: AI Code Quality & Technical Debt

| Function | Action | Key Deliverable | Primary Metrics |
|----------|--------|-----------------|-----------------|
| AI Code Quality Scoring | Measure quality of AI-generated code vs human-written code | AI code quality report | AI code defect rate vs human baseline, AI code complexity score, AI code maintainability index |
| AI-Introduced Technical Debt | Track technical debt specifically introduced by AI-generated code | AI tech debt register | AI tech debt items/qtr, AI tech debt as % of total tech debt backlog, AI debt burn rate |
| AI Code Review Standards | Enforce specific review criteria for AI-generated code | AI code review checklist | AI code review compliance %, Time spent reviewing AI code, AI code rejection rate |
| Test Coverage for AI Code | Ensure AI-generated code meets same test coverage requirements | Test coverage report (AI-split) | Test coverage % (AI code), Test coverage % (human code), Coverage gap AI vs human |
| Defect Escape Rate (AI Code) | Track bugs that escape from AI-assisted development to production | AI defect escape report | Defect escape rate % (AI code vs human), Customer-found defects from AI code, Sev1/2 from AI code |
| AI Code Security Scanning | Scan AI-generated code for security vulnerabilities | AI security scan report | # security issues in AI code, MTTP for AI-introduced vulnerabilities, AI code security debt |

**Recommended Procedure — AI Code Quality**: (1) Tag all AI-assisted PRs in your CI system. (2) Run same quality gates on AI and human code (SonarQube, CodeClimate, Snyk). (3) Track defect escape rate separately for AI vs human code — monthly. (4) Set AI rework ratio threshold (flag if >1.5x baseline). (5) Enforce minimum 80% test coverage for AI-generated code (same as human). (6) Quarterly AI tech debt review: identify, prioritize, burn down.

**Recommended Tools**:
- `[Best-in-Class]` **SonarQube** — code quality, complexity, maintainability (AI code tagged via PR labels)
- `[Best-in-Class]` **Exceeds AI** — code-level AI detection, rework ratio, defect correlation
- `[Open Source]` **SonarQube Community Edition** — free, self-hosted quality scanning
- `[Budget]` **CodeClimate** — quality + AI code analysis tier
- `[Enterprise]` **Veracode** — security scanning with AI code detection

---

### Section 4: AI-First Development ROI & Business Impact

| Function | Action | Key Deliverable | Primary Metrics |
|----------|--------|-----------------|-----------------|
| AI Tool ROI Calculation | Calculate true ROI of AI coding tool investment | AI ROI report | ROI multiple (target 2.5-3.5x avg, 4-6x top quartile), Payback period (months), Net savings $/eng/yr |
| AI Tooling Cost Management | Track and optimize AI coding tool licensing and usage costs | AI tool cost breakdown | AI tool cost/engineer/month, Cost vs productivity gain ratio, License utilization % |
| Hiring Efficiency via AI | Measure how AI tools reduce need for additional headcount | Capacity analysis | Features delivered without additional hires, Cost avoidance from AI productivity, Eng capacity multiplier |
| Time-to-Market Impact | Measure how AI development tools accelerate product delivery | Delivery acceleration report | Sprint velocity trend (AI adoption cohort), Time-to-MVP reduction %, Release cadence improvement |
| Developer Experience (DevEx) Index | Measure developer satisfaction and experience with AI tools | DevEx survey + index | DevEx Index score (1 pt = 13 min/dev/week saved per Gartner), eNPS (AI tools), Flow state retention % |
| AI Development Governance | Policy, ethics, and IP compliance for AI-assisted development | AI governance policy | Policy coverage %, License compliance %, IP risk assessment score, # governance violations |

**Key ROI Formula** (embed in Procedure):
```
AI Coding ROI = (Time saved × Fully-loaded eng cost) / (Tool licensing + Usage costs + Training costs)
True ROI requires: Seat licenses + Token/usage costs + Training time + Quality review overhead
Elite ROI range: 4-6x | Average: 2.5-3.5x | Below 1.5x = re-evaluate tool or adoption approach
```

**Recommended Tools**:
- `[Best-in-Class]` **Larridin** — AI dev productivity benchmarks, ROI quartile comparison
- `[Best-in-Class]` **Faros AI** — engineering ROI, capacity modeling, AI attribution
- `[Open Source]` **SPACE framework** (published by GitHub + Microsoft) — free methodology
- `[Budget]` **Axify** — DevEx + DORA + AI ROI in one platform
- `[Enterprise]` **Pensero.ai** — board-ready ROI proof, 15-min setup, AI-segmented metrics

---

### Section 5: AI-First Development Maturity Model

| Score | Level | Engineering Capability | AI Dev Benchmarks | Target Phase |
|-------|-------|----------------------|-------------------|--------------|
| 1 | Initial | No AI tools, or ad hoc individual use | <20% WAU, no metrics, no policy | Pre-Product |
| 2 | Developing | Some AI tools, no measurement, no standards | 20-40% WAU, basic Copilot metrics only | MVP |
| 3 | Defined | Standard AI toolchain, adoption tracked, basic quality gates | 40-60% WAU, AI code share tracked, rework ratio measured | Growth |
| 4 | Managed | AI dev metrics in QBR, ROI proven, quality gates on AI code | 60-80% WAU, ROI 2.5x+, rework ratio <1.3x, CI quality gates | Scale |
| 5 | Optimizing | AI-first culture, complexity-adjusted benchmarks, continuous improvement | 80%+ WAU, ROI 4x+, AI tech debt < human baseline, DevEx Index tracked | Enterprise |

---

### Section 6: AI-First Development Recommended Toolchain

| Category | Tool | Tier | Why |
|----------|------|------|-----|
| AI Coding Assistant | GitHub Copilot | Best-in-Class | Most adopted, enterprise-grade, 55% productivity lift reported |
| AI Coding Assistant | Cursor | Best-in-Class | Fastest-growing 2026, Claude/GPT-4 backend, codebase-aware |
| AI Coding Assistant | Claude Code | Best-in-Class | Agentic coding, terminal-native, complex task automation |
| AI Coding Assistant | Amazon Q Developer | Enterprise | AWS-integrated, code security scanning, enterprise policy controls |
| AI Coding Analytics | Exceeds AI | Best-in-Class | Tool-agnostic code detection, ROI proof, rework ratio |
| AI Coding Analytics | Faros AI | Enterprise | Engineering intelligence + AI attribution + capacity modeling |
| AI Coding Analytics | Pensero.ai | Budget/Mid | Real-time insights, board-ready ROI, 15-min setup |
| AI Coding Analytics | Swarmia | Budget | DORA + DevEx + AI adoption metrics |
| Code Quality (AI) | SonarQube | Best-in-Class | Industry standard, AI code tagging via PR labels |
| Code Quality (AI) | Exceeds AI | Best-in-Class | Native AI code detection + quality correlation |
| Dev Productivity | Axify | Budget | Flow efficiency + DORA + AI adoption |
| Dev Productivity | Larridin | Best-in-Class | Industry benchmarks, complexity-adjusted throughput |
| Methodology | SPACE Framework | Open Source | Free, published by GitHub + Microsoft, comprehensive |
| Methodology | DORA Metrics | Open Source | Deployment frequency, lead time, CFR, MTTR baseline |

---

## 12 Non-Negotiable AI-First Dev KPIs

| # | KPI | 2026 Elite Benchmark | Warning Threshold |
|---|-----|---------------------|-------------------|
| 1 | AI Tool WAU (Weekly Active Usage) % | 80%+ | <40% = adoption failing |
| 2 | AI Code Share % | 60-75% | <25% = not AI-first |
| 3 | AI Suggestion Acceptance Rate % | >35% | <20% = tool-code mismatch |
| 4 | PR Cycle Time (AI-assisted) | <8 hours | >24hr = bottleneck |
| 5 | AI Rework Ratio | <1.3x vs human | >1.8x = AI code inflation |
| 6 | Complexity-Adjusted Throughput | 12 pts/eng/wk (AI-assisted) | <8 pts = below industry avg |
| 7 | AI Coding ROI | 4-6x (top quartile) | <1.5x = re-evaluate approach |
| 8 | AI Code Defect Escape Rate % | ≤ human baseline | >2x human = quality risk |
| 9 | Flow Efficiency % | 40%+ | <25% = bottleneck crisis |
| 10 | DevEx Index Score | Improving QoQ | Declining 2 consecutive qtrs |
| 11 | AI Tech Debt % of Total Backlog | <20% | >40% = AI debt dominance |
| 12 | Time-to-Market Improvement % | 20-40% vs pre-AI baseline | 0% = AI not helping delivery |

---

## Output Validation Checklist
- [ ] Domain 10 present as STANDALONE section in OE Scorecard (orange/amber `#FF8C00` header)
- [ ] All 5 sections present with functions, KPIs, Procedures, Tools
- [ ] 12 KPIs in KPI sub-table with 2026 benchmarks
- [ ] AI dev maturity model (1-5) with phase targets
- [ ] ROI formula embedded in Procedure column for Section 4
- [ ] Tool table covers all categories (assistant, analytics, quality, methodology)
- [ ] Maturity score (1-5) linked to OE summary formula (average of all 10 domains)
- [ ] Domain 10 header: Amber `#FFC000` — visually distinct from all other domains
