# Reference: AI & Agentic Analysis Tab

## Purpose
Assess the AI and Agentic components of the product architecture with the same rigor as the 25 SaaS
Engineering Principles. This is appended as tab "26. AI & Agentic" to the SaaS Engineering workbook.

## Context
AI-native and AI-augmented SaaS products require a dedicated analysis layer that goes beyond traditional
SaaS engineering principles. This framework covers: LLM integration, agentic workflow design, AI safety,
evaluation pipelines, cost management, and responsible AI governance.

---

## Tab Structure: "26. AI & Agentic"

### Section 1: AI Product Strategy
| Item | Description | Maturity (1-5) | Notes |
|------|-------------|----------------|-------|
| AI Use Case Definition | Clear, prioritized list of AI use cases with business value | | |
| AI Value Proposition | Quantifiable improvement AI delivers (time saved, accuracy, throughput) | | |
| Build vs. Buy vs. Partner | Decision framework for LLM/AI component sourcing | | |
| AI Roadmap | Quarterly AI feature roadmap aligned to product strategy | | |
| Competitive AI Differentiation | AI capabilities that distinguish from competitors | | |

### Section 2: AI Architecture & Infrastructure
| Item | Description | Maturity (1-5) | Notes |
|------|-------------|----------------|-------|
| LLM Selection & Versioning | Model selection criteria, versioning strategy, fallback models | | |
| Prompt Engineering & Management | Systematic prompt design, versioning, and testing | | |
| Context Window Management | Efficient use of context, chunking strategies, RAG implementation | | |
| Vector Database & Embeddings | Embedding strategy, vector store selection, retrieval optimization | | |
| AI API Gateway | Centralized AI request routing, rate limiting, cost controls | | |
| Multi-Model Architecture | Strategy for using multiple models for different tasks | | |
| Fine-Tuning Strategy | When and how to fine-tune vs. prompt engineer vs. RAG | | |
| AI Caching | Response caching, semantic caching to reduce cost/latency | | |

### Section 3: Agentic Workflow Design
| Item | Description | Maturity (1-5) | Notes |
|------|-------------|----------------|-------|
| Agent Architecture | Agent framework selection (LangGraph, AutoGen, custom, etc.) | | |
| Tool & Function Calling | Design of tools agents can invoke, error handling | | |
| Human-in-the-Loop Design | Decision points requiring human approval or review | | |
| Agent Orchestration | Multi-agent coordination, task decomposition, routing | | |
| Agentic Memory Management | Short-term, long-term, and episodic memory for agents | | |
| Agent State Management | Persistence, resumability, and state recovery | | |
| Agent Guardrails | Safety constraints, output validation, refusal handling | | |
| Agentic Task Queuing | Async task management, priority queues, retry logic | | |

### Section 4: AI Quality & Evaluation
| Item | Description | Maturity (1-5) | Notes |
|------|-------------|----------------|-------|
| Evaluation Framework (Evals) | Automated evals for model output quality | | |
| Ground Truth Dataset | Curated examples for regression testing AI behavior | | |
| Human Evaluation Process | Expert review pipeline for AI output quality | | |
| A/B Testing for AI | Framework for comparing model versions and prompts | | |
| Hallucination Detection | Mechanisms to detect and reduce confabulation | | |
| Output Consistency Testing | Ensuring deterministic behavior where required | | |
| Regression Testing | Detecting quality degradation across model upgrades | | |

### Section 5: AI Observability & Operations
| Item | Description | Maturity (1-5) | Notes |
|------|-------------|----------------|-------|
| AI Request Tracing | End-to-end tracing of AI calls (prompt → response → action) | | |
| LLM Latency Monitoring | P50/P95/P99 latency tracking per model and endpoint | | |
| Token Usage Tracking | Input/output token consumption per feature, per customer | | |
| AI Error Rate Monitoring | Tracking failed, refused, and degraded AI responses | | |
| AI Cost per Request | Cost attribution to features, customers, and use cases | | |
| Model Drift Detection | Alerting when model behavior changes unexpectedly | | |
| AI Incident Playbooks | Runbooks for AI-specific incidents (hallucination surges, etc.) | | |

### Section 6: AI Cost Management (FinOps for AI)
| Item | Description | Maturity (1-5) | Notes |
|------|-------------|----------------|-------|
| Cost Attribution | Mapping AI spend to features, customers, and business value | | |
| Cost-per-Feature Budgeting | Budgets and alerts per AI-powered feature | | |
| Token Optimization | Prompt compression, batching, model downgrading where appropriate | | |
| Caching ROI | Measuring cost savings from AI response caching | | |
| Make vs. Buy Analysis | Ongoing analysis of build vs. API costs at scale | | |
| AI Cost Forecasting | Modeling AI cost growth with user/usage growth | | |

### Section 7: AI Safety & Responsible AI
| Item | Description | Maturity (1-5) | Notes |
|------|-------------|----------------|-------|
| Content Safety Filters | Input/output filtering for harmful, biased, or policy-violating content | | |
| Data Privacy in AI Pipelines | PII detection, data anonymization, no-training guarantees | | |
| Model Bias Assessment | Testing for demographic, geographic, and domain bias | | |
| Responsible AI Policy | Documented principles for ethical AI use in product | | |
| AI Transparency | Explainability features for AI-driven decisions | | |
| Regulatory Compliance (AI Act, etc.) | Awareness and compliance with emerging AI regulation | | |
| Red-Teaming & Adversarial Testing | Systematic attempts to break AI safety guardrails | | |

### Section 8: AI Security
| Item | Description | Maturity (1-5) | Notes |
|------|-------------|----------------|-------|
| Prompt Injection Defense | Detection and prevention of prompt injection attacks | | |
| Model Access Controls | Authentication and authorization for AI endpoints | | |
| Data Poisoning Prevention | Protecting training/fine-tuning data integrity | | |
| API Key Management | Secure storage and rotation of LLM API credentials | | |
| Sensitive Data Leakage Prevention | Ensuring PII/confidential data doesn't appear in AI outputs | | |

---

## How To Fill From User Input

Ask the user:
1. **AI Use Cases**: "What are the top AI/agentic use cases in your product?"
2. **Models Used**: "Which LLMs or AI models do you use? (GPT-4, Claude, Gemini, open source?)"
3. **Agentic Components**: "Do you have autonomous agents? What can they do?"
4. **Current AI Challenges**: "What are your biggest AI quality or cost challenges?"
5. **AI Maturity**: "How mature is your AI evaluation and observability practice?"

Use answers to:
- Score items with context-specific maturity ratings
- Add notes explaining the specific architecture and gaps
- Flag critical gaps (score ≤2) with recommended actions

---

## AI Maturity Benchmarks by Company Phase

### MVP/Early Stage
- Target scores: 2-3 across most sections
- Critical minimums: Safety (3+), Cost Attribution (2+), Basic Evals (2+)

### Growth Stage
- Target scores: 3-4
- Critical minimums: Observability (3+), Evals (3+), Cost Management (3+)

### Enterprise/Scale
- Target scores: 4-5
- Critical minimums: All safety sections (4+), Compliance (4+), Full observability (4+)

---

## Output Validation Checklist
- [ ] All 8 sections present
- [ ] Every item has a maturity score and product-specific note
- [ ] AI use cases from user input are referenced in notes
- [ ] Model names/frameworks from user input are called out specifically
- [ ] Safety and compliance sections completed (never skipped)
- [ ] Summary row at bottom: =AVERAGE of all scores
- [ ] Gap analysis: items ≤2 flagged with "⚠️ ACTION REQUIRED: [specific recommendation]"
