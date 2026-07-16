<h1 align="center">Awesome-Medical-Agents</h1>

<p align="center">
  <a href="https://arxiv.org/pdf/2607.11175v1"><img src="https://img.shields.io/badge/Survey%20Paper-arXiv-blue" alt="Survey Paper"></a>
  <a href="https://github.com/sindresorhus/awesome"><img src="https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg" alt="Awesome"></a>
  <a href="https://GitHub.com/Naereen/StrapDown.js/graphs/commit-activity"><img src="https://img.shields.io/badge/Maintained%3F-yes-green.svg" alt="Maintenance"></a>
  <a href="http://makeapullrequest.com"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat" alt="PRs Welcome"></a>
</p>

<p align="center">
  A curated reading list on <b>medical agents: scaling clinical systems from assistance to autonomy</b>.
  <br>
  Medical agents integrate perception, reasoning, planning, memory, tool use, and self-reflection into trustworthy clinical workflows.
</p>

<p align="center">
  <img src="figures/首页图.png" alt="Survey overview: scaling medical agents from assistance to autonomy" width="720">
</p>

---

<p align="center">
  <a href="#what-are-medical-agents">What are Medical Agents?</a> ·
  <a href="#why-agents-matter-now">Why Agents Matter Now?</a> ·
  <a href="#repository-map">Repository Map</a> ·
  <a href="#table-of-contents">Table of Contents</a>
</p>

Papers with publicly released code or project resources include an inline `[[Code](...)]` link. Entries without verified repositories omit that link. All arXiv IDs and repository URLs in this list have been verified to resolve to the correct paper or code.

> Contributions are welcome. If you find missing papers, inaccurate classifications, or newly released code, feel free to update this list.

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

## Paradigm Shift: Foundation Models → Agent Systems

| Characteristic | Foundation Models | Agent Systems |
|---|---|---|
| Task scope | Multitask, transferable | Multistep workflows |
| Reasoning | Implicit (in weights) | Explicit (CoT, tree search) |
| Tool integration | Limited (end-to-end) | Native (MCP, function calls) |
| Interaction | One-shot or few-shot | Multi-turn, iterative |
| Self-improvement | Limited | Reflection, self-play |
| Scaling axes | Parameter scaling | Parameter + inference-time + environment scaling |

## Repository Map

This repository is organized as a **conceptual map** of medical agent research. We group papers by their role in the agent pipeline.

| Section | Role in the repository |
|---|---|
| **Core Capabilities** | Six functional modules: perception, reasoning, planning, memory, tool use, and reflection |
| **Architecture Paradigms** | Single-agent, multi-agent, code-generation, and hybrid designs |
| **Training Strategies** | Prompting, SFT, preference optimization, RLVR/GRPO, self-play, and scaling |
| **Clinical Applications** | Radiology, pathology, ophthalmology, oncology, neurology, and crossmodal |
| **Benchmarks & Evaluation** | Static, sequential, and system-level evaluation frameworks |
| **Deployment & Governance** | Clinical integration, interoperability standards, and regulatory pathways |

Overall, this structure follows the lifecycle of a medical agent:

**Perceive → Reason → Plan → Remember → Use Tools → Reflect → Deploy**


## Table of Contents

<details open>
<summary>Browse the reading list</summary>

- [Core Capability Modules](#core-capability-modules)
  - [Perception](#perception)
  - [Reasoning](#reasoning)
  - [Planning](#planning)
  - [Memory](#memory)
  - [Tool Use](#tool-use)
  - [Action Reflection](#action-reflection)
- [Architecture Paradigms](#architecture-paradigms)
  - [Single-Agent Tool-Augmented](#single-agent-tool-augmented)
  - [Multi-Agent Role-Based](#multi-agent-role-based)
  - [Code Generation](#code-generation)
  - [Hybrid Architectures](#hybrid-architectures)
- [Training Strategies and Scaling](#training-strategies-and-scaling)
  - [Prompting and In-Context Learning](#prompting-and-in-context-learning)
  - [Supervised Fine-Tuning](#supervised-fine-tuning)
  - [Preference Optimization](#preference-optimization)
  - [RLVR and GRPO](#rlvr-and-grpo)
  - [Self-Play and Continual Improvement](#self-play-and-continual-improvement)
  - [Environment Scaling](#environment-scaling)
- [Clinical Applications](#clinical-applications)
  - [Radiology](#radiology)
  - [Pathology](#pathology)
  - [Ophthalmology](#ophthalmology)
  - [Oncology and Neurology](#oncology-and-neurology)
  - [Crossmodal and Cross-Specialty](#crossmodal-and-cross-specialty)
  - [Pharmacy and Clinical Decision](#pharmacy-and-clinical-decision)
  - [Agent-Driven AutoML](#agent-driven-automl)
- [Benchmarks and Evaluation](#benchmarks-and-evaluation)
  - [Agent-Specific Benchmarks](#agent-specific-benchmarks)
  - [Evaluation Metrics Beyond Accuracy](#evaluation-metrics-beyond-accuracy)
- [Deployment and Governance](#deployment-and-governance)
- [Open Challenges and Future Directions](#open-challenges-and-future-directions)

</details>

---

> Papers with publicly released code are marked with 🌟.

## Core Capability Modules

| Module | Year | Venue | Title / Method | Paper | Code / Data | Tags |
|---|---:|---|---|---|---|---|
| Perception | 2023 | NeurIPS | LLaVA-Med: Training a Large Language-and-Vision Assistant for Biomedicine | [Paper](https://arxiv.org/abs/2306.00890) | [Code](https://github.com/microsoft/LLaVA-Med) | Medical VLM, VQA |
| Perception | 2024 | arXiv | CheXagent: Towards a Foundation Model for Chest X-Ray Interpretation | [Paper](https://arxiv.org/abs/2401.12208) | [Code](https://github.com/Stanford-AIMI/CheXagent) | CXR, report understanding |
| Perception | 2024 | Nature Methods | MedSAM: Segment Anything in Medical Images | [Paper](https://www.nature.com/articles/s41592-024-02260-z) | [Code](https://github.com/bowang-lab/MedSAM) | Segmentation, grounding |
| Perception | 2025 | arXiv | MedRAX: Medical Reasoning Agent for Chest X-ray | [Paper](https://arxiv.org/abs/2502.02673) | [Code](https://github.com/bowang-lab/MedRAX) | Tool use, CXR |
| Reasoning | 2024 | NeurIPS | MDAgents: An Adaptive Collaboration of LLMs for Medical Decision-Making | [Paper](https://arxiv.org/abs/2404.15155) | [Code](https://github.com/mitmedialab/MDAgents) | Multi-agent, diagnosis |
| Reasoning | 2024 | arXiv | MedAgents: Large Language Models as Collaborators for Zero-shot Medical Reasoning | [Paper](https://arxiv.org/abs/2311.10537) | [Code](https://github.com/gersteinlab/MedAgents) | Multi-agent, reasoning |
| Reasoning | 2025 | arXiv | MedReason: Medical Reasoning with Knowledge Graph Grounding | [Paper](https://arxiv.org/abs/2504.00993) | [Code](https://github.com/UCSC-VLAA/MedReason) | KG, reasoning chains |
| Planning | 2025 | arXiv | MedAgent-Pro: Evidence-based Multi-modal Medical Diagnosis via Multi-agent Collaboration | [Paper](https://arxiv.org/abs/2503.18968) | [Code](https://github.com/jinlab-imvr/MedAgent-Pro) | Planning, evidence |
| Planning | 2025 | arXiv | MDTeamGPT: Self-evolving Multi-agent Framework for MDT Medical Consultation | [Paper](https://arxiv.org/abs/2503.13856) | - | MDT, consultation |
| Memory | 2026 | arXiv | ClinicalAgents: Clinical Trial Multi-Agent System with Longitudinal Memory | [Paper](https://arxiv.org/abs/2601.01170) | - | Memory, clinical trials |
| Tool Use | 2024 | EMNLP | EHRAgent: Code-empowered Tabular Reasoning on EHRs | [Paper](https://arxiv.org/abs/2401.07128) | [Code](https://github.com/wshi83/EhrAgent) | EHR, code-as-action |
| Tool Use | 2026 | arXiv | ABRA: Agentic Benchmark for Radiology Assistant | [Paper](https://arxiv.org/abs/2605.11224) | [Code](https://github.com/Luab/ABRA) | OHIF, Orthanc, tools |
| Environment Scaling | 2026 | arXiv | EnvScaler: Scaling Tool-Interactive Environments for Agents | [Paper](https://arxiv.org/abs/2601.05808) | [Code](https://github.com/RUC-NLPIR/EnvScaler) | Tool environment, scaling |
| Reflection / Audit | 2025 | arXiv | MedAgentAudit: Auditing Collaborative Failure Modes in Medical Multi-Agent Systems | [Paper](https://arxiv.org/abs/2510.10185) | [Code](https://github.com/MedX-PKU/MedAgentAudit) | Safety, audit |
| Self-Improvement | 2026 | arXiv | Evo-MedAgent: Evolutionary Agent Self-Improvement | [Paper](https://arxiv.org/abs/2604.14475) | - | Evolution, self-improvement |

<!-- Original bullet-style core capability reading list retained for reference during table conversion.

### Perception
> Visual encoders, multiscale processing, and visual tokenization for bridging continuous image features with discrete LLM token spaces.

#### 2025
- 🌟 [[NeurIPS 2025](https://arxiv.org/abs/2510.20639)] BTB3D: Better Tokens for Better 3D Vision-Language Modeling in Medical Imaging [[Code](https://github.com/ibrahimethemhamamci/BTB3D)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Perception&color=5F6F89&style=flat-square" alt="Perception"> <img src="https://img.shields.io/static/v1?label=&message=3D&color=4F6F73&style=flat-square" alt="3D">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2502.03333)] RadVLM: Multitask Conversational Vision-Language Model for Radiology [[Code](https://github.com/uzh-dqbm-cmi/RadVLM)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Perception&color=5F6F89&style=flat-square" alt="Perception"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">

#### 2024
- 🌟 [[arXiv 2024](https://arxiv.org/abs/2401.10815)] RAD-DINO: Scalable Medical Image Encoders Beyond Text Supervision [[Code](https://huggingface.co/microsoft/rad-dino)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Perception&color=5F6F89&style=flat-square" alt="Perception"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">
- 🌟 [[Nature Medicine 2024](https://arxiv.org/abs/2307.12914)] CONCH: A Visual-Language Foundation Model for Computational Pathology [[Code](https://github.com/mahmoodlab/CONCH)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Perception&color=5F6F89&style=flat-square" alt="Perception"> <img src="https://img.shields.io/static/v1?label=&message=Pathology&color=9B6B6B&style=flat-square" alt="Pathology">
- 🌟 [[CVPR 2024](https://arxiv.org/abs/2312.14238)] InternVL: Scaling Vision Foundation Models [[Code](https://github.com/OpenGVLab/InternVL)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Perception&color=5F6F89&style=flat-square" alt="Perception"> <img src="https://img.shields.io/static/v1?label=&message=Foundation&color=9A8A58&style=flat-square" alt="Foundation">

#### 2023
- 🌟 [[NeurIPS 2023](https://arxiv.org/abs/2306.00890)] LLaVA-Med: Training a Large Language-and-Vision Assistant for Biomedicine [[Code](https://github.com/microsoft/LLaVA-Med)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Perception&color=5F6F89&style=flat-square" alt="Perception"> <img src="https://img.shields.io/static/v1?label=&message=Foundation&color=9A8A58&style=flat-square" alt="Foundation">
- 🌟 [[arXiv 2023](https://arxiv.org/abs/2303.00915)] BiomedCLIP: Biomedical Contrastive Vision-Language Pretraining on 15M Pairs [[Code](https://huggingface.co/microsoft/BiomedCLIP-PubMedBERT_256-vit_base_patch16_224)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Perception&color=5F6F89&style=flat-square" alt="Perception"> <img src="https://img.shields.io/static/v1?label=&message=Foundation&color=9A8A58&style=flat-square" alt="Foundation">

### Reasoning
> Chain-of-thought, differential diagnosis, tree search, causal reasoning, and verification chains for clinical decision-making.

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2603.26182)] ClinicalAgents: Multi-Agent Orchestration with Dual-Memory for Clinical Decision Making <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning"> <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent">
- [[arXiv 2026](https://arxiv.org/abs/2603.01607)] CARE: Evidence-Grounded Agentic Reasoning for Medical VQA <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning"> <img src="https://img.shields.io/static/v1?label=&message=VQA&color=5F8791&style=flat-square" alt="VQA">

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2509.20067)] MACD: Multi-Agent Clinical Diagnosis with Self-Learned Knowledge for LLMs [[Code](https://github.com/qjdzj/MACD-Multi-Agent-Clinical-Diagnosis-with-Self-Learned-Knowledge-for-LLM)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning"> <img src="https://img.shields.io/static/v1?label=&message=Knowledge&color=4F6F73&style=flat-square" alt="Knowledge">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2502.19175)] MEDDxAgent: Unified Framework for Explainable Differential Diagnosis [[Code](https://github.com/nec-research/meddxagent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning"> <img src="https://img.shields.io/static/v1?label=&message=Diagnosis&color=6B8F8F&style=flat-square" alt="Diagnosis">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2502.19634)] MedVLM-R1: Incentivizing Medical Reasoning via Reinforcement Learning [[Code](https://github.com/JZPeterPan/MedVLM-R1)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning"> <img src="https://img.shields.io/static/v1?label=&message=RLVR&color=9A8A58&style=flat-square" alt="RLVR">

#### 2024
- 🌟 [[NeurIPS 2024](https://arxiv.org/abs/2404.15155)] MDAgents: Adaptive Multi-Agent Collaboration for Medical Decisions [[Code](https://github.com/mitmedialab/MDAgents)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning"> <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent">
- [[arXiv 2024](https://arxiv.org/abs/2404.18416)] Med-Gemini: Capabilities of Gemini Models in Medicine <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning"> <img src="https://img.shields.io/static/v1?label=&message=Foundation&color=9A8A58&style=flat-square" alt="Foundation">

### Planning
> ReAct, Plan-and-Solve, hierarchical decomposition, and adaptive tool discovery for multistep clinical workflows.

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2603.24649)] MedOpenClaw: Auditable VLM Agent for 3D Slicer Clinical Operations <br>
  <img src="https://img.shields.io/static/v1?label=&message=Planning&color=806F95&style=flat-square" alt="Planning"> <img src="https://img.shields.io/static/v1?label=&message=3D&color=4F6F73&style=flat-square" alt="3D">
- [[arXiv 2026](https://arxiv.org/abs/2603.05860)] MACRO: Evolving Medical Imaging Agents via Experience-Driven Self-Skill Discovery <br>
  <img src="https://img.shields.io/static/v1?label=&message=Planning&color=806F95&style=flat-square" alt="Planning"> <img src="https://img.shields.io/static/v1?label=&message=Tool%20Discovery&color=9A7F55&style=flat-square" alt="Tool Discovery">

#### 2025
- 🌟 [[ICML 2025](https://arxiv.org/abs/2502.02673)] MedRAX: Multimodal Reasoning Agent with Tool Orchestration for CXR [[Code](https://github.com/bowang-lab/MedRAX)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Planning&color=806F95&style=flat-square" alt="Planning"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">
- 🌟 [[ICLR 2026](https://arxiv.org/abs/2503.18968)] MedAgent-Pro: Evidence-Based Multimodal Medical Diagnosis via Reasoning Workflows [[Code](https://github.com/jinlab-imvr/MedAgent-Pro)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Planning&color=806F95&style=flat-square" alt="Planning"> <img src="https://img.shields.io/static/v1?label=&message=Evidence&color=6F8F72&style=flat-square" alt="Evidence">

### Memory
> Dual-layer architectures (working + episodic), RAG, agentic memory management, and knowledge-graph grounded data synthesis.

#### 2025
- 🌟 [[NeurIPS 2025](https://arxiv.org/abs/2502.12110)] A-MEM: Agentic Memory for LLM Agents [[Code](https://github.com/agiresearch/A-mem)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Memory&color=9B6B6B&style=flat-square" alt="Memory"> <img src="https://img.shields.io/static/v1?label=&message=Agentic&color=7B6F86&style=flat-square" alt="Agentic">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2504.00993)] MedReason: Eliciting Factual Medical Reasoning Steps via Knowledge Graphs [[Code](https://github.com/UCSC-VLAA/MedReason)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Memory&color=9B6B6B&style=flat-square" alt="Memory"> <img src="https://img.shields.io/static/v1?label=&message=Knowledge%20Graph&color=9A8A58&style=flat-square" alt="Knowledge Graph">

#### 2024
- 🌟 [[EMNLP 2024](https://arxiv.org/abs/2407.05131)] RULE: Reliable Multimodal RAG for Factuality in Medical VLMs [[Code](https://github.com/richard-peng-xia/RULE)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Memory&color=9B6B6B&style=flat-square" alt="Memory"> <img src="https://img.shields.io/static/v1?label=&message=RAG&color=6F8F72&style=flat-square" alt="RAG">

### Tool Use
> MCP integration, function calling, environment scaling, tool selection/composition, and tool discovery mechanisms.

#### 2026
- 🌟 [[arXiv 2026](https://arxiv.org/abs/2601.05808)] EnvScaler: Scaling Tool-Interactive Environments for Agents [[Code](https://github.com/RUC-NLPIR/EnvScaler)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Tool%20Use&color=5F8791&style=flat-square" alt="Tool Use"> <img src="https://img.shields.io/static/v1?label=&message=Environment%20Scaling&color=6B7280&style=flat-square" alt="Environment Scaling">

#### 2025
- 🌟 [[ACL 2025](https://arxiv.org/abs/2410.17657)] ReflecTool: Towards Reflection-Aware Tool-Augmented Clinical Agents [[Code](https://github.com/BlueZeros/ReflecTool)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Tool%20Use&color=5F8791&style=flat-square" alt="Tool Use"> <img src="https://img.shields.io/static/v1?label=&message=Reflection&color=806F95&style=flat-square" alt="Reflection">

#### 2023
- 🌟 [[ICLR 2024](https://arxiv.org/abs/2307.16789)] ToolLLM: Mastering 16,000+ Real-World APIs [[Code](https://github.com/OpenBMB/ToolBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Tool%20Use&color=5F8791&style=flat-square" alt="Tool Use"> <img src="https://img.shields.io/static/v1?label=&message=Foundation&color=9A8A58&style=flat-square" alt="Foundation">

### Action Reflection
> Reflexion, Self-Refine, cross-agent verification, and evolutionary self-improvement mechanisms.

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2604.14475)] Evo-MedAgent: Beyond One-Shot Diagnosis via Iterative Agent Self-Improvement <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reflection&color=806F95&style=flat-square" alt="Reflection"> <img src="https://img.shields.io/static/v1?label=&message=Self-Play&color=8A735F&style=flat-square" alt="Self-Play">

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2510.10185)] MedAgentAudit: Auditing Collaborative Failure Modes in Medical Multi-Agent Systems [[Code](https://github.com/MedX-PKU/MedAgentAudit)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reflection&color=806F95&style=flat-square" alt="Reflection"> <img src="https://img.shields.io/static/v1?label=&message=Safety&color=9A6F7F&style=flat-square" alt="Safety">

---

-->

## Architecture Paradigms

| Family | Year | Venue | Title / Method | Paper | Code / Data | Tags |
|---|---:|---|---|---|---|---|
| Single-agent tool-augmented | 2024 | arXiv | CheXagent: Foundation Model for Chest X-Ray Interpretation | [Paper](https://arxiv.org/abs/2401.12208) | [Code](https://github.com/Stanford-AIMI/CheXagent) | Single agent, CXR |
| Single-agent tool-augmented | 2025 | arXiv | MedRAX: Medical Reasoning Agent for Chest X-ray | [Paper](https://arxiv.org/abs/2502.02673) | [Code](https://github.com/bowang-lab/MedRAX) | Tools, reporting |
| Single-agent tool-augmented | 2024 | arXiv | MMedAgent: Learning to Use Medical Tools | [Paper](https://arxiv.org/abs/2407.02483) | - | Tool routing |
| Code-as-action | 2024 | EMNLP | EHRAgent: Code-empowered EHR Reasoning | [Paper](https://arxiv.org/abs/2401.07128) | [Code](https://github.com/wshi83/EhrAgent) | EHR, code execution |
| Code-as-action | 2026 | arXiv | MedOpenCLAW / MedFlowBench: Auditing Medical Imaging Workflow Agents | [Paper](https://arxiv.org/abs/2603.24649) | - | 3D Slicer, QuPath |
| Role-based multi-agent | 2024 | NeurIPS | MDAgents: Adaptive Collaboration of LLMs for Medical Decision-Making | [Paper](https://arxiv.org/abs/2404.15155) | [Code](https://github.com/mitmedialab/MDAgents) | Multi-agent, panel |
| Role-based multi-agent | 2024 | arXiv | MedAgents: LLM Collaborators for Medical Reasoning | [Paper](https://arxiv.org/abs/2311.10537) | [Code](https://github.com/gersteinlab/MedAgents) | Role play, debate |
| Role-based multi-agent | 2025 | arXiv | MDTeamGPT: Multi-disciplinary Team Medical Consultation | [Paper](https://arxiv.org/abs/2503.13856) | - | MDT, consultation |
| Dynamic topology | 2024 | ICML | GPTSwarm: Language Agents as Optimizable Graphs | [Paper](https://arxiv.org/abs/2402.16823) | [Code](https://github.com/metauto-ai/GPTSwarm) | Topology search |
| Dynamic topology | 2023 | arXiv | DyLAN: Dynamic LLM-Agent Network | [Paper](https://arxiv.org/abs/2310.02170) | - | Agent selection |
| Self-evolving architecture | 2026 | arXiv | Evo-MedAgent: Evolutionary Agent Self-Improvement | [Paper](https://arxiv.org/abs/2604.14475) | - | Self-improvement |

<!-- Original bullet-style architecture reading list retained for reference during table conversion.

<p align="center">
  <img src="figures/fig4_architectures_topologies1.png" alt="Architecture paradigms and topologies for medical agents" width="900">
</p>

### Single-Agent Tool-Augmented
> One LLM controller orchestrates a suite of external tools. Benefits directly from environment scaling.

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2603.24649)] MedOpenClaw: Auditable VLM Agent for 3D Slicer Clinical Imaging <br>
  <img src="https://img.shields.io/static/v1?label=&message=Single-Agent&color=5F6F89&style=flat-square" alt="Single-Agent"> <img src="https://img.shields.io/static/v1?label=&message=3D&color=4F6F73&style=flat-square" alt="3D">
- 🌟 [[arXiv 2026](https://arxiv.org/abs/2604.15231)] RadAgent: Autonomous Radiology Workflow Management for CT [[Code](https://github.com/eth-medical-ai-lab/rad-agent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Single-Agent&color=5F6F89&style=flat-square" alt="Single-Agent"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">

#### 2025
- 🌟 [[ICML 2025](https://arxiv.org/abs/2502.02673)] MedRAX: Multimodal Reasoning Agent with Tool Orchestration [[Code](https://github.com/bowang-lab/MedRAX)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Single-Agent&color=5F6F89&style=flat-square" alt="Single-Agent"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">

#### 2024
- 🌟 [[arXiv 2024](https://arxiv.org/abs/2401.12208)] CheXagent: Foundation Model for Chest X-Ray Interpretation [[Code](https://github.com/Stanford-AIMI/CheXagent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Single-Agent&color=5F6F89&style=flat-square" alt="Single-Agent"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">

### Multi-Agent Role-Based
> Multiple specialized agents collaborate, mirroring clinical division of labor (Resident–Fellow–Attending, multidisciplinary teams).

#### 2026
- [[ACL 2026](https://arxiv.org/abs/2604.16175)] MARCH: Multi-Agent Radiology Clinical Hierarchy for CT Report Generation <br>
  <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">
- [[arXiv 2026](https://arxiv.org/abs/2603.26182)] ClinicalAgents: Multi-Agent Orchestration with Dual-Memory <br>
  <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent"> <img src="https://img.shields.io/static/v1?label=&message=Orchestration&color=6F8F72&style=flat-square" alt="Orchestration">

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2503.13856)] MDTeamGPT: Self-Evolving Multidisciplinary Team Consultation [[Code](https://github.com/KaiChenNJ/MDTeamGPT)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent"> <img src="https://img.shields.io/static/v1?label=&message=Self-Evolving&color=8A735F&style=flat-square" alt="Self-Evolving">

#### 2024
- 🌟 [[NeurIPS 2024](https://arxiv.org/abs/2404.15155)] MDAgents: Adaptive Multi-Agent Medical Collaboration [[Code](https://github.com/mitmedialab/MDAgents)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent"> <img src="https://img.shields.io/static/v1?label=&message=Adaptive&color=6B8F8F&style=flat-square" alt="Adaptive">

### Code Generation
> LLMs produce executable analysis scripts for precise, reproducible, and auditable clinical reasoning.

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2603.24649)] MedOpenClaw: Executable 3D Slicer Commands for Volumetric Analysis <br>
  <img src="https://img.shields.io/static/v1?label=&message=Code%20Gen&color=6B7280&style=flat-square" alt="Code Gen"> <img src="https://img.shields.io/static/v1?label=&message=3D&color=4F6F73&style=flat-square" alt="3D">

#### 2024
- 🌟 [[EMNLP 2024](https://arxiv.org/abs/2401.07128)] EHRAgent: Code-Empowered EHR Reasoning Agent [[Code](https://github.com/wshi83/EhrAgent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Code%20Gen&color=6B7280&style=flat-square" alt="Code Gen"> <img src="https://img.shields.io/static/v1?label=&message=EHR&color=9A8A58&style=flat-square" alt="EHR">

### Hybrid Architectures
> Combine multiple paradigms for complex real-world clinical deployments.

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2603.05860)] MACRO: Self-Evolving Hybrid Agent with Experience-Driven Tool Discovery <br>
  <img src="https://img.shields.io/static/v1?label=&message=Hybrid&color=9A7F55&style=flat-square" alt="Hybrid"> <img src="https://img.shields.io/static/v1?label=&message=Self-Evolving&color=8A735F&style=flat-square" alt="Self-Evolving">

#### 2024
- [[arXiv 2024](https://arxiv.org/abs/2405.02957)] Agent Hospital: A Simulacrum of Hospital with Evolvable Medical Agents <br>
  <img src="https://img.shields.io/static/v1?label=&message=Hybrid&color=9A7F55&style=flat-square" alt="Hybrid"> <img src="https://img.shields.io/static/v1?label=&message=Simulation&color=5F8791&style=flat-square" alt="Simulation">

---

## Training Strategies and Scaling

<p align="center">
  <img src="figures/fig5_training_16_921.png" alt="Training strategies and scaling paths for medical agents" width="900">
</p>

### Prompting and In-Context Learning

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2604.16729)] Agentic LLMs for Training-Free Neuro-Radiological Image Analysis <br>
  <img src="https://img.shields.io/static/v1?label=&message=Prompting&color=5F6F89&style=flat-square" alt="Prompting"> <img src="https://img.shields.io/static/v1?label=&message=Zero-Shot&color=6B8F8F&style=flat-square" alt="Zero-Shot">

#### 2024
- [[arXiv 2024](https://arxiv.org/abs/2405.02957)] Agent Hospital: MedAgent-Zero Self-Evolution Without Manual Labeling <br>
  <img src="https://img.shields.io/static/v1?label=&message=Prompting&color=5F6F89&style=flat-square" alt="Prompting"> <img src="https://img.shields.io/static/v1?label=&message=Self-Evolving&color=8A735F&style=flat-square" alt="Self-Evolving">

### Supervised Fine-Tuning

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2502.03333)] RadVLM: Multitask Conversational Fine-Tuning for Radiology [[Code](https://github.com/uzh-dqbm-cmi/RadVLM)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=SFT&color=9A7B5F&style=flat-square" alt="SFT"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">

#### 2024
- 🌟 [[arXiv 2024](https://arxiv.org/abs/2401.12208)] CheXagent: Clinical Knowledge Alignment + Finding Extraction + Report Generation [[Code](https://github.com/Stanford-AIMI/CheXagent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=SFT&color=9A7B5F&style=flat-square" alt="SFT"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">

### Preference Optimization

#### 2025
- 🌟 [[CVPR 2025](https://arxiv.org/abs/2501.09695)] OPA-DPO: On-Policy Alignment for Mitigating Hallucination in LVLMs [[Code](https://github.com/zhyang2226/OPA-DPO)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=DPO&color=9B6B6B&style=flat-square" alt="DPO"> <img src="https://img.shields.io/static/v1?label=&message=VLM&color=5F8A75&style=flat-square" alt="VLM">

### RLVR and GRPO

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2512.06581)] MedGRPO: Group Relative Policy Optimization for Medical Video Understanding <br>
  <img src="https://img.shields.io/static/v1?label=&message=RLVR&color=9A8A58&style=flat-square" alt="RLVR"> <img src="https://img.shields.io/static/v1?label=&message=Video&color=5F8A75&style=flat-square" alt="Video">

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2502.19634)] MedVLM-R1: RL-Incentivized Reasoning in Medical VLMs [[Code](https://github.com/JZPeterPan/MedVLM-R1)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=RLVR&color=9A8A58&style=flat-square" alt="RLVR"> <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning">
- 🌟 [[Nature 2025](https://arxiv.org/abs/2501.12948)] DeepSeek-R1: Incentivizing Reasoning in LLMs via Reinforcement Learning [[Code](https://github.com/deepseek-ai/DeepSeek-R1)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=RLVR&color=9A8A58&style=flat-square" alt="RLVR"> <img src="https://img.shields.io/static/v1?label=&message=Foundation&color=9A8A58&style=flat-square" alt="Foundation">

### Self-Play and Continual Improvement

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2604.14475)] Evo-MedAgent: Iterative Self-Improvement Beyond One-Shot Diagnosis <br>
  <img src="https://img.shields.io/static/v1?label=&message=Self-Play&color=8A735F&style=flat-square" alt="Self-Play"> <img src="https://img.shields.io/static/v1?label=&message=Evolution&color=6F8F72&style=flat-square" alt="Evolution">

#### 2024
- [[arXiv 2024](https://arxiv.org/abs/2405.02957)] Agent Hospital: Simulated Training via Synthetic Patient Cases <br>
  <img src="https://img.shields.io/static/v1?label=&message=Self-Play&color=8A735F&style=flat-square" alt="Self-Play"> <img src="https://img.shields.io/static/v1?label=&message=Simulation&color=5F8791&style=flat-square" alt="Simulation">

### Environment Scaling
> Amplifying agent capability by enriching the tool and data environment rather than solely scaling model parameters.

#### 2026
- 🌟 [[arXiv 2026](https://arxiv.org/abs/2601.05808)] EnvScaler: Systematic Expansion of Tool-Interactive Environments [[Code](https://github.com/RUC-NLPIR/EnvScaler)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Env%20Scaling&color=6B7280&style=flat-square" alt="Env Scaling">

#### 2025
- 🌟 [[ICLR 2026](https://arxiv.org/abs/2506.04405)] MedAgentGym: Scalable Agentic Training Environment for Biomedical Data Science [[Code](https://github.com/wshi83/MedAgentGym)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Env%20Scaling&color=6B7280&style=flat-square" alt="Env Scaling"> <img src="https://img.shields.io/static/v1?label=&message=Training&color=9A7B5F&style=flat-square" alt="Training">

---

## Clinical Applications

<p align="center">
  <img src="figures/applications.png" alt="Clinical application landscape for medical agents" width="900">
</p>

### Radiology

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2603.24649)] MedOpenClaw: Auditable VLM Agent for 3D Slicer <br>
  <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology"> <img src="https://img.shields.io/static/v1?label=&message=3D&color=4F6F73&style=flat-square" alt="3D">
- [[ACL 2026](https://arxiv.org/abs/2604.16175)] MARCH: Multiagent CT Report Generation <br>
  <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology"> <img src="https://img.shields.io/static/v1?label=&message=Report%20Gen&color=6B7280&style=flat-square" alt="Report Gen">
- 🌟 [[arXiv 2026](https://arxiv.org/abs/2604.15231)] RadAgent: Autonomous Radiology Workflow Management [[Code](https://github.com/eth-medical-ai-lab/rad-agent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology"> <img src="https://img.shields.io/static/v1?label=&message=Workflow&color=9A7F55&style=flat-square" alt="Workflow">
- [[arXiv 2026](https://arxiv.org/abs/2604.16729)] Agentic Neuro-Radiology: Training-Free Brain MRI Pipeline <br>
  <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology"> <img src="https://img.shields.io/static/v1?label=&message=Neurology&color=9B6B6B&style=flat-square" alt="Neurology">

#### 2025
- 🌟 [[ICML 2025](https://arxiv.org/abs/2502.02673)] MedRAX: Tool Orchestration for CXR Analysis [[Code](https://github.com/bowang-lab/MedRAX)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology"> <img src="https://img.shields.io/static/v1?label=&message=CXR&color=6B8F8F&style=flat-square" alt="CXR">
- 🌟 [[ICLR 2026](https://arxiv.org/abs/2503.18968)] MedAgent-Pro: Evidence-Based Multimodal Diagnosis [[Code](https://github.com/jinlab-imvr/MedAgent-Pro)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology"> <img src="https://img.shields.io/static/v1?label=&message=Evidence&color=6F8F72&style=flat-square" alt="Evidence">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2510.21324)] CXR-Agent: Automated Chest Radiograph Interpretation [[Code](https://github.com/laojiahuo2003/CXRAgent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology"> <img src="https://img.shields.io/static/v1?label=&message=CXR&color=6B8F8F&style=flat-square" alt="CXR">

### Pathology

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2511.17052)] PathAgent: Navigator-Perceptor-Executor Loop for WSI [[Code](https://github.com/G14nTDo4/PathAgent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Pathology&color=9B6B6B&style=flat-square" alt="Pathology"> <img src="https://img.shields.io/static/v1?label=&message=WSI&color=5F8791&style=flat-square" alt="WSI">
- [[ICCV 2025](https://arxiv.org/abs/2502.08916)] PathFinder: Interactive Multiagent WSI Search <br>
  <img src="https://img.shields.io/static/v1?label=&message=Pathology&color=9B6B6B&style=flat-square" alt="Pathology"> <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent">
- 🌟 [[MICCAI 2025](https://arxiv.org/abs/2507.14680)] WSI-Agents: Collaborative Multiagent WSI Analysis [[Code](https://github.com/CVI-SZU/WSI-Agents)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Pathology&color=9B6B6B&style=flat-square" alt="Pathology"> <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2509.20279)] TissueLab: Agentic Tissue Analysis Environment [[Code](https://github.com/zhihuanglab/TissueLab-SDK)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Pathology&color=9B6B6B&style=flat-square" alt="Pathology"> <img src="https://img.shields.io/static/v1?label=&message=AutoML&color=6B7280&style=flat-square" alt="AutoML">

### Ophthalmology

#### 2025
- [[arXiv 2025](https://arxiv.org/abs/2511.09394)] EyeAgent: 53-Tool Agent Across 23 Imaging Modalities <br>
  <img src="https://img.shields.io/static/v1?label=&message=Ophthalmology&color=9A7682&style=flat-square" alt="Ophthalmology"> <img src="https://img.shields.io/static/v1?label=&message=Env%20Scaling&color=6B7280&style=flat-square" alt="Env Scaling">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2504.13650)] EyecareGPT: Multimodal LLM for Ophthalmic Imaging [[Code](https://github.com/dcdmllm/eyecaregpt)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Ophthalmology&color=9A7682&style=flat-square" alt="Ophthalmology"> <img src="https://img.shields.io/static/v1?label=&message=Multimodal&color=5F8791&style=flat-square" alt="Multimodal">

### Oncology and Neurology

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2604.16729)] Agentic Neuro-Radiology: Brain MRI Pipeline <br>
  <img src="https://img.shields.io/static/v1?label=&message=Neurology&color=9B6B6B&style=flat-square" alt="Neurology">

#### 2025
- [[npj Digital Medicine 2025](https://www.nature.com/articles/s41746-025-01940-4)] CARE-AD: Multiagent Alzheimer's Prediction <br>
  <img src="https://img.shields.io/static/v1?label=&message=Neurology&color=9B6B6B&style=flat-square" alt="Neurology"> <img src="https://img.shields.io/static/v1?label=&message=Longitudinal&color=6B8F8F&style=flat-square" alt="Longitudinal">

#### 2024
- [[arXiv 2024](https://arxiv.org/abs/2409.06351)] MAGDA: Guideline-Driven Diagnostic Assistance <br>
  <img src="https://img.shields.io/static/v1?label=&message=Oncology&color=9A6F7F&style=flat-square" alt="Oncology"> <img src="https://img.shields.io/static/v1?label=&message=Guidelines&color=6F8F72&style=flat-square" alt="Guidelines">

### Crossmodal and Cross-Specialty

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2603.05860)] MACRO: Self-Evolving Crossmodal Agent with Tool Discovery <br>
  <img src="https://img.shields.io/static/v1?label=&message=Crossmodal&color=5F8791&style=flat-square" alt="Crossmodal"> <img src="https://img.shields.io/static/v1?label=&message=Self-Evolving&color=8A735F&style=flat-square" alt="Self-Evolving">

#### 2025
- 🌟 [[ICLR 2026](https://arxiv.org/abs/2503.18968)] MedAgent-Pro: Evidence-Based Multimodal Diagnosis [[Code](https://github.com/jinlab-imvr/MedAgent-Pro)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Crossmodal&color=5F8791&style=flat-square" alt="Crossmodal"> <img src="https://img.shields.io/static/v1?label=&message=Evidence&color=6F8F72&style=flat-square" alt="Evidence">

#### 2024
- 🌟 [[ICLR 2025](https://arxiv.org/abs/2407.02483)] MMedAgent: Learning to Use Medical Tools with Multimodal Agent [[Code](https://github.com/Wangyixinxin/MMedAgent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Crossmodal&color=5F8791&style=flat-square" alt="Crossmodal"> <img src="https://img.shields.io/static/v1?label=&message=Tool%20Library&color=9A8A58&style=flat-square" alt="Tool Library">

### Pharmacy and Clinical Decision

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2503.10970)] TxAgent: Therapeutic Reasoning Agent with Multi-Step Tool Use [[Code](https://github.com/mims-harvard/TxAgent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Pharmacy&color=9A7F55&style=flat-square" alt="Pharmacy"> <img src="https://img.shields.io/static/v1?label=&message=Drug%20Safety&color=9A6F7F&style=flat-square" alt="Drug Safety">

#### 2024
- 🌟 [[MLHC 2024](https://arxiv.org/abs/2408.01869)] MALADE: Multiagent Adverse Drug Event Detection [[Code](https://github.com/jihyechoi77/malade)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Pharmacy&color=9A7F55&style=flat-square" alt="Pharmacy"> <img src="https://img.shields.io/static/v1?label=&message=Safety&color=9A6F7F&style=flat-square" alt="Safety">
- 🌟 [[EMNLP 2024](https://arxiv.org/abs/2401.07128)] EHRAgent: Code-Empowered EHR Reasoning [[Code](https://github.com/wshi83/EhrAgent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Clinical%20Decision&color=6B8F8F&style=flat-square" alt="Clinical Decision"> <img src="https://img.shields.io/static/v1?label=&message=Code%20Gen&color=6B7280&style=flat-square" alt="Code Gen">

### Agent-Driven AutoML

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2604.14475)] Evo-MedAgent: Evolutionary Agent Self-Improvement <br>
  <img src="https://img.shields.io/static/v1?label=&message=AutoML&color=6B7280&style=flat-square" alt="AutoML"> <img src="https://img.shields.io/static/v1?label=&message=Evolution&color=6F8F72&style=flat-square" alt="Evolution">

#### 2025
- 🌟 [[MICCAI 2025](https://arxiv.org/abs/2502.20301)] M3Builder: Automated Medical Model Building via Agent Pipeline [[Code](https://github.com/MAGIC-AI4Med/M3Builder)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=AutoML&color=6B7280&style=flat-square" alt="AutoML"> <img src="https://img.shields.io/static/v1?label=&message=Pipeline&color=5F6F89&style=flat-square" alt="Pipeline">
- 🌟 [[ICLR 2026](https://arxiv.org/abs/2506.04405)] MedAgentGym: Training Gymnasium for Medical Agents [[Code](https://github.com/wshi83/MedAgentGym)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=AutoML&color=6B7280&style=flat-square" alt="AutoML"> <img src="https://img.shields.io/static/v1?label=&message=Training%20Env&color=5F8791&style=flat-square" alt="Training Env">

---

## Method Summary Tables

The detailed reading list above is organized by year and subtopic. For faster scanning, the main method families are summarized below in compact tables.

### Core Capability Methods

| Capability | Representative Methods | Agent Role | Typical Evidence |
|---|---|---|---|
| **Perception** | LLaVA-Med, BiomedCLIP, RAD-DINO, MedSAM, MedRAX | Encodes images, regions, reports, and multimodal clinical inputs | Visual QA, grounding, segmentation, measurement |
| **Reasoning** | CoT, Med-Gemini, MDAgents, MedAgents, MedReason | Performs differential diagnosis, clinical inference, and evidence synthesis | Medical QA, case reasoning, knowledge-graph reasoning |
| **Planning** | ReAct, Plan-and-Solve, MedAgent-Pro, MDTeamGPT | Decomposes complex cases into executable subtasks | Tool chains, diagnostic workflows, team discussion |
| **Memory** | RAG, GraphRAG, ClinicalAgents, longitudinal agent memory | Preserves patient context, prior evidence, and cross-case experience | Retrieval, EHR context, longitudinal follow-up |
| **Tool Use** | Toolformer, HuggingGPT, MedRAX, EHRAgent, ABRA | Invokes calculators, viewers, databases, segmentation tools, and EHR APIs | Function calling, code execution, PACS/EHR interaction |
| **Reflection** | Reflexion, Self-Refine, MedAgentAudit, Evo-MedAgent | Checks errors, audits reasoning, and improves future actions | Self-verification, multi-agent review, failure analysis |

### Architecture Methods

| Architecture Family | Coordination Pattern | Representative Systems | Best Fit |
|---|---|---|---|
| **Single-agent tool-augmented** | One controller routes among tools | CheXagent, MedRAX, MMedAgent, CXR-Agent | Focused imaging tasks with a known toolbox |
| **Code-as-action agent** | Agent writes or executes code against clinical data/tools | EHRAgent, MedOpenCLAW, ABRA | EHR tables, imaging viewers, open-ended tool composition |
| **Role-based multi-agent** | Specialized clinical roles communicate through an orchestrator | MDAgents, MedAgents, MDTeamGPT, M3Builder | Multispecialty reasoning, review, and consensus |
| **Dynamic topology** | Communication graph changes by case difficulty | GPTSwarm, DyLAN, MaAS, dynamic graph agents | Hard or uncertain cases requiring adaptive compute |
| **Self-evolving system** | Agent revises prompts, memory, tools, or workflows over time | Evo-MedAgent, MACRO, TissueLab, self-evolving simulators | Continuous improvement under controlled governance |

### Training and Scaling Methods

| Training / Scaling Strategy | What Changes | Representative Methods | Main Benefit |
|---|---|---|---|
| **Prompting / ICL** | Instructions and examples only | CoT, ReAct, Plan-and-Solve | Fast adaptation without finetuning |
| **Supervised finetuning** | Model parameters trained on demonstrations | LLaVA-Med-style instruction tuning, medical VLM SFT | Better domain alignment and task format following |
| **Preference optimization** | Model behavior aligned to preferred outputs | DPO/RLAIF-style medical alignment | Safer and more clinician-aligned responses |
| **RL / verifiable reward** | Agent optimizes actions with outcome rewards | RLVR, GRPO, MedAgentGym-style training | Stronger multistep reasoning and tool-use reliability |
| **Test-time scaling** | More search, verification, or agent deliberation at inference | Self-consistency, tree/graph search, multi-agent review | Better hard-case performance with controllable cost |
| **Environment scaling** | Tool, data, simulator, and workflow environment expands | MedAgentBench, FHIR-AgentBench, ClinicalLab, ClinEnv | Capability gains without relying only on larger models |

### Clinical Application Methods

| Clinical Area | Main Agent Tasks | Representative Systems | Typical Workflow |
|---|---|---|---|
| **Radiology** | CXR/CT interpretation, report generation, measurement, triage | CheXagent, MedRAX, RadAgent, CXR-Agent, ABRA | Image review → tool calls → findings → report/audit |
| **Pathology** | WSI navigation, region selection, tissue classification, report support | PathAgent, CPathAgent, WSI-Agents, TeamPath, TissueLab | Coarse-to-fine slide search → evidence-grounded diagnosis |
| **Ophthalmology** | Multimodal eye imaging analysis and traceable reasoning | EyeAgent, EyecareGPT, OAAgent, EH-Benchmark | Modality selection → lesion/finding analysis → explanation |
| **Oncology** | Tumor evidence synthesis, guideline support, outcome labeling | MAGDA, RadGPT, RadOnc-GPT, autonomous oncology agents | Imaging + guideline + longitudinal evidence integration |
| **Neurology** | Neuroimaging interpretation, AD assessment, fairness-aware diagnosis | ADAgent, AD-CARE, CARE-AD, NeuroAgent | Multimodal evidence aggregation and longitudinal assessment |
| **Cross-domain care** | Dialogue, EHR search, care pathway automation, administration | AgentClinic, MedAgentBench, ClinicalLab, HealthAgentBench | Patient interaction → EHR/tool execution → decision support |

## Benchmarks and Evaluation

<p align="center">
  <img src="figures/fig7_benchmarks_taxonomy3.png" alt="Benchmark taxonomy for evaluating medical agents" width="900">
</p>

### Agent-Specific Benchmarks

> Three evaluation levels: static single capabilities, tool-augmented and interactive agency, and system-level clinical operation. The catalog below follows the survey's readiness taxonomy and includes paper, data, or code links where available.

#### Level 1: Isolated Single Capabilities

| Year | Benchmark | What it tests | Paper | Data / Code |
|---|---|---|---|---|
| 2018 | VQA-RAD | Clinician-generated radiology VQA | [Paper](https://www.nature.com/articles/sdata2018251) | [Data](https://huggingface.co/datasets/flaviagiammarino/vqa-rad) |
| 2019 | PubMedQA | Biomedical yes/no/maybe reasoning over abstracts | [Paper](https://arxiv.org/abs/1909.06146) | [Data](https://huggingface.co/datasets/qiaojin/PubMedQA) |
| 2020 | PathVQA | Pathology VQA with 32K questions over 5K images | [Paper](https://arxiv.org/abs/2003.10286) | [Data](https://huggingface.co/datasets/flaviagiammarino/path-vqa) |
| 2021 | MedQA | Medical licensing exam QA | [Paper](https://arxiv.org/abs/2009.13081) | [Data](https://huggingface.co/datasets/GBaker/MedQA-USMLE-4-options) |
| 2021 | SLAKE | Bilingual knowledge-enhanced radiology VQA | [Paper](https://arxiv.org/abs/2102.09542) | [Data](https://huggingface.co/datasets/mdwiratathya/SLAKE-vqa-english) |
| 2022 | MedMCQA | Multi-subject medical multiple-choice QA | [Paper](https://arxiv.org/abs/2203.14371) | [Data](https://huggingface.co/datasets/openlifescienceai/medmcqa) |
| 2022 | MS-CXR | Radiologist phrase grounding boxes for CXR | [Paper](https://arxiv.org/abs/2204.09817) | [Data](https://physionet.org/content/ms-cxr) |
| 2023 | ReXVal | Radiologist error annotations for report evaluation | [Paper](https://physionet.org/content/rexval-dataset/1.0.0/) | [Data](https://physionet.org/content/rexval-dataset) |
| 2024 | CheXbench | Chest X-ray perception and report understanding | [Paper](https://arxiv.org/abs/2401.12208) | [Code](https://github.com/Stanford-AIMI/CheXagent) |
| 2024 | OmniMedVQA | Large-scale medical VQA across 12 modalities | [Paper](https://arxiv.org/abs/2402.09181) | [Data](https://huggingface.co/datasets/foreverbeliever/OmniMedVQA) |
| 2024 | MedSafetyBench | Medical safety benchmark with harmful requests | [Paper](https://arxiv.org/abs/2403.03744) | [Code](https://github.com/AI4LIFE-GROUP/med-safety-bench) |
| 2024 | CARES | Medical LVLM trustworthiness across reliability dimensions | [Paper](https://arxiv.org/abs/2406.06007) | [Code](https://github.com/richard-peng-xia/CARES) |
| 2024 | ClinicalBench | LLMs vs classical clinical prediction models | [Paper](https://arxiv.org/abs/2411.06469) | [Code](https://github.com/canyuchen/ClinicalBench) |
| 2025 | MedXpertQA | Expert-level text and multimodal medical reasoning | [Paper](https://arxiv.org/abs/2501.18362) | [Data](https://huggingface.co/datasets/TsinghuaC3I/MedXpertQA) |
| 2025 | MedHallu | Medical hallucination detection benchmark | [Paper](https://arxiv.org/abs/2502.14302) | [Data](https://huggingface.co/datasets/UTAustin-AIHealth/MedHallu) |
| 2025 | HealthBench | Physician-rubric multiturn health conversations | [Paper](https://arxiv.org/abs/2505.08775) | [Data](https://huggingface.co/datasets/openai/healthbench) |
| 2025 | MedReason | Knowledge-graph grounded medical reasoning chains | [Paper](https://arxiv.org/abs/2504.00993) | [Code](https://github.com/UCSC-VLAA/MedReason) |
| 2025 | GEMeX | Grounded explainable chest X-ray VQA | [Paper](https://arxiv.org/abs/2411.16778) | [Data](https://www.med-vqa.com/GEMeX) |
| 2026 | RADAR | 3D radiology report discrepancy review | [Paper](https://arxiv.org/abs/2603.06681) | - |

#### Level 2: Tool-Augmented and Interactive Agency

| Year | Benchmark | What it tests | Paper | Data / Code |
|---|---|---|---|---|
| 2024 | AgentClinic | Multimodal multiagent simulated clinical encounters | [Paper](https://arxiv.org/abs/2405.07960) | [Code](https://github.com/SamuelSchmidgall/AgentClinic) |
| 2024 | MedCalc-Bench | Clinical calculator and medical computation | [Paper](https://arxiv.org/abs/2406.12036) | [Data](https://huggingface.co/datasets/ncbi/MedCalc-Bench-v1.0) |
| 2024 | EHRNoteQA | QA over MIMIC-IV discharge summaries | [Paper](https://arxiv.org/abs/2402.16040) | [Data](https://physionet.org/content/ehr-notes-qa-llms) |
| 2025 | MedAgentBench | FHIR-compliant virtual EHR agentic tasks | [Paper](https://arxiv.org/abs/2501.14654) | [Code](https://github.com/stanfordmlgroup/medagentbench) |
| 2025 | MedR-Bench | Real-case medical reasoning quality | [Paper](https://arxiv.org/abs/2503.04691) | [Code](https://github.com/MAGIC-AI4Med/MedRBench) |
| 2025 | MedAgentsBench | Hard multistep clinical reasoning | [Paper](https://arxiv.org/abs/2503.07459) | [Data](https://huggingface.co/datasets/super-dainiu/MedicalAgentsBench) |
| 2025 | 3MDBench | Multimodal multiagent doctor-patient dialogue | [Paper](https://arxiv.org/abs/2504.13861) | [Data](https://huggingface.co/datasets/univanxx/3mdbench) |
| 2025 | MedAgentBoard | Multiagent vs single-LLM clinical tasks | [Paper](https://arxiv.org/abs/2505.12371) | [Code](https://github.com/yhzhu99/medagentboard) |
| 2025 | MedBrowseComp | Multihop medical web-browsing agents | [Paper](https://arxiv.org/abs/2505.14963) | [Data](https://huggingface.co/datasets/AIM-Harvard/MedBrowseComp) |
| 2025 | BFCL | Live executable function and tool calling | [Paper](https://openreview.net/forum?id=2GmDdhBdDk) | [Data](https://huggingface.co/datasets/gorilla-llm/Berkeley-Function-Calling-Leaderboard) |
| 2025 | MedOdyssey | Medical long-context reasoning up to 200K tokens | [Paper](https://arxiv.org/abs/2406.15019) | [Code](https://github.com/JOHNNY-fans/MedOdyssey) |
| 2025 | LongHealth | Long fictional patient clinical documents | [Paper](https://arxiv.org/abs/2401.14490) | [Code](https://github.com/kbressem/LongHealth) |
| 2025 | R2MED | Reasoning-based medical retrieval | [Paper](https://arxiv.org/abs/2505.14558) | [Code](https://github.com/R2MED/R2MED) |
| 2025 | CURE-Bench | Therapeutic agent reasoning | [Paper](https://arxiv.org/abs/2512.11682) | [Code](https://github.com/mims-harvard/CURE-Bench) |
| 2025 | MedAgentSim | Self-evolving multi-agent clinical simulation | [Paper](https://arxiv.org/abs/2503.22678) | [Code](https://github.com/MAXNORM8650/MedAgentSim) |
| 2025 | PatientSim | Persona-driven patient simulation from MIMIC-IV | [Paper](https://arxiv.org/abs/2505.17818) | [Code](https://github.com/dek924/PatientSim) |
| 2026 | MedDialogRubrics | Multiturn diagnostic consultation with rubrics | [Paper](https://arxiv.org/abs/2601.03023) | - |
| 2026 | AgentRx | Single vs multi-agent multimodal clinical prediction | [Paper](https://arxiv.org/abs/2605.10286) | - |
| 2026 | ABRA | Radiology agent with OHIF, Orthanc, and 21 tools | [Paper](https://arxiv.org/abs/2605.11224) | [Code](https://github.com/Luab/ABRA) |
| 2026 | AutoMedBench | Workflow-aware autonomous medical AI research | [Paper](https://arxiv.org/abs/2606.01961) | [Code](https://github.com/automedbench/automedbench) |
| 2026 | DeepMed | Medical deep-research agent with multi-hop search | [Paper](https://aclanthology.org/2026.findings-acl.904) | - |
| 2026 | MedResearchBench | Medical research agents on clinical research tasks | [Paper](https://www.medrxiv.org/content/10.64898/2026.03.30.26349749v1) | - |
| 2026 | EHRBench | EHR-grounded clinical decision making | [Paper](https://arxiv.org/abs/2605.30637) | - |

#### Level 3: System-Level Clinical Operation

| Year | Benchmark | What it tests | Paper | Data / Code |
|---|---|---|---|---|
| 2024 | EHRAgent | Code-empowered multitabular EHR reasoning | [Paper](https://arxiv.org/abs/2401.07128) | [Code](https://github.com/wshi83/EhrAgent) |
| 2025 | ClinicalLab | Multidepartmental clinical benchmark | [Paper](https://arxiv.org/abs/2406.13890) | [Code](https://github.com/WeixiangYAN/ClinicalLab) |
| 2025 | MedChain | Sequential clinical workflow benchmark | [Paper](https://arxiv.org/abs/2412.01605) | [Code](https://github.com/ljwztc/MedChain) |
| 2025 | MedHELM | Holistic medical LLM evaluation | [Paper](https://arxiv.org/abs/2505.23802) | [Code](https://github.com/stanford-crfm/helm) |
| 2025 | MedAgentGym | Code-based medical reasoning training environment | [Paper](https://arxiv.org/abs/2506.04405) | [Code](https://github.com/wshi83/MedAgentGym) |
| 2025 | FHIR-AgentBench | HL7 FHIR interoperable EHR tasks | [Paper](https://arxiv.org/abs/2509.19319) | [Code](https://github.com/glee4810/FHIR-AgentBench) |
| 2025 | MedAgentAudit | Collaborative failure-mode audit for multiagent systems | [Paper](https://arxiv.org/abs/2510.10185) | [Code](https://github.com/MedX-PKU/MedAgentAudit) |
| 2026 | MedOpenClaw | Auditable full-study agents over clinical imaging | [Paper](https://arxiv.org/abs/2603.24649) | - |
| 2026 | MedFlowBench | Imaging viewer workflows for radiology and pathology | [Paper](https://arxiv.org/abs/2603.24649) | - |
| 2026 | PhysicianBench | Real-EHR long-horizon tasks with grounded checkpoints | [Paper](https://arxiv.org/abs/2605.02240) | [Code](https://github.com/HealthRex/PhysicianBench) |
| 2026 | CHI-Bench | Long-horizon healthcare workflow automation | [Paper](https://arxiv.org/abs/2605.16679) | [Code](https://github.com/actava-ai/chi-bench) |
| 2026 | MedCase-Structured | Text-to-FHIR reasoning over structured EHR | [Paper](https://arxiv.org/abs/2605.30295) | [Data](https://huggingface.co/datasets/system-technologies/MedCase-Structured) |
| 2026 | ClinEnv | Interactive long-horizon inpatient EHR simulation | [Paper](https://arxiv.org/abs/2606.02568) | - |
| 2026 | HealthAdminBench | Computer-use agents for healthcare administration | [Paper](https://arxiv.org/abs/2604.09937) | [Code](https://github.com/som-shahlab/health-admin-bench) |
| 2026 | HealthAgentBench | Agentic healthcare tasks across patient-journey environments | [Paper](https://arxiv.org/abs/2606.31179) | [Project](https://microsoft.github.io/HealthAgentBench) |
| 2026 | EHR-Complex | Interactive clinical database reasoning on MIMIC-IV | [Paper](https://arxiv.org/abs/2606.23301) | - |

### Evaluation Metrics Beyond Accuracy

| Dimension | What it measures | Why it matters |
|---|---|---|
| **Reasoning quality** | Coherence and clinical validity of reasoning traces | Explainability and clinician trust |
| **Efficiency** | Tool invocations, reasoning steps, latency | Clinical feasibility |
| **Robustness** | Performance across demographics and edge cases | Equitable healthcare delivery |
| **Safety** | Hallucination rate, false positive severity | Patient safety |
| **User experience** | Empathy, comprehensibility, actionability | Clinician adoption |

---

## Deployment and Governance

### Industry Deployment Landscape

| Organization | Domain | Key System |
|---|---|---|
| Google Health | Multi-domain | Med-Gemini |
| Microsoft | Multi-domain | Dragon Copilot (100K+ clinicians) |
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

### Regulatory Pathways

| Jurisdiction | Framework | Key Challenge for Agents |
|---|---|---|
| FDA (US) | SaMD + AI/ML Action Plan + PCCPs | Validating multistep reasoning |
| EU | MDR + AI Act (High-Risk) | Explainability requirements |
| NMPA (China) | Adapting for agent-based systems | Integration complexity |

---

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

---

## Open-Source Resources

| Resource | Type | Description |
|---|---|---|
| [LLaVA-Med](https://github.com/microsoft/LLaVA-Med) | Model | Open medical VQA model |
| [CheXagent](https://github.com/Stanford-AIMI/CheXagent) | Model + Data | Chest X-ray agent |
| [MedRAX](https://github.com/bowang-lab/MedRAX) | Framework | Tool orchestration for CXR |
| [MedAgent-Pro](https://github.com/jinlab-imvr/MedAgent-Pro) | Framework | Evidence-based multimodal diagnosis |
| [AutoGen](https://github.com/microsoft/autogen) | Framework | Multi-agent orchestration |
| [MetaGPT](https://github.com/geekan/MetaGPT) | Framework | Multi-agent programming |
| [AgentClinic](https://github.com/SamuelSchmidgall/AgentClinic) | Benchmark | Clinical agent evaluation |
| [MedAgentGym](https://github.com/wshi83/MedAgentGym) | Framework | Agent training gymnasium |
| [TxAgent](https://github.com/mims-harvard/TxAgent) | Framework | Therapeutic reasoning agent |
| [Awesome-AI-Agents-for-Healthcare](https://github.com/AgenticHealthAI/Awesome-AI-Agents-for-Healthcare) | List | Related awesome list |

---

## Related Surveys

- [A Survey of LLM-based Agents in Medicine: How far are we from Baymax? (2025)](https://arxiv.org/abs/2502.11211) — LLM medical agent survey
- [Awesome-AI-Agents-for-Healthcare](https://github.com/AgenticHealthAI/Awesome-AI-Agents-for-Healthcare) — Broader healthcare agent list
- [Awesome-Multimodal-in-Medical-Imaging](https://github.com/richard-peng-xia/awesome-multimodal-in-medical-imaging) — Multimodal medical imaging resources

---

## Star History

If you find this repository useful, please consider giving it a ⭐!

## LICENSE

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

## Citation

```bibtex
@article{zhu2026path,
  title={The Path to Self-Evolving Clinical Systems: Scaling Medical Agents from Assistance to Autonomy},
  author={Zhu, Chunzheng and Tian, Lei and Tan, Bohan and Zhou, Ziqi and Sun, Yuxuan and Wang, Yijun and Lv, Chengchao and Wen, Yilin and He, Yijun and Lin, Jinghao and Chen, Yihang and Tan, Cheewei and Wei, Qianshan and Zhao, Lei and Pu, Bin and Li, Kenli and Xue, Yuan and Lin, Jianxin},
  journal={arXiv preprint arXiv:2607.11175},
  year={2026},
  url={https://arxiv.org/abs/2607.11175}
}
```

## Contact

If you have any questions or suggestions, please feel free to open an issue or submit a pull request.
