# Reference: SaaS Engineering Principles Assessment

## Purpose
Assess engineering maturity across all 25 SaaS Engineering Principles. This produces a complete
multi-tab Excel workbook with product-specific analysis, maturity scores (1-5), and action items.

## Source Template
Based on `Lumenci_SaaS_Engineering_Principles_Checklists.xlsx` (25 principle tabs + Overview)

---

## The 25 SaaS Engineering Principles

### Foundations (Principles 1-4)
| # | Principle | Focus Area |
|---|-----------|------------|
| 1 | Live Site Focus | Production health, customer-centricity, incident response |
| 2 | Engineering Agility | CI/CD, DevOps, team structure, delivery velocity |
| 3 | Troubleshooting | Detection, diagnosis, runbooks, RCA |
| 4 | Business Model | Value proposition, pricing, revenue predictability |

### Diagnostics (Principles 5-7)
| # | Principle | Focus Area |
|---|-----------|------------|
| 5 | Service Health Data | Metrics collection, dashboards, anomaly detection |
| 6 | Telemetry Data | Instrumentation, data pipeline, storage strategy |
| 7 | Analytics & Visualization | Data integration, dashboards, real-time capabilities |

### Availability (Principles 8-11)
| # | Principle | Focus Area |
|---|-----------|------------|
| 8 | High Availability | Architecture, fault isolation, graceful degradation |
| 9 | Redundancy | Compute/storage/network redundancy, failover |
| 10 | Disaster Recovery | RPO/RTO, backup systems, recovery automation |
| 11 | Business Continuity | BIA, continuity procedures, communication protocols |

### Security & Privacy (Principles 12-15)
| # | Principle | Focus Area |
|---|-----------|------------|
| 12 | Security Compliance | Governance, access control, data protection |
| 13 | Data Privacy | Privacy governance, data minimization, retention |
| 14 | Security Threats | Threat intelligence, preventive controls, detection |
| 15 | Vulnerability Management | Scanning, penetration testing, remediation |

### Performance & Scale (Principles 16-18)
| # | Principle | Focus Area |
|---|-----------|------------|
| 16 | Performance Optimization | Metrics, profiling, caching, DB optimization |
| 17 | Scalability Architecture | Horizontal scale, auto-scaling, capacity planning |
| 18 | Multi-Tenancy | Tenant isolation, onboarding, lifecycle management |

### Deployment Practices (Principles 19-21)
| # | Principle | Focus Area |
|---|-----------|------------|
| 19 | CI/CD Practices | Build automation, test automation, deployment pipelines |
| 20 | Release & Feature Flags | Release strategy, flag architecture, flag lifecycle |
| 21 | Deployment & IaC | Infrastructure as code, zero-downtime deployment |

### Operability (Principles 22-25)
| # | Principle | Focus Area |
|---|-----------|------------|
| 22 | Observability | Metrics, logging, distributed tracing |
| 23 | Operational Excellence | Runbooks, automation, SRE practices |
| 24 | Self-Service | User provisioning, configuration, integrations |
| 25 | Alerting | Alert definition, routing, escalation |

---

## Tab Structure (per principle)

Each tab has this structure:
```
Row 1: [Principle Name] Checklist                    (title, merged, navy)
Row 2: Instructions text                              (italic, gray)
Row 3: Item | Description | Maturity (1-5) | Notes   (header, navy)
Row 4+: Category header rows (medium blue)
Row 5+: Checklist items with maturity scores and notes
Last row: Overall Score formula
```

### Maturity Scale
| Score | Level | Description |
|-------|-------|-------------|
| 1 | Initial | Ad hoc, undocumented, reactive |
| 2 | Developing | Some processes exist, inconsistently applied |
| 3 | Defined | Documented, consistently applied |
| 4 | Managed | Measured, managed with data |
| 5 | Optimizing | Continuously improved, industry-leading |

### Overview Tab: Summary Scorecard

The Overview tab gets a summary table added:
```
| Principle | Score | Target | Gap | Priority | Recommended Procedure | Recommended Tools |
```
- Score = AVERAGE of all maturity scores in that tab
- Target = user-defined target (default 4.0)
- Gap = Target - Score
- Priority = IF(Gap>2, "Critical", IF(Gap>1, "High", IF(Gap>0, "Medium", "On Track")))

---

## How To Fill Analysis From User Input

When generating the SaaS Engineering assessment, ask:

1. **Architecture Overview**: "Describe your architecture briefly (microservices/monolith, cloud provider, key services)"
2. **Current Pain Points**: "What are your top 3 engineering/operational pain points?"
3. **Team Maturity**: "How mature is your DevOps/SRE practice? (1-5)"
4. **Compliance Requirements**: "Any specific compliance needs? (SOC2, HIPAA, GDPR, FedRAMP)"
5. **Scale**: "Current user/tenant count? Expected 12-month growth?"

Then for each principle tab:
- Set Maturity scores based on stated architecture and pain points
- Add product-specific Notes explaining WHY that score was given
- Flag items scoring ≤2 with "⚠️ ACTION REQUIRED" in Notes
- Items scoring 5 get "✓ Strength — maintain and document"

### Score Assignment Heuristics by Phase

**Pre-Product / MVP Phase**
- Principles 1-4: 2-3 (foundations being built)
- Principles 8-11: 1-2 (not yet critical)
- Principles 12-15: 2-3 (must establish early)
- Principles 19-21: 3-4 (CI/CD is table stakes)

**Growth Phase**
- Principles 5-7: 3-4 (data becomes critical)
- Principles 8-9: 3-4 (HA now required)
- Principles 16-18: 3-4 (performance at scale)

**Enterprise / Scale Phase**
- All principles: 4-5 target
- Principles 10-15: 4-5 mandatory
- Principles 22-25: 4-5 mandatory

---

## Python Generation Pattern

```python
# Load source template or build from scratch
# For each of 25 principles:
#   - Set tab name per source (e.g., "1. Live Site Focus")
#   - Populate checklist items from the known framework
#   - Fill Maturity (1-5) based on user input
#   - Fill Notes with product-specific analysis
#   - Add overall average formula at bottom: =AVERAGE(C4:C{last_row})
#
# Add "Overview" tab first with summary scorecard
# Add "26. AI & Agentic" tab last (see references/04-ai-agentic.md)
# Add "OE Scorecard" tab (see references/06-ops-excellence.md)

# Color mapping for maturity scores:
MATURITY_COLORS = {
    1: "FF0000",  # Red — Critical
    2: "FF7E00",  # Orange — Needs Work
    3: "FFD966",  # Yellow — Developing
    4: "92D050",  # Light Green — Good
    5: "00B050",  # Green — Excellent
}
```

---

## Output Validation Checklist
- [ ] All 25 principle tabs present and named correctly
- [ ] Every checklist item has a maturity score (1-5)
- [ ] Every checklist item has a product-specific note
- [ ] Overview tab has summary with average scores
- [ ] Items ≤2 are flagged with action recommendations
- [ ] No formula errors (#REF!, #DIV/0!, etc.)
- [ ] Conditional formatting applied to Maturity column

## Recommended Procedures + Tools Per Principle Group

### Foundations (1–4)
| Principle | Recommended Procedure | Recommended Tools |
|-----------|----------------------|-------------------|
| 1. Live Site Focus | On-call rotation setup → SLO definition → blameless postmortem cadence → customer communication SLA | `[Best-in-Class]` PagerDuty · `[Best-in-Class]` Datadog · `[Open Source]` Grafana · `[Enterprise]` Dynatrace |
| 2. Engineering Agility | CI/CD pipeline audit → DORA metrics baseline → sprint health review | `[Best-in-Class]` GitHub Actions · `[Best-in-Class]` Linear · `[Open Source]` GitLab CI · `[Enterprise]` Harness |
| 3. Troubleshooting | Runbook library → structured RCA template → detection-to-resolution SLA | `[Best-in-Class]` Notion (runbooks) · `[Best-in-Class]` Datadog · `[Open Source]` Grafana · `[Enterprise]` Dynatrace Davis AI |
| 4. Business Model | Value prop canvas → pricing model review → ARR/NRR tracking dashboard | `[Best-in-Class]` Stripe (billing) · `[Best-in-Class]` ChartMogul (SaaS metrics) · `[Budget]` Baremetrics · `[Enterprise]` Zuora |

### Diagnostics (5–7)
| Principle | Recommended Procedure | Recommended Tools |
|-----------|----------------------|-------------------|
| 5. Service Health Data | MELT instrumentation plan → dashboard standards → alert hygiene review | `[Best-in-Class]` Datadog · `[Open Source]` Prometheus + Grafana · `[Budget]` Better Stack · `[Enterprise]` Splunk |
| 6. Telemetry Data | OpenTelemetry instrumentation → data pipeline design → retention policy | `[Best-in-Class]` Honeycomb · `[Open Source]` OpenTelemetry + Jaeger · `[Budget]` New Relic (free tier) · `[Enterprise]` Dynatrace |
| 7. Analytics & Visualization | Data warehouse design → BI tool rollout → self-serve analytics training | `[Best-in-Class]` Looker/Tableau · `[Open Source]` Metabase · `[Budget]` Redash · `[Enterprise]` Snowflake + dbt |

### Availability (8–11)
| Principle | Recommended Procedure | Recommended Tools |
|-----------|----------------------|-------------------|
| 8. High Availability | HA architecture review → fault injection testing → chaos engineering plan | `[Best-in-Class]` AWS/GCP/Azure multi-AZ · `[Open Source]` Chaos Monkey · `[Enterprise]` Gremlin (chaos engineering) |
| 9. Redundancy | Redundancy mapping by service tier → failover testing → quarterly DR drill | `[Best-in-Class]` AWS Route53 + ALB · `[Best-in-Class]` Cloudflare · `[Enterprise]` F5 NGINX Plus |
| 10. Disaster Recovery | RPO/RTO definition → backup automation → quarterly recovery test | `[Best-in-Class]` AWS Backup · `[Best-in-Class]` Veeam · `[Open Source]` Velero (K8s) · `[Enterprise]` Zerto |
| 11. Business Continuity | BIA (Business Impact Analysis) → BC plan → tabletop exercises | `[Best-in-Class]` Everbridge · `[Best-in-Class]` ServiceNow BCM · `[Budget]` Confluence BC templates |

### Security & Privacy (12–15)
| Principle | Recommended Procedure | Recommended Tools |
|-----------|----------------------|-------------------|
| 12. Security Compliance | Compliance gap analysis → control mapping → evidence collection → annual audit | `[Best-in-Class]` Vanta · `[Best-in-Class]` Drata · `[Budget]` Tugboat Logic · `[Enterprise]` OneTrust |
| 13. Data Privacy | Data inventory → DPIA → retention policy → consent management | `[Best-in-Class]` OneTrust · `[Best-in-Class]` BigID · `[Budget]` Osano · `[Enterprise]` Informatica |
| 14. Security Threats | Threat intel subscription → SIEM alert tuning → purple team exercises | `[Best-in-Class]` CrowdStrike · `[Best-in-Class]` SentinelOne · `[Open Source]` Wazuh · `[Enterprise]` Microsoft Sentinel |
| 15. Vulnerability Management | Asset inventory → CVSS prioritization → patch SLA by severity → scan cadence | `[Best-in-Class]` Snyk · `[Best-in-Class]` Wiz · `[Open Source]` OpenVAS · `[Enterprise]` Tenable |

### Performance & Scale (16–18)
| Principle | Recommended Procedure | Recommended Tools |
|-----------|----------------------|-------------------|
| 16. Performance Optimization | Baseline P50/P95/P99 → profiling sessions → caching strategy → DB query review | `[Best-in-Class]` Datadog APM · `[Best-in-Class]` New Relic · `[Open Source]` Pyroscope (profiling) · `[Enterprise]` Dynatrace |
| 17. Scalability Architecture | Load test at 2x/10x → auto-scale policy → capacity plan → cost projection | `[Best-in-Class]` k6 (load testing) · `[Best-in-Class]` AWS Auto Scaling · `[Open Source]` Locust · `[Enterprise]` KEDA |
| 18. Multi-Tenancy | Tenant isolation model review → provisioning automation → usage metering | `[Best-in-Class]` Stripe (metered billing) · `[Best-in-Class]` Auth0 (tenant isolation) · `[Enterprise]` Stigg (entitlements) |

### Deployment Practices (19–21)
| Principle | Recommended Procedure | Recommended Tools |
|-----------|----------------------|-------------------|
| 19. CI/CD Practices | Pipeline audit → DORA metrics → test coverage gates → build time optimization | `[Best-in-Class]` GitHub Actions · `[Best-in-Class]` CircleCI · `[Open Source]` Jenkins · `[Enterprise]` Harness CI/CD |
| 20. Release & Feature Flags | Flag taxonomy → lifecycle policy → % rollout → flag cleanup sprints | `[Best-in-Class]` LaunchDarkly · `[Best-in-Class]` Flagsmith · `[Open Source]` Unleash · `[Budget]` Split.io |
| 21. Deployment & IaC | Terraform modules → GitOps workflow → drift detection → zero-downtime deploy checklist | `[Best-in-Class]` Terraform + Atlantis · `[Best-in-Class]` Pulumi · `[Open Source]` ArgoCD · `[Enterprise]` Spacelift |

### Operability (22–25)
| Principle | Recommended Procedure | Recommended Tools |
|-----------|----------------------|-------------------|
| 22. Observability | OTel instrumentation → 3-pillar coverage (metrics/logs/traces) → SLO dashboards | `[Best-in-Class]` Datadog · `[Best-in-Class]` Honeycomb · `[Open Source]` Grafana LGTM stack · `[Enterprise]` Dynatrace |
| 23. Operational Excellence | Runbook library → SRE error budget policy → toil reduction OKR | `[Best-in-Class]` PagerDuty · `[Best-in-Class]` FireHydrant (incident mgmt) · `[Open Source]` Grafana OnCall · `[Enterprise]` xMatters |
| 24. Self-Service | Provisioning automation → API-first design → developer portal | `[Best-in-Class]` Backstage (developer portal) · `[Best-in-Class]` Stripe (self-serve billing) · `[Enterprise]` Salesforce Communities |
| 25. Alerting | Alert taxonomy → noise reduction → escalation policy → on-call health metrics | `[Best-in-Class]` PagerDuty · `[Best-in-Class]` Opsgenie · `[Open Source]` Alertmanager · `[Enterprise]` BigPanda (AIOps alert correlation) |


---

## Recommended Procedures & Tools By Principle (Search-Verified May 2026)

| # | Principle | Recommended Procedure | Recommended Tools |
|---|-----------|----------------------|-------------------|
| 1 | Live Site Focus | 1. Define SLOs per service. 2. Error budget policy. 3. Blameless PIR for every Sev1. 4. Weekly site review. | `[Best]` Datadog · `[OSS]` Grafana LGTM · `[Budget]` Better Stack · `[Ent]` Dynatrace |
| 2 | Engineering Agility | 1. Baseline DORA metrics. 2. Set quarterly improvement targets. 3. CI/CD gate on every PR. | `[Best]` GitHub Actions · `[OSS]` Jenkins, ArgoCD · `[Budget]` CircleCI · `[Ent]` Harness |
| 3 | Troubleshooting | 1. Runbook per top 20 incidents. 2. RCA template. 3. Blameless review cadence. | `[Best]` PagerDuty · `[OSS]` Rootly · `[Budget]` Incident.io · `[Ent]` ServiceNow IM |
| 4 | Business Model | 1. Pricing review semi-annually. 2. Unit economics dashboard. 3. ARR/NRR cohort tracking. | `[Best]` Stripe — billing · `[Best]` ChartMogul — SaaS metrics · `[Ent]` Maxio |
| 5 | Service Health Data | 1. Define golden signals per service. 2. Build health dashboard. 3. Anomaly alerts on all golden signals. | `[Best]` Datadog · `[OSS]` Prometheus+Grafana · `[Budget]` New Relic (free) · `[Ent]` Dynatrace |
| 6 | Telemetry Data | 1. Adopt OpenTelemetry standard. 2. Instrument all services. 3. Define retention policy. | `[Best]` Datadog · `[OSS]` OpenObserve, Jaeger · `[Budget]` Grafana Cloud · `[Ent]` Dynatrace |
| 7 | Analytics & Visualization | 1. Unified data platform. 2. Real-time dashboard per persona. 3. Self-serve analytics for PMs. | `[Best]` Amplitude · `[OSS]` Grafana · `[Budget]` Mixpanel · `[Ent]` Looker, Tableau |
| 8 | High Availability | 1. Define availability SLO. 2. Multi-zone/region deploy. 3. Chaos engineering monthly. | `[Best]` AWS/GCP multi-AZ · `[OSS]` Chaos Monkey · `[Best]` Datadog SLOs · `[Ent]` Dynatrace |
| 9 | Redundancy | 1. N+1 redundancy for all critical services. 2. Automated failover testing quarterly. | `[Best]` AWS Route 53, GCP Cloud DNS · `[OSS]` HAProxy · `[Ent]` F5 · `[Best]` Cloudflare |
| 10 | Disaster Recovery | 1. Define RPO/RTO per tier. 2. Automated backup verification. 3. DR test quarterly. | `[Best]` AWS Backup · `[OSS]` Velero (K8s) · `[Budget]` Backblaze B2 · `[Ent]` IBM Resiliency |
| 11 | Business Continuity | 1. BIA annually. 2. BC playbook documented. 3. Communication protocol tested. | `[Best]` PagerDuty — BC orchestration · `[OSS]` Netdata · `[Ent]` Everbridge |
| 12 | Security Compliance | 1. NIST CSF maturity annually. 2. Access review quarterly. 3. Compliance automation. | `[Best]` Vanta · `[Best]` Drata · `[OSS]` OpenSCAP · `[Ent]` Archer GRC |
| 13 | Data Privacy | 1. DPIA for new features. 2. Data inventory maintained. 3. Retention policy enforced. | `[Best]` OneTrust · `[Best]` Osano · `[OSS]` OpenDPR · `[Ent]` BigID |
| 14 | Security Threats | 1. Threat model per product quarter. 2. Threat intel subscription. 3. SIEM alerts reviewed daily. | `[Best]` CrowdStrike Falcon · `[OSS]` OSSEC · `[Budget]` Wazuh · `[Ent]` Microsoft Sentinel |
| 15 | Vulnerability Mgmt | 1. Continuous scanning in CI. 2. MTTP SLAs (Critical: 24h). 3. Bug bounty program. | `[Best]` Snyk · `[OSS]` OWASP ZAP, Trivy · `[Budget]` Snyk (free) · `[Ent]` Wiz, Veracode |
| 16 | Performance Optimization | 1. Define performance SLOs. 2. Load test every release. 3. Profile hot paths monthly. | `[Best]` Datadog APM · `[OSS]` k6, Locust · `[Budget]` Grafana k6 Cloud · `[Ent]` Dynatrace |
| 17 | Scalability Architecture | 1. Horizontal scaling by default. 2. Auto-scaling configured. 3. Capacity plan per quarter. | `[Best]` AWS Auto Scaling · `[OSS]` KEDA (K8s) · `[Best]` Datadog Forecast · `[Ent]` Turbonomic |
| 18 | Multi-Tenancy | 1. Tenant isolation design review. 2. Per-tenant metering. 3. Lifecycle automation. | `[Best]` Stripe — billing per tenant · `[Best]` Auth0/Okta — tenant isolation · `[OSS]` Keycloak |
| 19 | CI/CD Practices | 1. All code through pipeline. 2. 80%+ test automation. 3. Deploy-on-green policy. | `[Best]` GitHub Actions · `[OSS]` Jenkins, Tekton, ArgoCD · `[Budget]` CircleCI · `[Ent]` Harness |
| 20 | Release & Feature Flags | 1. Feature flags for every major feature. 2. Flag lifecycle policy. 3. Canary releases default. | `[Best]` LaunchDarkly — flag management · `[OSS]` Unleash · `[Budget]` Flagsmith · `[Ent]` Split.io |
| 21 | Deployment & IaC | 1. All infra as code. 2. No manual infra changes. 3. GitOps workflow for deployments. | `[Best]` Terraform + Atlantis · `[OSS]` Pulumi OSS, ArgoCD · `[Budget]` CDK (AWS) · `[Ent]` Env0 |
| 22 | Observability | 1. Instrument metrics+logs+traces per service. 2. Dashboards per team. 3. Golden signal alerts. | `[Best]` Datadog · `[OSS]` Grafana LGTM+OTel · `[Budget]` Better Stack · `[Ent]` Honeycomb, Dynatrace |
| 23 | Operational Excellence | 1. Runbooks for top 20 incidents. 2. On-call rotation. 3. Blameless PIR cadence. | `[Best]` PagerDuty · `[OSS]` Rootly · `[Budget]` Incident.io · `[Ent]` ServiceNow ITSM |
| 24 | Self-Service | 1. Self-service provisioning for all users. 2. Config management UI. 3. Self-serve analytics. | `[Best]` Retool — internal tools · `[OSS]` Backstage (Spotify) · `[Budget]` Budibase · `[Ent]` ServiceNow |
| 25 | Alerting | 1. Alert on symptoms not causes. 2. Alert hierarchy (Sev1-3). 3. Reduce noise monthly. | `[Best]` PagerDuty · `[OSS]` Alertmanager · `[Budget]` Better Stack · `[Ent]` Dynatrace, OpsGenie |

## Excel Column Update
All SaaS Principle assessment rows now include two additional columns after Notes:
- Column G: **Recommended Procedure** (light green `#E2EFDA`) — numbered steps, phase-aware
- Column H: **Recommended Tools** (light purple `#EAE0F5`) — 4 tiers: Best/OSS/Budget/Enterprise
