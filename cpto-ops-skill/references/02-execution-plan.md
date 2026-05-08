# Reference: Execution Plan & Task Tracking

## Purpose
Translate strategic priorities into a concrete, trackable execution plan. This is the operational
backbone — every workstream, task, owner, and timeline in one place.

## Source Template
Based on `Lumenci_Execution_Strategy_and_Plan.xlsx`:
- Sheet 1: `Product Management Activities` (task tracker)
- Sheet 2: `Strategic Mix` (horizon planning)
- Sheet 3: `Top Priorities` (priority stack)

---

## Sheet 1: Product Management Activities

### Schema
| Column | Header | Description |
|--------|--------|-------------|
| A | Item No | Auto-numbered (e.g., 1.1, 1.2, 2.1) |
| B | Workstreams / Tasks | Workstream name (bold) or task name (indented) |
| C | Status | Not Started / In Progress / On Hold / Blocked / Done |
| D | Owner | Person or team responsible |
| E | Priority | High / Medium / Low |
| F | Start Date | Planned start |
| G | Target Date | Planned completion |
| H | Actual Date | Actual completion (formula-driven) |
| I | % Complete | 0-100% (manual or formula: `=IF(C2="Done",100,IF(C2="In Progress",50,0))`) |
| J | Sprint/Milestone | Sprint number or milestone name |
| K | Dependencies | Item numbers this task depends on |
| L | **Recommended Procedure** | Best-practice process for this task type (auto-populated by skill) |
| M | **Recommended Tools** | 2-4 named tools with category tags (auto-populated by skill) |
| N | Notes | Blockers, context, decisions |

### Core Workstreams (from Lumenci Framework)

Always include these top-level workstreams — add product-specific ones after:

**1. Team Structure**
- Create stakeholder team
- Create product team structure
- Setup regular team update calls
- Assign roles and responsibilities
- Create Product Advisory Board (PAB)
- Setup PAB meetings
- Skills assessment
- ✓ Team Structure Complete

**2. Tools and Infrastructure**
- Create master plan repository
- Setup financial tools
- Configure project management tooling (Jira/Linear/Asana)
- Setup communication channels (Slack structure)
- Configure CI/CD pipeline
- Setup monitoring/observability stack
- ✓ Tools & Infrastructure Complete

**3. Strategy & Roadmap**
- Define product vision & mission
- Conduct market & competitive analysis
- Define customer segments and ICPs
- Develop product roadmap (quarterly)
- Define OKRs and KPIs
- Create pricing & packaging strategy
- ✓ Strategy & Roadmap Complete

**4. Product Development**
- Define feature backlog with priorities
- Sprint planning setup
- Design system / UX standards
- Architecture design review
- Engineering kickoff
- QA / test automation framework
- ✓ Product Development Track Complete

**5. GTM & Launch**
- Define launch strategy
- Create GTM plan
- Sales enablement preparation
- Marketing campaign planning
- Launch readiness review
- ✓ GTM & Launch Complete

**6. Operational Excellence**
- Setup SLO/SLA targets
- Incident response process
- On-call rotation setup
- Monitoring & alerting configuration
- Post-incident review cadence
- ✓ Ops Excellence Complete

**7. Security & Compliance**
- Security threat model
- Compliance requirements assessment (SOC2, GDPR, etc.)
- Penetration testing schedule
- Security training for team
- ✓ Security & Compliance Complete

**8. AI & Agentic [if applicable]**
- AI use case prioritization
- LLM/model selection
- AI architecture design
- Responsible AI policy
- AI metrics & evaluation framework
- ✓ AI & Agentic Complete

### Python Generation Pattern

```python
# Workstream rows: bold, medium blue fill (#2E75B6), white text, no item number
# Task rows: normal weight, alternating white/#DCE6F1, indented in column B
# Milestone rows (✓): italic, green fill (#70AD47)

# Item numbering: workstream = "1.", tasks = "1.1", "1.2", etc.
# Status dropdown: data_validation with list
# % Complete formula: =IF(C{row}="Done",100,IF(C{row}="In Progress",50,IF(C{row}="In Progress",50,0)))
# Conditional format column C by status color
```

---

## Sheet 2: Strategic Mix

### Purpose
Horizon planning across 3 time periods. Answers the strategic questions every CPTO must address.

### Schema
| Column | Header |
|--------|--------|
| A | (blank — question category) |
| B | Strategic Question |
| C | < 1 Year Response |
| D | 1-2 Years Response |
| E | 3+ Years Response |

### Strategic Questions (from Lumenci Framework)

**External Market Focus**
- What will the industry look like? Will you be expanding into other industry areas?
- Which products will you compete with? How will your products be competitively positioned?
- What are your attack and defend strategies?
- Which segments will you pursue and why? How will customer needs evolve?

**Internal Support**
- How much money will you need? What are the budgetary requirements?
- What talent and team capabilities are required?
- What infrastructure investments are needed?

**Product Strategy**
- What is the core value proposition for each horizon?
- Which features differentiate vs. maintain competitive parity?
- What is the build vs. buy vs. partner decision framework?

**Go-to-Market**
- What channels will you prioritize?
- What is the pricing evolution?
- What partnerships accelerate GTM?

**Technology & Platform**
- What is the architecture evolution?
- What AI/ML capabilities will be native vs. integrated?
- What platform capabilities enable the product strategy?

---

## Sheet 3: Top Priorities

See `references/01-top-priorities.md` for full schema. This tab is the same as the standalone output
but embedded in the execution workbook for cross-referencing.

---

## Recommended Tools by Workstream

| Workstream | Recommended Procedure | Recommended Tools |
|------------|----------------------|-------------------|
| Team Structure | RACI → skills matrix → weekly cadence | `[Best-in-Class]` Notion (org docs) · `[Best-in-Class]` Lattice (people ops) · `[Budget]` Confluence |
| Tools & Infrastructure | Vendor eval matrix → PoC → rollout plan | `[Best-in-Class]` GitHub (source control) · `[Best-in-Class]` Terraform (IaC) · `[Open Source]` ArgoCD (GitOps) · `[Enterprise]` Harness |
| Strategy & Roadmap | OKR cascade → quarterly roadmap review | `[Best-in-Class]` Productboard · `[Best-in-Class]` Aha! · `[Budget]` Linear · `[Enterprise]` Jira Advanced Roadmaps |
| Product Development | Sprint ceremonies → definition of done | `[Best-in-Class]` Linear · `[Best-in-Class]` Jira · `[Best-in-Class]` Figma (design) · `[Open Source]` GitLab |
| GTM & Launch | Launch checklist → go/no-go gate process | `[Best-in-Class]` Asana (launch tracking) · `[Best-in-Class]` HubSpot · `[Budget]` Trello · `[Enterprise]` Salesforce |
| Operational Excellence | SLO definition → runbook creation → postmortem process | `[Best-in-Class]` PagerDuty · `[Best-in-Class]` Datadog · `[Open Source]` Grafana/Prometheus · `[Enterprise]` Dynatrace |
| Security & Compliance | Threat model → SDLC gates → pen test schedule | `[Best-in-Class]` Snyk · `[Best-in-Class]` Vanta · `[Open Source]` OWASP ZAP · `[Enterprise]` Wiz |
| AI & Agentic | Use-case prioritization → eval framework → production monitoring | `[Best-in-Class]` LangSmith · `[Open Source]` LangFuse · `[Best-in-Class]` Weights & Biases · `[Enterprise]` Datadog LLM Observability |

## User Input Collection Sequence

When generating the Execution Plan, ask the user:

1. **Company & Product**: "What is the product name and company?"
2. **Phase**: "What phase is the product in? (Pre-product / MVP / Growth / Scale / Enterprise)"
3. **Team Size**: "How large is the engineering/product team?"
4. **Timeline**: "What is the target launch or milestone date?"
5. **Custom Workstreams**: "Are there specific workstreams beyond the standard ones? (e.g., Partner integrations, M&A integration, AI features)"
6. **Current Status**: "Which tasks are already in progress or done?"

Then auto-populate with sensible defaults and let user refine.

---

## Validation Rules
- [ ] Every task has an owner (role or name)
- [ ] Every task has a target date
- [ ] No orphaned tasks (every task belongs to a workstream)
- [ ] Milestone rows mark completion of each workstream
- [ ] % Complete column uses Excel formula (not hardcoded)
- [ ] Status column uses data validation dropdown
