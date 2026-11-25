# Survey Notes

[← Back to Awesome-Medical-Agents](../README.md)

This page collects background and deployment material from the [medical agents survey](https://arxiv.org/abs/2607.11175). The survey methodology describes the original review; the README also tracks later releases.

## What are Medical Agents?

In the context of clinical AI, a **medical agent** is a computational system that moves beyond static, single-pass inference to interact dynamically with clinical environments. Unlike traditional foundation models that map inputs to outputs, agents actively decompose complex clinical tasks, invoke specialized tools, maintain contextual memory, and iteratively refine their decisions based on intermediate feedback.

A medical agent is formally defined as $\mathcal{A} = (\mathcal{P}, \mathcal{R}, \mathcal{L}, \mathcal{M}, \mathcal{T}, \mathcal{F})$, composed of six functional modules:

| Module | Function | Clinical Role |
|---|---|---|
| **Perception** $\mathcal{P}$ | Visual feature extraction from medical images | Sensory interface to raw clinical data |
| **Reasoning** $\mathcal{R}$ | Structured clinical thinking (CoT, differential diagnosis) | Diagnostic accuracy and explainability |
| **Planning** $\mathcal{L}$ | Task decomposition into executable sub-tasks | Efficient multistep workflow execution |
| **Memory** $\mathcal{M}$ | Short-term + long-term information storage and retrieval | Contextual continuity across encounters |
| **Tool Use** $\mathcal{T}$ | Invocation of external specialist models and databases | Extended capabilities beyond intrinsic knowledge |
| **Action Reflection** $\mathcal{F}$ | Self-evaluation and iterative improvement | Error correction and quality assurance |

## Why Agents Matter Now

This repository follows the survey **The Path to Self-Evolving Clinical Systems: Scaling Medical Agents from Assistance to Autonomy**. Its organizing principle is deployment-first: before an agent can be trusted in practice, it must handle real clinical scenarios, contamination-resistant benchmarks, and interactive training environments.

The transition from passive models to autonomous agents is driven by four converging factors:

| Factor | Why it matters |
|---|---|
| **Multimodal LLM maturation** | GPT-4V, Med-Gemini, LLaVA-Med provide powerful reasoning backbones that jointly process images and text |
| **Standardized tool interfaces** | MCP and function-calling APIs enable seamless orchestration of diverse specialist models |
| **Environment scaling** | Agent capability can be amplified by enriching the tool environment, complementing parameter scaling |
| **Clinical workflow demand** | Real consultations require multistep reasoning (read scan → cross-reference → report → flag follow-up) |

```text
🏥 Clinical Need → 🧠 Agent Reasoning → 🔧 Tool Orchestration → 📋 Report & Action → 🔁 Self-Reflection
```

## Three-Level Autonomy Taxonomy

| Level | Name | Description | Representative |
|---|---|---|---|
| **L1** | Assisted | Agent enhances clinician efficiency; all decisions require confirmation | CheXagent, MedSAM |
| **L2** | Cooperative | Agent proactively decomposes tasks within human-in-the-loop framework | MDAgents, MedAgent-Pro |
| **L3** | Fully Autonomous | End-to-end workflows with minimal oversight and exception-based escalation | RadAgent, Agent Hospital |

## Scaling Spine

Following the survey, we organize the field around a single **scaling spine**:

| Axis | Focus | Why it matters |
|---|---|---|
| **Framework Scaling** | Architecture paradigms, tool orchestration, and multi-agent topologies | Determines how agents coordinate reasoning and action |
| **Capability Scaling** | The harness-driven loop from perception to action | Turns isolated modules into closed clinical workflows |
| **Environment Scaling** | Rich tool, data, PACS, EHR, FHIR, and clinical gym ecosystems | Expands what agents can do without relying only on larger models |

The long-term destination is **clinical self-evolution**: agents that improve through interaction with environments, consolidate successful workflows, and adapt to new clinical distributions under rigorous governance.

## Survey Scope and Methodology

| Item | Scope |
|---|---|
| **Time window** | January 2022 to June 2026, covering the period in which LLM-driven agency became technically feasible for medical imaging and clinical workflows |
| **Search axes** | Agentic AI (`agent`, `agentic`, `tool use`, `multi-agent`, `autonomous`), medical imaging (`radiology`, `pathology`, `CT`, `MRI`, `X-ray`, `report generation`), and foundation models (`LLM`, `VLM`, `vision-language`) |
| **Screening scale** | 1,174 initial records, 942 after de-duplication, and 300+ included studies after reviewer screening and snowballing |
| **Inclusion criterion** | Systems with an autonomous loop that can perceive, reason, and act on an imaging or clinical task |
| **Scope boundary** | EHR and therapeutic agents are included when they provide reusable architectural lessons for imaging agents, such as tool use, code execution, memory, safety, or downstream care handoff |

## Paradigm Shift: Foundation Models → Agent Systems

| Characteristic | Foundation Models | Agent Systems |
|---|---|---|
| Task scope | Multitask, transferable | Multistep workflows |
| Reasoning | Implicit (in weights) | Explicit (CoT, tree search) |
| Tool integration | Limited (end-to-end) | Native (MCP, function calls) |
| Interaction | One-shot or few-shot | Multi-turn, iterative |
| Self-improvement | Limited | Reflection, self-play |
| Scaling axes | Parameter scaling | Parameter + inference-time + environment scaling |

## Evaluation Metrics Beyond Accuracy

| Dimension | What it measures | Why it matters |
|---|---|---|
| **Reasoning quality** | Coherence and clinical validity of reasoning traces | Explainability and clinician trust |
| **Efficiency** | Tool invocations, reasoning steps, latency | Clinical feasibility |
| **Robustness** | Performance across demographics and edge cases | Equitable healthcare delivery |
| **Safety** | Hallucination rate, false positive severity | Patient safety |
| **User experience** | Empathy, comprehensibility, actionability | Clinician adoption |

## Deployment and Governance

### Industry Deployment Landscape

| Organization | Domain | Key System |
|---|---|---|
| Google Health | Multi-domain | Med-Gemini |
| Microsoft | Multi-domain | Dragon Copilot |
| Rad AI | Radiology | Report generation agents |
| Aidoc | Radiology | Critical finding triage |
| Qure.ai | Radiology | CXR/CT reading agents |
| GE Healthcare | Radiology | MCP workflow agents |
| PathAI | Pathology | WSI analysis agents |

### Interoperability Standards

| Standard | Role |
|---|---|
| **DICOM** | Universal medical image storage/transmission |
| **HL7 FHIR** | Structured clinical data exchange |
| **MCP** | Agent–tool orchestration middleware |

### Agent Protocol Stack

| Layer | Protocol / Pattern | Role in Medical Agents | Representative Direction |
|---|---|---|---|
| Data layer | DICOM | Imaging storage, retrieval, viewer integration, and audit trail compatibility | PACS-native radiology/pathology workflows |
| Data layer | HL7 FHIR | Structured clinical records, orders, medications, observations, and care plans | EHR-grounded agents and virtual EHR benchmarks |
| Tool layer | MCP | Uniform exposure of tools, databases, calculators, viewers, and APIs to agents | Environment scaling and hospital tool registries |
| Clinical bridge | MCP-FHIR | Direct binding between agent tool calls and FHIR resources | Decision support over structured EHR |
| Agent layer | A2A / ANP / ACP | Delegation and negotiation among independent agents | Multi-agent consultation and cross-system handoff |
| Execution layer | Code-as-action | Sandboxed SQL/Python/viewer commands for auditable computation | EHRAgent, MedOpenCLAW, ABRA-style workflows |

### Regulatory Pathways

| Jurisdiction | Framework | Key Challenge for Agents |
|---|---|---|
| FDA (US) | SaMD + AI/ML Action Plan + Predetermined Change Control Plans (PCCPs) | Validating multistep reasoning and controlled post-deployment updates |
| EU | MDR / IVDR + AI Act (High-Risk) | Explainability, accountability, and high-risk AI obligations |
| NMPA (China) | Adapting for agent-based systems | Integration complexity |

### Deployment Pillars

| Pillar | What Must Work | Why It Matters |
|---|---|---|
| Productization | Reliable UI integration, latency budgets, monitoring, fallback paths | Hospitals buy workflow reliability, not only model accuracy |
| Interoperability | DICOM/FHIR compatibility, MCP tool exposure, substitutable agents | Prevents one-off integrations and vendor lock-in |
| Governance | Audit logs, model update controls, human escalation, liability boundaries | Makes adaptive and self-evolving agents reviewable |

## Open Challenges and Future Directions

### Open Challenges

| Challenge | Manifestation | Mitigation Direction | Maturity |
|---|---|---|---|
| **Hallucination** | Visual fabrication, reasoning confabulation | Grounding, RAG, cross-agent verification | Early research |
| **Cascade failures** | Error propagation in multiagent pipelines | Circuit breakers, redundant paths, audits | Nascent |
| **3D/video gap** | Poor volumetric reasoning | 3D tokenization, agentic 3D pipelines | Active research |
| **Computational cost** | High latency multistep reasoning | Distillation, small tool models, test-time scaling | Moderate |
| **Fairness/privacy** | Demographic bias, MCP security risks | Federated agents, differential privacy | Early stage |

### Future Roadmap

| Horizon | Direction | Expected Impact |
|---|---|---|
| **Near-term (1–2 yr)** | Standardized evaluation; hallucination detection; environment scaling via MCP; human–agent interaction | Reproducible comparison, clinical safety |
| **Medium-term (2–5 yr)** | Native 3D/4D agents; longitudinal patient modeling; federated agents; regulatory maturation | Comprehensive interpretation, equitable agents |
| **Long-term (5–10 yr)** | Embodied clinical agents; autonomous screening; precision medicine; self-evolving ecosystems | Autonomous procedures, universal access |

## Survey Assets

- [Taxonomy figure](../figures/fig2_taxonomy_16_931.png)
- [Scaling curves (PDF)](../figures/fig_scaling_curves.pdf)
- [Roadmap figure (PDF)](../figures/fig10_roadmap_16_9.pdf)
