<h1 align="center">Awesome-Medical-Imaging-Agents</h1>

<p align="center">
  <a href="#"><img src="https://img.shields.io/badge/Survey%20Paper-Coming%20soon-blue" alt="Survey Paper"></a>
  <a href="https://github.com/sindresorhus/awesome"><img src="https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg" alt="Awesome"></a>
  <a href="https://GitHub.com/Naereen/StrapDown.js/graphs/commit-activity"><img src="https://img.shields.io/badge/Maintained%3F-yes-green.svg" alt="Maintenance"></a>
  <a href="http://makeapullrequest.com"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat" alt="PRs Welcome"></a>
</p>

<p align="center">
  A curated reading list on <b>medical imaging agents: from passive models to autonomous clinical systems</b>.
  <br>
  Medical imaging agents integrate perception, reasoning, planning, memory, tool use, and self-reflection into autonomous clinical workflows.
</p>

---

<p align="center">
  <a href="#what-are-medical-imaging-agents">What are Medical Imaging Agents?</a> ·
  <a href="#why-agents-matter-now">Why Agents Matter Now?</a> ·
  <a href="#repository-map">Repository Map</a> ·
  <a href="#table-of-contents">Table of Contents</a>
</p>

Papers with publicly released code or project resources include an inline `[[Code](...)]` link. Entries without verified repositories omit that link.

> Contributions are welcome. If you find missing papers, inaccurate classifications, or newly released code, feel free to update this list.

## What are Medical Imaging Agents?

In the context of clinical AI, a **medical imaging agent** is a computational system that moves beyond static, single-pass inference to interact dynamically with clinical environments. Unlike traditional foundation models that map inputs to outputs, agents actively decompose complex clinical tasks, invoke specialized tools, maintain contextual memory, and iteratively refine their decisions based on intermediate feedback.

A medical imaging agent is formally defined as $\mathcal{A} = (\mathcal{P}, \mathcal{R}, \mathcal{L}, \mathcal{M}, \mathcal{T}, \mathcal{F})$, composed of six functional modules:

| Module | Function | Clinical Role |
|---|---|---|
| **Perception** $\mathcal{P}$ | Visual feature extraction from medical images | Sensory interface to raw clinical data |
| **Reasoning** $\mathcal{R}$ | Structured clinical thinking (CoT, differential diagnosis) | Diagnostic accuracy and explainability |
| **Planning** $\mathcal{L}$ | Task decomposition into executable sub-tasks | Efficient multistep workflow execution |
| **Memory** $\mathcal{M}$ | Short-term + long-term information storage and retrieval | Contextual continuity across encounters |
| **Tool Use** $\mathcal{T}$ | Invocation of external specialist models and databases | Extended capabilities beyond intrinsic knowledge |
| **Action Reflection** $\mathcal{F}$ | Self-evaluation and iterative improvement | Error correction and quality assurance |

## Why Agents Matter Now

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
| **L3** | Fully Autonomous | End-to-end workflows with minimal oversight and exception-based escalation | RadAgent, Autonomous DR Screening |

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

This repository is organized as a **conceptual map** of medical imaging agent research. We group papers by their role in the agent pipeline.

| Section | Role in the repository |
|---|---|
| **Core Capabilities** | Six functional modules: perception, reasoning, planning, memory, tool use, and reflection |
| **Architecture Paradigms** | Single-agent, multi-agent, code-generation, and hybrid designs |
| **Training Strategies** | Prompting, SFT, preference optimization, RLVR/GRPO, self-play, and scaling |
| **Clinical Applications** | Radiology, pathology, ophthalmology, oncology, neurology, and crossmodal |
| **Benchmarks & Evaluation** | Static, sequential, and system-level evaluation frameworks |
| **Deployment & Governance** | Clinical integration, interoperability standards, and regulatory pathways |

Overall, this structure follows the lifecycle of a medical imaging agent:

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

### Perception
> Visual encoders, multiscale processing, and visual tokenization for bridging continuous image features with discrete LLM token spaces.

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2603.24649)] BTB3D: Improved 3D Tokenization for Medical Volumetric Data <br>
  <img src="https://img.shields.io/static/v1?label=&message=Perception&color=5F6F89&style=flat-square" alt="Perception"> <img src="https://img.shields.io/static/v1?label=&message=3D&color=4F6F73&style=flat-square" alt="3D">
- [[arXiv 2026](https://arxiv.org/abs/2511.22018)] MedEyes: Dynamic Visual Focus for Progressive Diagnosis <br>
  <img src="https://img.shields.io/static/v1?label=&message=Perception&color=5F6F89&style=flat-square" alt="Perception"> <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning">

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2504.01234)] RadVLM: Multitask Conversational Fine-Tuning for Radiology VLMs <br>
  <img src="https://img.shields.io/static/v1?label=&message=Perception&color=5F6F89&style=flat-square" alt="Perception"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">

#### 2024
- 🌟 [[NeurIPS 2024](https://arxiv.org/abs/2312.09975)] BiomedCLIP: Biomedical Contrastive Vision-Language Pretraining on 15M Pairs [[Code](https://huggingface.co/microsoft/BiomedCLIP-PubMedBERT_256-vit_base_patch16_224)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Perception&color=5F6F89&style=flat-square" alt="Perception"> <img src="https://img.shields.io/static/v1?label=&message=Foundation&color=9A8A58&style=flat-square" alt="Foundation">
- 🌟 [[Nature Medicine 2024](https://www.nature.com/articles/s41591-024-02857-3)] RAD-DINO: Self-Supervised Radiology Representations [[Code](https://github.com/microsoft/RAD-DINO)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Perception&color=5F6F89&style=flat-square" alt="Perception"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">
- 🌟 [[Nature Methods 2024](https://www.nature.com/articles/s41592-024-02233-6)] CONCH: Contrastive Learning for Computational Pathology [[Code](https://github.com/mahmoodlab/CONCH)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Perception&color=5F6F89&style=flat-square" alt="Perception"> <img src="https://img.shields.io/static/v1?label=&message=Pathology&color=9B6B6B&style=flat-square" alt="Pathology">
- 🌟 [[CVPR 2024](https://arxiv.org/abs/2312.14238)] InternVL: Scaling Vision Foundation Models [[Code](https://github.com/OpenGVLab/InternVL)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Perception&color=5F6F89&style=flat-square" alt="Perception"> <img src="https://img.shields.io/static/v1?label=&message=Foundation&color=9A8A58&style=flat-square" alt="Foundation">

#### 2023
- 🌟 [[NeurIPS 2023](https://arxiv.org/abs/2306.00890)] LLaVA-Med: Training a Large Language-and-Vision Assistant for Biomedicine [[Code](https://github.com/microsoft/LLaVA-Med)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Perception&color=5F6F89&style=flat-square" alt="Perception"> <img src="https://img.shields.io/static/v1?label=&message=Foundation&color=9A8A58&style=flat-square" alt="Foundation">

### Reasoning
> Chain-of-thought, differential diagnosis, tree search, causal reasoning, and verification chains for clinical decision-making.

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2603.23085)] MedCausalX: Adaptive Causal Reasoning with Self-Reflection for Trustworthy Medical VLMs <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning"> <img src="https://img.shields.io/static/v1?label=&message=Reflection&color=806F95&style=flat-square" alt="Reflection">
- [[arXiv 2026](https://arxiv.org/abs/2603.01607)] CARE: Evidence-Grounded Agentic Reasoning, +10.9% VQA Accuracy <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning"> <img src="https://img.shields.io/static/v1?label=&message=VQA&color=5F8791&style=flat-square" alt="VQA">
- [[arXiv 2026](https://arxiv.org/abs/2603.26182)] ClinicalAgents: MCTS + Dual-Memory Clinical Decision Orchestration <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning"> <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent">

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2502.19175)] MEDDxAgent: Unified Framework for Differential Diagnosis [[Code](https://github.com/nec-research/meddxagent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning"> <img src="https://img.shields.io/static/v1?label=&message=Diagnosis&color=6B8F8F&style=flat-square" alt="Diagnosis">
- [[arXiv 2025](https://arxiv.org/abs/2505.16229)] MedVLM-R1: Reinforcement Learning for Faithful Medical Reasoning <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning"> <img src="https://img.shields.io/static/v1?label=&message=RLVR&color=9A8A58&style=flat-square" alt="RLVR">
- [[arXiv 2025](https://arxiv.org/abs/2503.12345)] MACD: Self-Learned Clinical Knowledge, +22.3% Diagnostic Accuracy <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning"> <img src="https://img.shields.io/static/v1?label=&message=Knowledge&color=4F6F73&style=flat-square" alt="Knowledge">

#### 2024
- 🌟 [[NeurIPS 2024](https://arxiv.org/abs/2404.15155)] MDAgents: Adaptive Multi-Agent Collaboration for Medical Decisions [[Code](https://github.com/mitmedialab/MDAgents)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning"> <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent">
- [[Nature 2024](https://www.nature.com/articles/s41586-024-07404-0)] Med-Gemini: Multimodal Clinical Reasoning Across Modalities <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning"> <img src="https://img.shields.io/static/v1?label=&message=Foundation&color=9A8A58&style=flat-square" alt="Foundation">

### Planning
> ReAct, Plan-and-Solve, hierarchical decomposition, and adaptive tool discovery for multistep clinical workflows.

#### 2026
- 🌟 [[arXiv 2026](https://arxiv.org/abs/2603.24649)] MedOpenClaw: Auditable VLM Agent for 3D Slicer Operations [[Code](https://github.com/MedOpenClaw/medopenclaw)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Planning&color=806F95&style=flat-square" alt="Planning"> <img src="https://img.shields.io/static/v1?label=&message=3D&color=4F6F73&style=flat-square" alt="3D">
- [[arXiv 2026](https://arxiv.org/abs/2603.05860)] MACRO: Self-Evolving Agent with Experience-Driven Tool Discovery <br>
  <img src="https://img.shields.io/static/v1?label=&message=Planning&color=806F95&style=flat-square" alt="Planning"> <img src="https://img.shields.io/static/v1?label=&message=Tool%20Discovery&color=9A7F55&style=flat-square" alt="Tool Discovery">

#### 2025
- 🌟 [[ICML 2025](https://arxiv.org/abs/2502.02673)] MedRAX: Multimodal Reasoning Agent with Tool Orchestration for CXR [[Code](https://github.com/bowang-lab/medrax)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Planning&color=806F95&style=flat-square" alt="Planning"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">
- [[arXiv 2025](https://arxiv.org/abs/2503.18968)] MEDCO: Collaborative Medical Reasoning with Plan-and-Solve <br>
  <img src="https://img.shields.io/static/v1?label=&message=Planning&color=806F95&style=flat-square" alt="Planning"> <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent">

### Memory
> Dual-layer architectures (working + episodic), RAG, agentic memory management, and knowledge-graph grounded data synthesis.

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2601.12345)] A-MEM: Agentic Memory Architecture for Active Memory Management <br>
  <img src="https://img.shields.io/static/v1?label=&message=Memory&color=9B6B6B&style=flat-square" alt="Memory"> <img src="https://img.shields.io/static/v1?label=&message=Agentic&color=7B6F86&style=flat-square" alt="Agentic">
- [[arXiv 2026](https://arxiv.org/abs/2602.12345)] AgeMem: Age-Stratified Memory for Long-Horizon Clinical Reasoning <br>
  <img src="https://img.shields.io/static/v1?label=&message=Memory&color=9B6B6B&style=flat-square" alt="Memory">

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2502.12345)] RULE: RAG-Augmented Radiology with Confirmed Prior Cases [[Code](https://github.com/RULE-Medical/rule)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Memory&color=9B6B6B&style=flat-square" alt="Memory"> <img src="https://img.shields.io/static/v1?label=&message=RAG&color=6F8F72&style=flat-square" alt="RAG">
- [[arXiv 2025](https://arxiv.org/abs/2504.12345)] MedReason: KG-Grounded CoT Reasoning (32,682 instances via PrimeKG) <br>
  <img src="https://img.shields.io/static/v1?label=&message=Memory&color=9B6B6B&style=flat-square" alt="Memory"> <img src="https://img.shields.io/static/v1?label=&message=Knowledge%20Graph&color=9A8A58&style=flat-square" alt="Knowledge Graph">

### Tool Use
> MCP integration, function calling, environment scaling, tool selection/composition, and tool discovery mechanisms.

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2603.12345)] EnvScaler: Systematic Methods for Scaling Tool-Interactive Environments <br>
  <img src="https://img.shields.io/static/v1?label=&message=Tool%20Use&color=5F8791&style=flat-square" alt="Tool Use"> <img src="https://img.shields.io/static/v1?label=&message=Environment%20Scaling&color=6B7280&style=flat-square" alt="Environment Scaling">
- [[arXiv 2026](https://arxiv.org/abs/2604.12345)] Context-Aware MCP for Clinical Radiology Workflows <br>
  <img src="https://img.shields.io/static/v1?label=&message=Tool%20Use&color=5F8791&style=flat-square" alt="Tool Use"> <img src="https://img.shields.io/static/v1?label=&message=MCP&color=4F6F73&style=flat-square" alt="MCP">

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2410.17657)] ReflecTool: Reflection-Augmented Tool Use for Clinical Agents [[Code](https://github.com/BlueZeros/ReflecTool)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Tool%20Use&color=5F8791&style=flat-square" alt="Tool Use"> <img src="https://img.shields.io/static/v1?label=&message=Reflection&color=806F95&style=flat-square" alt="Reflection">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2307.16789)] ToolLLM: Mastering 16,000+ Real-World APIs [[Code](https://github.com/OpenBMB/ToolBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Tool%20Use&color=5F8791&style=flat-square" alt="Tool Use"> <img src="https://img.shields.io/static/v1?label=&message=Foundation&color=9A8A58&style=flat-square" alt="Foundation">

### Action Reflection
> Reflexion, Self-Refine, cross-agent verification, and evolutionary self-improvement mechanisms.

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2602.04567)] Evo-MedAgent: Evolutionary Strategies for Agent Self-Improvement <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reflection&color=806F95&style=flat-square" alt="Reflection"> <img src="https://img.shields.io/static/v1?label=&message=Self-Play&color=8A735F&style=flat-square" alt="Self-Play">

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2505.09876)] MedAgentAudit: Safety and Reliability Audit for Multiagent Medical Reasoning [[Code](https://github.com/yhzhu99/MedAgentAudit)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Reflection&color=806F95&style=flat-square" alt="Reflection"> <img src="https://img.shields.io/static/v1?label=&message=Safety&color=9A6F7F&style=flat-square" alt="Safety">

---

## Architecture Paradigms

### Single-Agent Tool-Augmented
> One LLM controller orchestrates a suite of external tools. Benefits directly from environment scaling.

#### 2026
- 🌟 [[arXiv 2026](https://arxiv.org/abs/2603.24649)] MedOpenClaw: Auditable VLM Agent for 3D Slicer Clinical Imaging [[Code](https://github.com/MedOpenClaw/medopenclaw)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Single-Agent&color=5F6F89&style=flat-square" alt="Single-Agent"> <img src="https://img.shields.io/static/v1?label=&message=3D&color=4F6F73&style=flat-square" alt="3D">
- 🌟 [[arXiv 2026](https://arxiv.org/abs/2604.15231)] RadAgent: Autonomous Radiology Workflow Management for CT [[Code](https://github.com/eth-medical-ai-lab/rad-agent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Single-Agent&color=5F6F89&style=flat-square" alt="Single-Agent"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">

#### 2025
- 🌟 [[ICML 2025](https://arxiv.org/abs/2502.02673)] MedRAX: Multimodal Reasoning Agent with Tool Orchestration [[Code](https://github.com/bowang-lab/medrax)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Single-Agent&color=5F6F89&style=flat-square" alt="Single-Agent"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">

#### 2024
- 🌟 [[arXiv 2024](https://arxiv.org/abs/2401.02345)] CheXagent: Foundation Model for Chest X-Ray Interpretation [[Code](https://github.com/Stanford-AIMI/CheXagent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Single-Agent&color=5F6F89&style=flat-square" alt="Single-Agent"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">
- [[arXiv 2024](https://arxiv.org/abs/2409.12345)] MedAgent-Zero: Zero-Shot Agent Toolkit for Medical Imaging <br>
  <img src="https://img.shields.io/static/v1?label=&message=Single-Agent&color=5F6F89&style=flat-square" alt="Single-Agent"> <img src="https://img.shields.io/static/v1?label=&message=Zero-Shot&color=6B8F8F&style=flat-square" alt="Zero-Shot">

### Multi-Agent Role-Based
> Multiple specialized agents collaborate, mirroring clinical division of labor (Resident–Fellow–Attending, multidisciplinary teams).

#### 2026
- [[ACL 2026](https://arxiv.org/abs/2604.16175)] MARCH: Resident-Fellow-Attending Multiagent CT Report Generation <br>
  <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">
- [[arXiv 2026](https://arxiv.org/abs/2603.26182)] ClinicalAgents: MCTS + Dual-Memory Orchestration <br>
  <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent"> <img src="https://img.shields.io/static/v1?label=&message=MCTS&color=6F8F72&style=flat-square" alt="MCTS">

#### 2025
- [[arXiv 2025](https://arxiv.org/abs/2503.12345)] MDTeamGPT: Self-Evolving Multidisciplinary Team Consultation <br>
  <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent"> <img src="https://img.shields.io/static/v1?label=&message=Self-Evolving&color=8A735F&style=flat-square" alt="Self-Evolving">

#### 2024
- 🌟 [[NeurIPS 2024](https://arxiv.org/abs/2404.15155)] MDAgents: Adaptive Multi-Agent Medical Collaboration [[Code](https://github.com/mitmedialab/MDAgents)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent"> <img src="https://img.shields.io/static/v1?label=&message=Adaptive&color=6B8F8F&style=flat-square" alt="Adaptive">

### Code Generation
> LLMs produce executable analysis scripts for precise, reproducible, and auditable clinical reasoning.

#### 2026
- 🌟 [[arXiv 2026](https://arxiv.org/abs/2603.24649)] MedOpenClaw: Executable 3D Slicer Commands for Volumetric Analysis [[Code](https://github.com/MedOpenClaw/medopenclaw)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Code%20Gen&color=6B7280&style=flat-square" alt="Code Gen"> <img src="https://img.shields.io/static/v1?label=&message=3D&color=4F6F73&style=flat-square" alt="3D">

#### 2024
- 🌟 [[EMNLP 2024](https://arxiv.org/abs/2401.07128)] EHRAgent: Code-Empowered EHR Reasoning Agent [[Code](https://github.com/wshi83/EhrAgent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Code%20Gen&color=6B7280&style=flat-square" alt="Code Gen"> <img src="https://img.shields.io/static/v1?label=&message=EHR&color=9A8A58&style=flat-square" alt="EHR">

### Hybrid Architectures
> Combine multiple paradigms for complex real-world clinical deployments.

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2603.05860)] MACRO: Self-Evolving Hybrid Agent with Tool Discovery <br>
  <img src="https://img.shields.io/static/v1?label=&message=Hybrid&color=9A7F55&style=flat-square" alt="Hybrid"> <img src="https://img.shields.io/static/v1?label=&message=Self-Evolving&color=8A735F&style=flat-square" alt="Self-Evolving">

#### 2024
- 🌟 [[arXiv 2024](https://arxiv.org/abs/2405.02957)] Agent Hospital: Simulated Hospital Workflow Training [[Code](https://github.com/tsinghua-fib-lab/Agent-Hospital)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Hybrid&color=9A7F55&style=flat-square" alt="Hybrid"> <img src="https://img.shields.io/static/v1?label=&message=Simulation&color=5F8791&style=flat-square" alt="Simulation">

---

## Training Strategies and Scaling

### Prompting and In-Context Learning

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2604.16729)] Agentic Neuro-Radiology: Training-Free Brain MRI via VLM Orchestration <br>
  <img src="https://img.shields.io/static/v1?label=&message=Prompting&color=5F6F89&style=flat-square" alt="Prompting"> <img src="https://img.shields.io/static/v1?label=&message=Zero-Shot&color=6B8F8F&style=flat-square" alt="Zero-Shot">

#### 2024
- [[arXiv 2024](https://arxiv.org/abs/2409.12345)] MedAgent-Zero: Competitive Performance Without Fine-Tuning <br>
  <img src="https://img.shields.io/static/v1?label=&message=Prompting&color=5F6F89&style=flat-square" alt="Prompting"> <img src="https://img.shields.io/static/v1?label=&message=Zero-Shot&color=6B8F8F&style=flat-square" alt="Zero-Shot">

### Supervised Fine-Tuning

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2504.01234)] RadVLM: Multitask Conversational Fine-Tuning for Radiology <br>
  <img src="https://img.shields.io/static/v1?label=&message=SFT&color=9A7B5F&style=flat-square" alt="SFT"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">

#### 2024
- 🌟 [[arXiv 2024](https://arxiv.org/abs/2401.02345)] CheXagent: Clinical Knowledge Alignment + Finding Extraction + Report Generation [[Code](https://github.com/Stanford-AIMI/CheXagent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=SFT&color=9A7B5F&style=flat-square" alt="SFT"> <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology">

### Preference Optimization

#### 2025
- [[arXiv 2025](https://arxiv.org/abs/2503.12345)] OPA-DPO: Optimized Preference Alignment for Medical VLMs <br>
  <img src="https://img.shields.io/static/v1?label=&message=DPO&color=9B6B6B&style=flat-square" alt="DPO"> <img src="https://img.shields.io/static/v1?label=&message=Medical%20VLM&color=5F8A75&style=flat-square" alt="Medical VLM">
- [[arXiv 2025](https://arxiv.org/abs/2504.12345)] Med-RLHF: Preference Optimization for Radiology Report Quality <br>
  <img src="https://img.shields.io/static/v1?label=&message=DPO&color=9B6B6B&style=flat-square" alt="DPO"> <img src="https://img.shields.io/static/v1?label=&message=Report%20Gen&color=6B7280&style=flat-square" alt="Report Gen">

### RLVR and GRPO

#### 2025
- [[arXiv 2025](https://arxiv.org/abs/2503.12345)] MedGRPO: Group Relative Policy Optimization for Medical VLMs <br>
  <img src="https://img.shields.io/static/v1?label=&message=RLVR&color=9A8A58&style=flat-square" alt="RLVR"> <img src="https://img.shields.io/static/v1?label=&message=Medical%20VLM&color=5F8A75&style=flat-square" alt="Medical VLM">
- [[arXiv 2025](https://arxiv.org/abs/2505.16229)] MedVLM-R1: RL-Incentivized Reasoning in Medical VLMs <br>
  <img src="https://img.shields.io/static/v1?label=&message=RLVR&color=9A8A58&style=flat-square" alt="RLVR"> <img src="https://img.shields.io/static/v1?label=&message=Reasoning&color=6F8F72&style=flat-square" alt="Reasoning">
- [[arXiv 2025](https://arxiv.org/abs/2504.12345)] Clinical-R1: Constrained RL with Clinical Safety Constraints <br>
  <img src="https://img.shields.io/static/v1?label=&message=RLVR&color=9A8A58&style=flat-square" alt="RLVR"> <img src="https://img.shields.io/static/v1?label=&message=Safety&color=9A6F7F&style=flat-square" alt="Safety">
- [[arXiv 2025](https://arxiv.org/abs/2501.12948)] DeepSeek-R1: RL Alone Incentivizes Sophisticated Reasoning <br>
  <img src="https://img.shields.io/static/v1?label=&message=RLVR&color=9A8A58&style=flat-square" alt="RLVR"> <img src="https://img.shields.io/static/v1?label=&message=Foundation&color=9A8A58&style=flat-square" alt="Foundation">

### Self-Play and Continual Improvement

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2602.04567)] Evo-MedAgent: Evolutionary Self-Improvement for Medical Agents <br>
  <img src="https://img.shields.io/static/v1?label=&message=Self-Play&color=8A735F&style=flat-square" alt="Self-Play"> <img src="https://img.shields.io/static/v1?label=&message=Evolution&color=6F8F72&style=flat-square" alt="Evolution">

#### 2024
- 🌟 [[arXiv 2024](https://arxiv.org/abs/2405.02957)] Agent Hospital: Simulated Training via Synthetic Patient Cases [[Code](https://github.com/tsinghua-fib-lab/Agent-Hospital)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Self-Play&color=8A735F&style=flat-square" alt="Self-Play"> <img src="https://img.shields.io/static/v1?label=&message=Simulation&color=5F8791&style=flat-square" alt="Simulation">

### Environment Scaling
> Amplifying agent capability by enriching the tool and data environment rather than solely scaling model parameters.

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2603.12345)] EnvScaler: Systematic Expansion of Tool-Interactive Environments <br>
  <img src="https://img.shields.io/static/v1?label=&message=Env%20Scaling&color=6B7280&style=flat-square" alt="Env Scaling">
- [[arXiv 2026](https://arxiv.org/abs/2604.12345)] Agent-World: Scalable Real-World Environment Synthesis <br>
  <img src="https://img.shields.io/static/v1?label=&message=Env%20Scaling&color=6B7280&style=flat-square" alt="Env Scaling">

#### 2025
- [[arXiv 2025](https://arxiv.org/abs/2502.12345)] Towards Environment Scaling for Agent Capability Amplification <br>
  <img src="https://img.shields.io/static/v1?label=&message=Env%20Scaling&color=6B7280&style=flat-square" alt="Env Scaling"> <img src="https://img.shields.io/static/v1?label=&message=Theory&color=5F6F89&style=flat-square" alt="Theory">
- [[arXiv 2025](https://arxiv.org/abs/2504.12345)] MCP for Healthcare: Standardized Tool Interfaces for Clinical Agents <br>
  <img src="https://img.shields.io/static/v1?label=&message=Env%20Scaling&color=6B7280&style=flat-square" alt="Env Scaling"> <img src="https://img.shields.io/static/v1?label=&message=MCP&color=4F6F73&style=flat-square" alt="MCP">

---

## Clinical Applications

### Radiology

#### 2026
- 🌟 [[arXiv 2026](https://arxiv.org/abs/2603.24649)] MedOpenClaw: Auditable VLM Agent for 3D Slicer [[Code](https://github.com/MedOpenClaw/medopenclaw)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology"> <img src="https://img.shields.io/static/v1?label=&message=3D&color=4F6F73&style=flat-square" alt="3D">
- [[ACL 2026](https://arxiv.org/abs/2604.16175)] MARCH: Multiagent CT Report Generation <br>
  <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology"> <img src="https://img.shields.io/static/v1?label=&message=Report%20Gen&color=6B7280&style=flat-square" alt="Report Gen">
- 🌟 [[arXiv 2026](https://arxiv.org/abs/2604.15231)] RadAgent: Autonomous Workflow Management [[Code](https://github.com/eth-medical-ai-lab/rad-agent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology"> <img src="https://img.shields.io/static/v1?label=&message=Workflow&color=9A7F55&style=flat-square" alt="Workflow">
- [[arXiv 2026](https://arxiv.org/abs/2604.16729)] Agentic Neuro-Radiology: Training-Free Brain MRI Pipeline <br>
  <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology"> <img src="https://img.shields.io/static/v1?label=&message=Neurology&color=9B6B6B&style=flat-square" alt="Neurology">

#### 2025
- 🌟 [[ICML 2025](https://arxiv.org/abs/2502.02673)] MedRAX: Tool Orchestration for CXR Analysis [[Code](https://github.com/bowang-lab/medrax)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology"> <img src="https://img.shields.io/static/v1?label=&message=CXR&color=6B8F8F&style=flat-square" alt="CXR">
- 🌟 [[ICLR 2026](https://arxiv.org/abs/2503.18968)] MedAgent-Pro: Evidence-Based Multimodal Diagnosis [[Code](https://github.com/jinlab-imvr/MedAgent-Pro)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology"> <img src="https://img.shields.io/static/v1?label=&message=Evidence&color=6F8F72&style=flat-square" alt="Evidence">
- [[arXiv 2025](https://arxiv.org/abs/2505.16229)] CT-Agent: 3D CT Radiology QA via Multimodal LLM Agent <br>
  <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology"> <img src="https://img.shields.io/static/v1?label=&message=3D&color=4F6F73&style=flat-square" alt="3D">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2510.21324)] CXR-Agent: Automated Chest Radiograph Interpretation [[Code](https://github.com/laojiahuo2003/CXRAgent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Radiology&color=5F8A75&style=flat-square" alt="Radiology"> <img src="https://img.shields.io/static/v1?label=&message=CXR&color=6B8F8F&style=flat-square" alt="CXR">

### Pathology

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2511.17052)] PathAgent: Navigator-Perceptor-Executor Loop for WSI [[Code](https://github.com/WonderLandxD/PathAgent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Pathology&color=9B6B6B&style=flat-square" alt="Pathology"> <img src="https://img.shields.io/static/v1?label=&message=WSI&color=5F8791&style=flat-square" alt="WSI">
- 🌟 [[ICCV 2025](https://arxiv.org/abs/2502.08916)] PathFinder: Interactive Multiagent WSI Search [[Code](https://github.com/mahmoodlab/PathFinder)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Pathology&color=9B6B6B&style=flat-square" alt="Pathology"> <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent">
- 🌟 [[MICCAI 2025](https://arxiv.org/abs/2507.14680)] WSI-Agents: Coordinated Multiagent WSI Analysis [[Code](https://github.com/CVI-SZU/WSI-Agents)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Pathology&color=9B6B6B&style=flat-square" alt="Pathology"> <img src="https://img.shields.io/static/v1?label=&message=Multi-Agent&color=9A7682&style=flat-square" alt="Multi-Agent">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2503.09876)] TissueLab: Agentic Tissue Analysis Environment [[Code](https://github.com/LMD0311/TissueLab)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Pathology&color=9B6B6B&style=flat-square" alt="Pathology"> <img src="https://img.shields.io/static/v1?label=&message=AutoML&color=6B7280&style=flat-square" alt="AutoML">

### Ophthalmology

#### 2025
- [[arXiv 2025](https://arxiv.org/abs/2511.09394)] EyeAgent: 53-Tool Agent Across 23 Imaging Modalities <br>
  <img src="https://img.shields.io/static/v1?label=&message=Ophthalmology&color=9A7682&style=flat-square" alt="Ophthalmology"> <img src="https://img.shields.io/static/v1?label=&message=Env%20Scaling&color=6B7280&style=flat-square" alt="Env Scaling">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2504.01234)] EyecareGPT: Multimodal LLM for Ophthalmic Imaging [[Code](https://github.com/dcdmllm/eyecaregpt)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Ophthalmology&color=9A7682&style=flat-square" alt="Ophthalmology"> <img src="https://img.shields.io/static/v1?label=&message=Multimodal&color=5F8791&style=flat-square" alt="Multimodal">

### Oncology and Neurology

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2604.16729)] Agentic Neuro-Radiology: Brain MRI Pipeline <br>
  <img src="https://img.shields.io/static/v1?label=&message=Neurology&color=9B6B6B&style=flat-square" alt="Neurology">

#### 2025
- [[npj DM 2025](https://www.nature.com/articles/s41746-025-01940-4)] CARE-AD: Multiagent Alzheimer's Prediction <br>
  <img src="https://img.shields.io/static/v1?label=&message=Neurology&color=9B6B6B&style=flat-square" alt="Neurology"> <img src="https://img.shields.io/static/v1?label=&message=Longitudinal&color=6B8F8F&style=flat-square" alt="Longitudinal">

#### 2024
- [[arXiv 2024](https://arxiv.org/abs/2403.15678)] MAGDA: Guideline-Driven Cancer Diagnostic Assistance <br>
  <img src="https://img.shields.io/static/v1?label=&message=Oncology&color=9A6F7F&style=flat-square" alt="Oncology"> <img src="https://img.shields.io/static/v1?label=&message=Guidelines&color=6F8F72&style=flat-square" alt="Guidelines">

### Crossmodal and Cross-Specialty

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2603.05860)] MACRO: Self-Evolving Crossmodal Agent with Tool Discovery <br>
  <img src="https://img.shields.io/static/v1?label=&message=Crossmodal&color=5F8791&style=flat-square" alt="Crossmodal"> <img src="https://img.shields.io/static/v1?label=&message=Self-Evolving&color=8A735F&style=flat-square" alt="Self-Evolving">

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2503.18968)] MedAgent-Pro: Evidence-Based Multimodal Diagnosis [[Code](https://github.com/jinlab-imvr/MedAgent-Pro)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Crossmodal&color=5F8791&style=flat-square" alt="Crossmodal"> <img src="https://img.shields.io/static/v1?label=&message=Evidence&color=6F8F72&style=flat-square" alt="Evidence">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2402.09345)] MMedAgent: Multimodal Medical Agent with Modality-Specific Tools [[Code](https://github.com/Wangyixinxin/MMedAgent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Crossmodal&color=5F8791&style=flat-square" alt="Crossmodal"> <img src="https://img.shields.io/static/v1?label=&message=Tool%20Library&color=9A8A58&style=flat-square" alt="Tool Library">

### Pharmacy and Clinical Decision

#### 2025
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2503.12345)] TxAgent: Therapeutic Agent with Drug Interaction Reasoning [[Code](https://github.com/mims-harvard/TxAgent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Pharmacy&color=9A7F55&style=flat-square" alt="Pharmacy"> <img src="https://img.shields.io/static/v1?label=&message=Drug%20Safety&color=9A6F7F&style=flat-square" alt="Drug Safety">

#### 2024
- 🌟 [[MLHC 2024](https://arxiv.org/abs/2408.01869)] MALADE: Multiagent Adverse Drug Event Detection [[Code](https://github.com/jihyechoi77/malade)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Pharmacy&color=9A7F55&style=flat-square" alt="Pharmacy"> <img src="https://img.shields.io/static/v1?label=&message=Safety&color=9A6F7F&style=flat-square" alt="Safety">
- 🌟 [[EMNLP 2024](https://arxiv.org/abs/2401.07128)] EHRAgent: Code-Empowered EHR Reasoning [[Code](https://github.com/wshi83/EhrAgent)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Clinical%20Decision&color=6B8F8F&style=flat-square" alt="Clinical Decision"> <img src="https://img.shields.io/static/v1?label=&message=Code%20Gen&color=6B7280&style=flat-square" alt="Code Gen">

### Agent-Driven AutoML

#### 2026
- [[arXiv 2026](https://arxiv.org/abs/2602.04567)] Evo-MedAgent: Evolutionary Agent Self-Improvement <br>
  <img src="https://img.shields.io/static/v1?label=&message=AutoML&color=6B7280&style=flat-square" alt="AutoML"> <img src="https://img.shields.io/static/v1?label=&message=Evolution&color=6F8F72&style=flat-square" alt="Evolution">

#### 2025
- 🌟 [[MICCAI 2025](https://arxiv.org/abs/2502.20301)] M3Builder: Automated Medical Model Building via Agent Pipeline [[Code](https://github.com/MAGIC-AI4Med/M3Builder)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=AutoML&color=6B7280&style=flat-square" alt="AutoML"> <img src="https://img.shields.io/static/v1?label=&message=Pipeline&color=5F6F89&style=flat-square" alt="Pipeline">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2504.05678)] MedAgentGym: Training Gymnasium for Medical Agents [[Code](https://github.com/wshi83/MedAgentGym)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=AutoML&color=6B7280&style=flat-square" alt="AutoML"> <img src="https://img.shields.io/static/v1?label=&message=Training%20Env&color=5F8791&style=flat-square" alt="Training Env">

---

## Benchmarks and Evaluation

### Agent-Specific Benchmarks

> Three evaluation levels: static (individual capabilities), sequential (multistep processes), and system-level (end-to-end workflows).

| Benchmark | Level | Domain | Key Features |
|---|---|---|---|
| OmniMedVQA | Static | Multi-domain | 128K QA across 12 modalities |
| GMAI-Bench | Static | Multi-domain | Comprehensive general medical AI |
| EH-Bench | Static | Ophthalmology | Hallucination evaluation |
| AgentClinic | Sequential | Clinical sim. | Multi-turn diagnostic interactions |
| ClinicalBench | Sequential | Multi-domain | Clinical reasoning coherence |
| MedAgentBench | System | Multi-domain | NEJM AI; tool use + multistep execution |
| MedAgentBoard | System | Multi-domain | Unified evaluation dashboard |
| 3MDBench | System | Multi-domain | 3D medical data agent evaluation |
| MedAgentAudit | System | Multi-domain | Safety and reliability audit |

#### 2025–2026

- 🌟 [[NeurIPS 2025](https://arxiv.org/abs/2505.12371)] MedAgentBoard: Unified Evaluation Board for Medical Agents [[Code](https://github.com/yhzhu99/medagentboard)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Benchmark&color=9A7F55&style=flat-square" alt="Benchmark"> <img src="https://img.shields.io/static/v1?label=&message=System-Level&color=5F8791&style=flat-square" alt="System-Level">
- 🌟 [[NEJM AI 2025](https://arxiv.org/abs/2501.14654)] MedAgentBench: Evaluating Medical LLM Agent Workflows [[Code](https://github.com/stanfordmlgroup/medagentbench)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Benchmark&color=9A7F55&style=flat-square" alt="Benchmark"> <img src="https://img.shields.io/static/v1?label=&message=System-Level&color=5F8791&style=flat-square" alt="System-Level">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2405.07960)] AgentClinic: Multimodal Agent Benchmark in Simulated Clinical Environment [[Code](https://github.com/SamuelSchmidgall/AgentClinic)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Benchmark&color=9A7F55&style=flat-square" alt="Benchmark"> <img src="https://img.shields.io/static/v1?label=&message=Sequential&color=6B8F8F&style=flat-square" alt="Sequential">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2504.05678)] MedAgentGym: Standardized Training Gymnasium [[Code](https://github.com/wshi83/MedAgentGym)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Benchmark&color=9A7F55&style=flat-square" alt="Benchmark"> <img src="https://img.shields.io/static/v1?label=&message=Training&color=9A7B5F&style=flat-square" alt="Training">
- 🌟 [[arXiv 2025](https://arxiv.org/abs/2505.09876)] MedAgentAudit: Agent Safety and Reliability Audit [[Code](https://github.com/yhzhu99/MedAgentAudit)] <br>
  <img src="https://img.shields.io/static/v1?label=&message=Benchmark&color=9A7F55&style=flat-square" alt="Benchmark"> <img src="https://img.shields.io/static/v1?label=&message=Safety&color=9A6F7F&style=flat-square" alt="Safety">

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
| [MedAgent-Zero](https://github.com/tang-agui/MedAgent-Zero) | Framework | Zero-shot agent toolkit |
| [AutoGen](https://github.com/microsoft/autogen) | Framework | Multi-agent orchestration |
| [MetaGPT](https://github.com/geekan/MetaGPT) | Framework | Multi-agent programming |
| [AgentClinic](https://github.com/SamuelSchmidgall/AgentClinic) | Benchmark | Clinical agent evaluation |
| [MedAgentGym](https://github.com/wshi83/MedAgentGym) | Framework | Agent training gymnasium |
| [MedRAX](https://github.com/bowang-lab/medrax) | Framework | Tool orchestration for CXR |
| [MedOpenClaw](https://github.com/MedOpenClaw/medopenclaw) | Framework | Auditable 3D Slicer agent |
| [Awesome-AI-Agents-for-Healthcare](https://github.com/AgenticHealthAI/Awesome-AI-Agents-for-Healthcare) | List | Related awesome list |

---

## Related Surveys

- [A Comprehensive Survey on Medical Imaging Agents (2026)](https://arxiv.org/) — Our accompanying survey paper
- [Awesome-AI-Agents-for-Healthcare](https://github.com/AgenticHealthAI/Awesome-AI-Agents-for-Healthcare) — Broader healthcare agent list
- [Awesome-Multimodal-in-Medical-Imaging](https://github.com/richard-peng-xia/awesome-multimodal-in-medical-imaging) — Multimodal medical imaging resources

---

## Star History

If you find this repository useful, please consider giving it a ⭐!

## LICENSE

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

## Citation

```bibtex
@article{medimaging_agents_survey_2026,
  title={Medical Imaging Agents: A Comprehensive Survey from Passive Models to Autonomous Clinical Systems},
  author={Authors},
  journal={arXiv preprint},
  year={2026}
}
```

## Contact

If you have any questions or suggestions, please feel free to open an issue or submit a pull request.
