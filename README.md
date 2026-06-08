# From Language Models to Agentic Foundation Models: Architecture, Data, Environments, Rewards, Training, Agentic RL Infra, and Harnesses

作者：codex, darwin.mathsfan@gmail.com  
版本：`v0.1.0`

本仓库保存一篇关于 **Agentic Foundation Models（AFMs，智能体基础模型）** 的综述论文第一版公开草稿。

English version: [English README](#english-readme).

## 推荐阅读路径

当前 `v0.1.0` 是第一版公开草稿。就这一版而言，**建议优先阅读社区发布版本**：

- 社区发布版本：[`community/community-post.md`](community/community-post.md)
- 社区发布 PDF：[`community/community-post.pdf`](community/community-post.pdf)

社区发布版本已经针对读者体验做了更强的结构化整理，更适合作为了解本文核心观点、AFM Formation Stack 和整体技术框架的入口。

论文版目前主要作为完整草稿快照和后续版本演进的基线，用于保存完整章节、引用、图表和版本记录。由于第一版论文正文仍处于早期草稿阶段，**暂时建议只作为参考材料，不建议作为主要阅读入口或逐段精读对象**。后续版本会继续打磨论文正文、引用质量和章节衔接。

相关文件：

- Release PDF：[`releases/v0.1.0/agentic-foundation-model-survey-v0.1.0.pdf`](releases/v0.1.0/agentic-foundation-model-survey-v0.1.0.pdf)
- 最新论文 PDF：[`paper/agentic-foundation-model-survey.pdf`](paper/agentic-foundation-model-survey.pdf)
- 最新论文 Markdown：[`paper/agentic-foundation-model-survey.md`](paper/agentic-foundation-model-survey.md)
- 引用文件：[`references/references.bib`](references/references.bib)

## 核心理念

这篇综述的核心观点是：Agentic Foundation Model 不是简单地“给语言模型套一层工具调用”，也不是单纯的“更强推理模型”。AFM 更应该被理解为一套 **AFM Formation Stack（智能体基础模型形成栈）**：它通过模型结构、数据链路、交互环境、奖励/验证器系统、训练流水线、Agentic RL 基础设施、运行时 harness，以及特定场景适配，共同塑造模型的 agentic 能力。

本文的中心论点是：

> Agentic 能力来自长程模型底座、agentic 轨迹数据、交互式环境、奖励/验证器系统、后训练流水线、可扩展 Agentic RL Infra，以及运行时 harness 的协同设计。

这个框架明确区分三个容易混淆的层次：

- **Agentic Foundation Model**：训练出来的模型本体，以及模型内部学到的 agentic 能力。
- **Agent Harness / Product Runtime**：让模型在真实产品或任务中运行的系统，包括工具、上下文、权限、状态、记忆、执行和反馈闭环。
- **Scenario Agent**：面向具体场景落地的 agent，例如 coding、deep research、GUI/computer-use、办公生产力、数据分析和 multi-agent co-work。

## AFM Formation Stack 与论文结构

| 章节 | 在 AFM Formation Stack 中的作用 | 主要子主题 |
|---|---|---|
| 1. Introduction | 说明为什么需要把 AFM 看成一个 training-and-systems paradigm。 | 从语言模型到 AFM；agentic 能力为何是训练和系统问题；证据碎片化；本文贡献；范围和边界。 |
| 2. Definitions, Capabilities, and Evaluation Boundaries | 建立全文的概念和边界定义。 | AFM 工作定义；agentic 能力分类；model/environment/harness/product/scenario agent 边界；benchmark capability vs product capability；证据强度。 |
| 3. Related Work and Literature Review | 按 AFM formation 的视角重新组织已有相关工作。 | LLM agent 综述；tool-use/action model；agent benchmark；agentic RL；reward model；RL infra；GUI/computer-use/deep research/multi-agent 综述。 |
| 4. Model Architecture for Agentic Inference | 解释支持 long-horizon agentic workload 的模型结构底座。 | 长上下文；KV/cache-aware model design；sparse/linear/hybrid attention；MoE 和 active compute；agentic inference pattern；architecture-serving co-design；模型族证据。 |
| 5. Data Pipeline | 解释数据如何从静态语料演化为 agentic trajectories。 | Foundation data；agentic CPT 和 mid-training；demonstration/cold-start trajectory；synthetic trajectory；RL rollout data；过滤、难度控制和泄漏控制；data flywheel。 |
| 6. Agentic Environments | 讨论训练和评测中使用的交互式任务环境。 | Environment schema；可验证性谱系；强可验证环境；半可验证环境；GUI/product-like environment；环境生成和扩展；training environment vs evaluation harness。 |
| 7. Reward and Verifier Systems | 研究如何把环境反馈转化为可训练信号。 | Reward granularity；rule/outcome verifier；execution/state verifier；format reward；process/trajectory reward；judge/generative verifier；治理信号；reward hacking。 |
| 8. Training Pipeline | 把 agentic post-training 放到 AFM 完整训练生命周期中分析。 | Pretraining priors；agentic CPT；SFT/cold start；preference/RFT；RLVR 和 agentic RL；domain/mixed/general RL；distillation/unification/self-evolution；模型族训练披露。 |
| 9. Agentic RL Infra | 解释为什么多轮 agentic RL 需要新的基础设施。 | 新 infra 的必要性；rollout orchestration；sandbox/env pool；reward service；trajectory storage；trainer-inference disaggregation；staleness；KV reuse；可观测性和成本。 |
| 10. Mainstream Agentic Foundation Model Landscape | 用 formation-stack 视角横向比较主流模型路线。 | 比较协议；architecture/inference strategy；data/env strategy；reward/training strategy；RL infra 和 harness 披露；路线分类；开放/闭源披露缺口。 |
| 11. Agent Harness and Product Runtime | 区分 product runtime 证据和 model training 证据。 | Harness 定义；tool registry/connectors/MCP；context 和 lifecycle management；sandbox、permission 和 governance；observability 和 badcase triage；telemetry；harness-vs-training 边界。 |
| 12. From AFMs to Scenario Agents | 说明 AFM 如何变成具体场景 agent。 | Scenario-agent formula；coding/SWE agent；search/deep research agent；GUI/computer-use agent；office/productivity agent；data/SQL/scientific/MLE agent；multi-agent co-work；跨场景对比。 |
| 13. Open Problems | 总结当前仍未解决的科学和工程问题。 | 披露和可复现缺口；非 coding 场景验证；long-horizon credit assignment；环境可靠性、安全和成本；harness 泛化；benchmark contamination；治理信号；Agentic RL 计算瓶颈。 |
| 14. Future Directions | 展望 AFM 后续研究和系统演进方向。 | Multi-agent co-work；multimodal AFM；更广泛真实世界落地；long-horizon memory/checkpointing；self-evolving loops；标准化评测和可复现 infra。 |
| 15. Conclusion | 总结 AFM formation stack 和研究路线图。 | Formation stack 总结；AFM、harness 和 scenario agent 的区别；research roadmap。 |

## 本综述希望贡献什么

这篇草稿面向希望系统理解 AFM 方向的研究者、工程师和基础设施建设者。

主要贡献包括：

- 提出一种以 formation stack 为核心的 Agentic Foundation Model 分析框架。
- 区分模型训练、环境设计、奖励/验证器系统、RL 基础设施和产品 harness。
- 为主流 AFM 模型族和场景 agent 提供横向比较框架。
- 建立证据边界，区分论文明确披露、官方 runtime 证据、本地综合和谨慎推断。
- 总结 multi-agent、multimodal、long-horizon 和真实世界 agentic system 的未来研究路线。

## 证据边界

本文对不同类型的 claim 使用不同证据等级：

- 论文和技术报告用于支持其中明确披露的 architecture、data、reward、training 和 infrastructure claim。
- 官方产品文档、system card 和 runtime blog 主要用于支持 product/runtime/harness claim。
- 本地综合只作为组织和归纳材料，不能替代公开证据。
- 推断性内容会使用谨慎表述，不会写成已经披露的训练 recipe。

尤其是，长上下文和基础设施导向的模型报告会被作为 model-system substrate 的证据，而不会自动被当成完整 agent training recipe 的披露。

## 仓库结构

```text
paper/
  agentic-foundation-model-survey.md
  agentic-foundation-model-survey.pdf

community/
  community-post.md
  community-post.pdf

assets/
  figures/gptimage/

references/
  references.bib

releases/
  v0.1.0/
```

## 版本管理策略

本仓库保留两类论文产物：

- `paper/`：最新的可编辑/公开版本。
- `releases/vX.Y.Z/`：不可变的版本快照。

当前第一版公开快照是：

- `v0.1.0`：initial public draft。

后续更新应创建新的 release 目录，例如 `releases/v0.2.0/`，同时让 `paper/` 始终保存最新工作版本。

## 当前状态

这是早期公开草稿。欢迎反馈，尤其是：

- 是否遗漏或错误分类了 AFM 模型族证据，
- Agentic RL Infra 系统是否覆盖充分，
- Reward/verifier taxonomy 是否合理，
- Scenario agent 对比是否完整，
- Model training 和 product runtime 之间的证据边界是否清晰。

---

# English README

Authors: codex, darwin.mathsfan@gmail.com  
Version: `v0.1.0`

This repository hosts the first public draft of a survey paper on **Agentic Foundation Models (AFMs)**.

## Recommended Reading Path

The current `v0.1.0` release is an early public draft. For this version, **we recommend starting with the community post**:

- Community post: [`community/community-post.md`](community/community-post.md)
- Community post PDF: [`community/community-post.pdf`](community/community-post.pdf)

The community post has been more carefully structured for reader experience and is the best entry point for understanding the core thesis, the AFM Formation Stack, and the overall technical framework.

The paper version is currently maintained as a full draft snapshot and versioning baseline. It preserves the complete chapter structure, references, figures, and release record. Since the first paper draft is still at an early stage, **we recommend treating it as reference material rather than the primary reading path or a section-by-section reading target**. Future versions will continue to improve the paper prose, citation quality, and chapter coherence.

Related files:

- Release PDF: [`releases/v0.1.0/agentic-foundation-model-survey-v0.1.0.pdf`](releases/v0.1.0/agentic-foundation-model-survey-v0.1.0.pdf)
- Latest paper PDF: [`paper/agentic-foundation-model-survey.pdf`](paper/agentic-foundation-model-survey.pdf)
- Latest paper Markdown: [`paper/agentic-foundation-model-survey.md`](paper/agentic-foundation-model-survey.md)
- References: [`references/references.bib`](references/references.bib)

## Core Idea

This survey argues that an Agentic Foundation Model is not merely a language model wrapped by tools, nor simply a reasoning model with stronger test-time computation. Instead, AFMs should be understood through an **AFM Formation Stack**: a training-and-systems stack that jointly shapes agentic capabilities through model architecture, data, environments, rewards, training, RL infrastructure, harnesses, and scenario-specific adaptation.

The central thesis is:

> Agentic capability emerges from the co-design of long-horizon model substrates, agentic trajectory data, interactive environments, reward/verifier systems, post-training pipelines, scalable agentic RL infrastructure, and runtime harnesses.

This framing separates three often-confused layers:

- **Agentic Foundation Model**: the trained model and its learned agentic capabilities.
- **Agent Harness / Product Runtime**: the runtime system that manages tools, context, permissions, state, memory, execution, and product feedback.
- **Scenario Agent**: a deployed agent for a specific domain such as coding, deep research, GUI/computer-use, productivity, data analysis, or multi-agent co-work.

## AFM Formation Stack and Paper Structure

| Chapter | Role in the AFM Formation Stack | Main Subtopics |
|---|---|---|
| 1. Introduction | Defines the motivation for AFMs as a training-and-systems paradigm. | From LMs to AFMs; agentic capability as a training-and-systems problem; fragmented evidence; survey contributions; scope and boundaries. |
| 2. Definitions, Capabilities, and Evaluation Boundaries | Establishes the conceptual vocabulary used throughout the survey. | AFM definition; capability taxonomy; model/environment/harness/product/scenario boundaries; benchmark vs product capability; evidence strength. |
| 3. Related Work and Literature Review | Reorganizes prior work around AFM formation rather than isolated agent frameworks. | LLM agent surveys; tool-use/action models; benchmarks; agentic RL; reward models; RL infra; GUI/computer-use/deep research/multi-agent surveys. |
| 4. Model Architecture for Agentic Inference | Explains the model-side substrate needed for long-horizon agentic work. | Long context; KV/cache-aware design; sparse/linear/hybrid attention; MoE and active compute; agentic inference patterns; architecture-serving co-design; model-family evidence. |
| 5. Data Pipeline | Covers how static corpora evolve into agentic trajectories. | Foundation data; agentic CPT and mid-training; demonstrations; synthetic trajectories; RL rollout data; filtering and difficulty control; data flywheels. |
| 6. Agentic Environments | Describes the interactive task worlds used for training and evaluation. | Environment schema; verifiability spectrum; strongly verifiable environments; semi-verifiable environments; GUI/product-like environments; environment generation; training env vs eval harness. |
| 7. Reward and Verifier Systems | Studies how environment feedback becomes trainable signals. | Reward granularity; rule/outcome verifiers; execution/state verifiers; format rewards; process/trajectory rewards; judge and generative verifiers; governance signals; reward hacking. |
| 8. Training Pipeline | Places agentic post-training inside the full AFM training lifecycle. | Pretraining priors; agentic CPT; SFT/cold start; preference/RFT; RLVR and agentic RL; domain/mixed/general RL; distillation/unification/self-evolution; disclosure across model families. |
| 9. Agentic RL Infra | Explains the infrastructure required to scale multi-turn agentic RL. | Why new infra is needed; rollout orchestration; sandbox/env pools; reward services; trajectory storage; trainer-inference disaggregation; staleness; KV reuse; observability and cost. |
| 10. Mainstream Agentic Foundation Model Landscape | Compares major model-family routes using the formation-stack lens. | Comparison protocol; architecture/inference strategies; data/env strategies; reward/training strategies; RL infra and harness disclosure; route taxonomy; open/closed disclosure gaps. |
| 11. Agent Harness and Product Runtime | Separates product runtime evidence from model training evidence. | Harness definition; tool registries/connectors/MCP; context and lifecycle management; sandboxing and permissions; observability and badcase triage; telemetry; harness-vs-training boundary. |
| 12. From AFMs to Scenario Agents | Shows how AFMs become domain-specific agents. | Scenario-agent formula; coding/SWE agents; search/deep research agents; GUI/computer-use agents; productivity agents; data/SQL/scientific/MLE agents; multi-agent co-work; cross-scenario comparison. |
| 13. Open Problems | Summarizes unresolved technical and scientific challenges. | Disclosure gaps; non-coding verification; long-horizon credit assignment; environment reliability/security/cost; harness generalization; benchmark contamination; governance signals; compute bottlenecks. |
| 14. Future Directions | Outlines likely next steps for AFM research and systems. | Multi-agent co-work; multimodal AFMs; real-world deployment; long-horizon memory/checkpointing; self-evolving loops; standardized evaluation and reproducible infra. |
| 15. Conclusion | Recaps the AFM formation stack and research roadmap. | Stack summary; AFM vs harness vs scenario agents; research roadmap. |

## What This Survey Tries to Contribute

This draft is intended to be useful for researchers, engineers, and infrastructure builders who want a structured map of the emerging AFM space.

The survey contributes:

- A formation-stack view of Agentic Foundation Models.
- A separation between model training, environment design, reward/verifier systems, RL infrastructure, and product harnesses.
- A comparison framework for mainstream AFM model families and scenario agents.
- An evidence discipline for distinguishing disclosed facts, official runtime evidence, local synthesis, and cautious inference.
- A roadmap for future work on multi-agent, multimodal, long-horizon, and real-world agentic systems.

## Evidence Discipline

The paper uses different evidence levels for different kinds of claims:

- Technical papers and reports support architecture, data, reward, training, and infrastructure claims when explicitly disclosed.
- Official product documents, system cards, and runtime blogs support product/runtime/harness claims.
- Local synthesis is used as secondary organization, not as a replacement for public evidence.
- Inference is stated cautiously and is not presented as disclosed training recipe.

In particular, long-context and infrastructure-oriented model reports are treated as evidence for model-system substrate design, not automatically as full agent-training recipe disclosures.

## Repository Layout

```text
paper/
  agentic-foundation-model-survey.md
  agentic-foundation-model-survey.pdf

community/
  community-post.md
  community-post.pdf

assets/
  figures/gptimage/

references/
  references.bib

releases/
  v0.1.0/
```

## Versioning Policy

The repository keeps two kinds of paper artifacts:

- `paper/`: latest editable/public copy.
- `releases/vX.Y.Z/`: immutable release snapshots.

The current first public snapshot is:

- `v0.1.0`: initial public draft.

Future updates should create a new release directory, for example `releases/v0.2.0/`, while keeping the latest working version in `paper/`.

## Status

This is an early public draft. Feedback is welcome, especially on:

- missing or misclassified AFM model-family evidence,
- agentic RL infrastructure systems,
- reward/verifier taxonomies,
- scenario-agent comparisons,
- evidence boundaries between model training and product runtime.
