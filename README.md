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

## 推荐论文阅读列表

本文整理和引用了约 118 篇论文、技术报告、system card 和官方工程文章。README 中不重复完整 bibliography，而是给出一份按 **AFM Formation Stack** 组织的推荐阅读路径。完整引用列表见：

- [`references/references.bib`](references/references.bib)
- [`paper/agentic-foundation-model-survey.md#references`](paper/agentic-foundation-model-survey.md#references)

如果只想快速理解本文框架，建议先读 **P0 必读主线**；如果要深入某个技术模块，再按主题阅读后续列表。

### P0 必读主线

这些材料最能支撑本文的核心问题：AFM 为什么不是单一模型能力，而是一套由模型结构、数据、环境、奖励、训练、RL infra 和 harness 共同形成的技术栈。

- [Agentic AI: A Comprehensive Survey of Architectures, Applications, and Future Directions](https://arxiv.org/abs/2510.25445)
- [Agentic Large Language Models, a Survey](https://arxiv.org/abs/2503.23037)
- [The Landscape of Agentic Reinforcement Learning for LLMs: A Survey](https://arxiv.org/abs/2509.02547)
- [DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning](https://arxiv.org/abs/2501.12948)
- [DeepSeek-V3 Technical Report](https://arxiv.org/abs/2412.19437)
- [DeepSeek-V3.2: Pushing the Frontier of Open Large Language Models](https://arxiv.org/abs/2512.02556)
- [DeepSeek-V4: Towards Highly Efficient Million-Token Context Intelligence](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro)
- [GLM-4.5: Agentic, Reasoning, and Coding Foundation Models](https://arxiv.org/abs/2508.06471)
- [GLM-5: from Vibe Coding to Agentic Engineering](https://arxiv.org/abs/2602.15763)
- [Kimi K2: Open Agentic Intelligence](https://arxiv.org/abs/2507.20534)
- [Kimi-Researcher: End-to-End RL Training for Emerging Agentic Capabilities](https://moonshotai.github.io/Kimi-Researcher/)
- [Qwen3](https://qwenlm.github.io/blog/qwen3/)
- [Qwen3-Coder-Next Technical Report](https://arxiv.org/abs/2603.00729)
- [The MiniMax-M2 Series: Mini Activations Unleashing Max Real-World Intelligence](https://arxiv.org/abs/2605.26494)
- [Tongyi DeepResearch Technical Report](https://arxiv.org/abs/2510.24701)
- [Agent Lightning: Train ANY AI Agents with Reinforcement Learning](https://arxiv.org/abs/2508.03680)
- [AgentRL: Scaling Agentic Reinforcement Learning with a Multi-Turn, Multi-Task Framework](https://arxiv.org/abs/2510.04206)
- [AgentGym-RL: Training LLM Agents for Long-Horizon Decision Making through Multi-Turn Reinforcement Learning](https://arxiv.org/abs/2509.08755)
- [AReaL-SEA: Self-Evolving Agents with Verifiable Rewards](https://arxiv.org/abs/2601.22607)
- [Reward Model Survey: A Comprehensive Survey of Reward Models: Taxonomy, Applications, Challenges, and Future](https://arxiv.org/abs/2504.12328)
- [Agent Harness Engineering: A Survey](https://openreview.net/forum?id=3hXEPbG0dh)
- [Effective Harnesses for Long-Running Agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- [Harness Engineering](https://openai.com/index/harness-engineering/)
- [SWE-bench: Can Language Models Resolve Real-World GitHub Issues?](https://arxiv.org/abs/2310.06770)
- [WebArena: A Realistic Web Environment for Building Autonomous Agents](https://arxiv.org/abs/2307.13854)
- [OSWorld: Benchmarking Multimodal Agents for Open-Ended Tasks in Real Computer Environments](https://arxiv.org/abs/2404.07972)
- [GAIA: A Benchmark for General AI Assistants](https://arxiv.org/abs/2311.12983)

### Survey / Overview

先读这些材料，可以建立 agentic AI、agentic LLM、agentic RL、deep research、GUI/OS agent 和 harness 的全局地图。

- [Agentic AI Frameworks: Architectures, Protocols, and Design Challenges](https://arxiv.org/abs/2508.10146)
- [Agentic AI Needs a Systems Theory](https://arxiv.org/abs/2503.00237)
- [Agentic AI Workload Characteristics](https://arxiv.org/abs/2605.26297)
- [Deep Research Agents: A Systematic Examination and Roadmap](https://arxiv.org/abs/2506.18096)
- [Reinforcement Learning Foundations for Deep Research Systems: A Survey](https://arxiv.org/abs/2509.06733)
- [Large Language Model-Brained GUI Agents: A Survey](https://arxiv.org/abs/2411.18279)
- [OS Agents: A Survey on MLLM-based Agents for Computer, Phone and Browser Use](https://arxiv.org/abs/2508.04482)
- [Agent Harness for Large Language Model Agents: A Survey](https://www.preprints.org/manuscript/202604.0428)

### Model Architecture and Agentic Inference

这一组用于理解为什么 AFM 需要长上下文、cache-aware inference、hybrid attention、MoE/active compute，以及模型结构和 serving infra 的协同设计。

- [DeepSeek-V4: Towards Highly Efficient Million-Token Context Intelligence](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro)
- [DeepSeek-V3 Technical Report](https://arxiv.org/abs/2412.19437)
- [DeepSeek-V3.2: Pushing the Frontier of Open Large Language Models](https://arxiv.org/abs/2512.02556)
- [Kimi K2: Open Agentic Intelligence](https://arxiv.org/abs/2507.20534)
- [Kimi K2.5: Visual Agentic Intelligence](https://arxiv.org/abs/2602.02276)
- [GLM-4.5: Agentic, Reasoning, and Coding Foundation Models](https://arxiv.org/abs/2508.06471)
- [vLLM: Easy, Fast, and Cheap LLM Serving with PagedAttention](https://arxiv.org/abs/2309.06180)
- [LMCache: An Efficient KV Cache Layer for Enterprise-Scale LLM Inference](https://arxiv.org/abs/2510.09665)
- [TokenCake: A KV-Cache-centric Serving Framework for LLM-based Multi-Agent Applications](https://arxiv.org/abs/2510.18586)
- [ThunderAgent: A Simple, Fast and Program-Aware Agentic Inference System](https://arxiv.org/abs/2602.13692)
- [Continuum: Efficient and Robust Multi-Turn LLM Agent Scheduling with KV Cache Time-to-Live](https://arxiv.org/abs/2511.02230)

### Data Pipeline and Agentic Trajectory Construction

这一组用于理解 agentic data 如何从静态语料、工具调用数据、合成任务、环境轨迹和 rollout data 逐步形成。

- [A Survey of LLM-driven Synthetic Data Generation, Curation, and Evaluation](https://arxiv.org/abs/2406.15126)
- [APIGen: Automated Pipeline for Generating Verifiable and Diverse Function-Calling Datasets](https://arxiv.org/abs/2406.18518)
- [EnvFactory: Scaling Tool-Use Agents via Executable Environments Synthesis and Robust RL](https://arxiv.org/abs/2605.18703)
- [WebExplorer: Explore and Evolve for Training Long-Horizon Web Agents](https://arxiv.org/abs/2509.06501)
- [WebShaper: Agentically Data Synthesizing via Information-Seeking Formalization](https://arxiv.org/abs/2507.15061)
- [Tool-R0: Self-Evolving LLM Agents for Tool-Learning from Zero Data](https://arxiv.org/abs/2602.21320)
- [FlowAgent: Tools as Continuous Flow for Evolving Agentic Reasoning](https://arxiv.org/abs/2605.07339)

### Agentic Environments and Benchmarks

这一组用于理解 training environment、evaluation harness、strong verifier、semi-verifiable environment 和 product-like environment 的差异。

- [AgentBench: Evaluating LLMs as Agents](https://arxiv.org/abs/2308.03688)
- [SWE-bench: Can Language Models Resolve Real-World GitHub Issues?](https://arxiv.org/abs/2310.06770)
- [SWE-agent: Agent-Computer Interfaces Enable Automated Software Engineering](https://arxiv.org/abs/2405.15793)
- [OpenHands: An Open Platform for AI Software Developers as Generalist Agents](https://arxiv.org/abs/2407.16741)
- [R2E-Gym: Procedural Environments and Hybrid Verifiers for Scaling Open-Weights SWE Agents](https://arxiv.org/abs/2504.07164)
- [WebArena: A Realistic Web Environment for Building Autonomous Agents](https://arxiv.org/abs/2307.13854)
- [OSWorld: Benchmarking Multimodal Agents for Open-Ended Tasks in Real Computer Environments](https://arxiv.org/abs/2404.07972)
- [OpenComputer: Verifiable Software Worlds for Computer-Use Agents](https://arxiv.org/abs/2605.19769)
- [TheAgentCompany: Benchmarking LLM Agents on Consequential Real World Tasks](https://arxiv.org/abs/2412.14161)
- [tau-bench: A Benchmark for Tool-Agent-User Interaction in Real-World Domains](https://arxiv.org/abs/2406.12045)

### Reward and Verifier Systems

这一组用于理解从 unit test、rule verifier、state verifier 到 rubric、judge、generative verifier 的奖励系统谱系。

- [A Comprehensive Survey of Reward Models: Taxonomy, Applications, Challenges, and Future](https://arxiv.org/abs/2504.12328)
- [Generative Verifiers: Reward Modeling as Next-Token Prediction](https://arxiv.org/abs/2408.15240)
- [Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains](https://arxiv.org/abs/2507.17746)
- [AutoRubric: Scaling Rubric-Based Evaluation and Reward Modeling](https://arxiv.org/abs/2603.00077)
- [Agent-RLVR: Training Software Engineering Agents via Guidance and Environment Rewards](https://arxiv.org/abs/2506.11425)
- [R1-Code-Interpreter: Training Code Interpreter Tool Use via Multi-Turn SFT and RL](https://arxiv.org/abs/2505.21668)
- [SandboxEval: Towards Securing Test Environment for Untrusted Code](https://arxiv.org/abs/2504.00018)

### Training Pipeline and Agentic RL

这一组用于理解从 pretraining、agentic CPT、SFT/cold start、preference/RFT、RLVR，到 domain/mixed/general RL、distillation/unification/self-evolution 的训练链路。

- [DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning](https://arxiv.org/abs/2501.12948)
- [DAPO: An Open-Source LLM Reinforcement Learning System at Scale](https://arxiv.org/abs/2503.14476)
- [Reinforcement Learning for Large Reasoning Models: A Survey](https://arxiv.org/abs/2509.08827)
- [Agent Lightning: Train ANY AI Agents with Reinforcement Learning](https://arxiv.org/abs/2508.03680)
- [AgentRL: Scaling Agentic Reinforcement Learning with a Multi-Turn, Multi-Task Framework](https://arxiv.org/abs/2510.04206)
- [AgentGym-RL: Training LLM Agents for Long-Horizon Decision Making through Multi-Turn Reinforcement Learning](https://arxiv.org/abs/2509.08755)
- [AReaL-SEA: Self-Evolving Agents with Verifiable Rewards](https://arxiv.org/abs/2601.22607)
- [Tool-R0: Self-Evolving LLM Agents for Tool-Learning from Zero Data](https://arxiv.org/abs/2602.21320)
- [WebRL: Training LLM Web Agents via Self-Evolving Online Curriculum Reinforcement Learning](https://arxiv.org/abs/2411.02337)
- [Toward Training Superintelligent Software Agents through Self-Play SWE-RL](https://arxiv.org/abs/2512.18552)

### Agentic RL Infra

这一组用于理解为什么传统 RLHF/RLVR infra 不足以支撑多轮 agentic rollout，以及 agentic RL infra 如何围绕 rollout、sandbox、reward service、trajectory store、weight sync、staleness 和 KV reuse 演进。

- [OpenRLHF: An Easy-to-use, Scalable and High-performance RLHF Framework](https://aclanthology.org/2025.acl-demo.3/)
- [ReaLHF: Optimized RLHF Training for Large Language Models through Parameter Reallocation](https://arxiv.org/abs/2406.14088)
- [HybridFlow: A Flexible and Efficient RLHF Framework](https://arxiv.org/abs/2409.19256)
- [AReaL: A Large-Scale Asynchronous Reinforcement Learning System for Language Reasoning](https://arxiv.org/abs/2505.24298)
- [AReaL-DTA: Dynamic Tree Attention for Efficient RL Training](https://arxiv.org/abs/2602.00482)
- [ROLL: A Flexible, Efficient and User-Friendly Large-Scale Reinforcement Learning Framework](https://arxiv.org/abs/2506.06122)
- [RollArt and RollArc: Disaggregated Agentic RL Infrastructure](https://arxiv.org/abs/2512.22560)
- [ROSE: Rollout On Serving GPUs via Cooperative Elasticity for Agentic RL](https://arxiv.org/abs/2605.06534)
- [OpenTinker: An Agentic RL Infrastructure](https://arxiv.org/abs/2601.07376)
- [RLFactory: A Unified Reinforcement Learning Framework for LLM Agents](https://arxiv.org/abs/2509.06980)
- [ProRL Agent: Rollout-as-a-Service for RL Training of Multi-Turn LLM Agents](https://arxiv.org/abs/2603.18815)
- [A-3PO: Staleness-aware Proximal Policy Approximation](https://arxiv.org/abs/2512.06547)

### Agent Harness and Product Runtime

这一组用于理解 product harness、tool interface、context/state management、permission/sandbox、telemetry、eval 和 badcase triage。它们主要支撑 runtime/product evidence，不能直接当作未披露的训练 recipe。

- [Agent Harness Engineering: A Survey](https://openreview.net/forum?id=3hXEPbG0dh)
- [Agent Harness for Large Language Model Agents: A Survey](https://www.preprints.org/manuscript/202604.0428)
- [Code as Agent Harness](https://arxiv.org/abs/2605.18747)
- [Building Effective AI Agents](https://www.anthropic.com/engineering/building-effective-agents)
- [Effective Harnesses for Long-Running Agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- [Harness Design for Long-Running Application Development](https://www.anthropic.com/engineering/harness-design-long-running-apps)
- [Harness Engineering](https://openai.com/index/harness-engineering/)
- [Computer-Using Agent](https://openai.com/index/computer-using-agent/)
- [ChatGPT Agent System Card](https://openai.com/index/chatgpt-agent-system-card/)
- [Operator System Card](https://openai.com/index/operator-system-card/)
- [Introducing the Gemini 2.5 Computer Use Model](https://blog.google/technology/google-deepmind/gemini-computer-use-model/)
- [Writing Effective Tools for AI Agents](https://www.anthropic.com/engineering/writing-tools-for-agents)

### Scenario Agents

这一组用于理解 AFM 如何通过场景数据、环境、奖励、RL infra 和 harness 组合成 coding、deep research、GUI/computer-use、data/SQL/MLE 和 multi-agent 等具体 agent。

- [DeepSWE: Training a Fully Open-Sourced Coding Agent by Scaling RL](https://www.together.ai/blog/deepswe)
- [SWE-RL: Advancing LLM Reasoning via Reinforcement Learning on Open Software Evolution](https://arxiv.org/abs/2502.18449)
- [KAT-Coder-V2](https://arxiv.org/abs/2603.27703)
- [Qwen3-Coder: Agentic Coding in the World](https://qwenlm.github.io/blog/qwen3-coder/)
- [WebDancer: Towards Autonomous Information Seeking Agency](https://arxiv.org/abs/2505.22648)
- [WebSailor: Navigating Super-human Reasoning for Web Agent](https://arxiv.org/abs/2507.02592)
- [WebSailor-V2: Bridging the Chasm to Proprietary Agents via Synthetic Data and Scalable RL Training](https://arxiv.org/abs/2509.13305)
- [WebAgent-R1: Training Web Agents via End-to-End Multi-Turn Reinforcement Learning](https://arxiv.org/abs/2505.16421)
- [Agent S2: A Compositional Generalist-Specialist Framework for Computer Use Agents](https://arxiv.org/abs/2504.00906)
- [ToolCUA: GUI-Tool Path Orchestration for Computer Use Agents](https://arxiv.org/abs/2605.12481)
- [Microsoft Magma: A Foundation Model for Multimodal AI Agents](https://arxiv.org/abs/2502.13130)
- [SQL-R1: Training Natural Language to SQL Reasoning Model By Reinforcement Learning](https://arxiv.org/abs/2504.08600)
- [ML-Agent: Reinforcing LLM Agents for Autonomous Machine Learning Engineering](https://arxiv.org/abs/2505.23723)
- [AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation](https://arxiv.org/abs/2308.08155)
- [Magentic-One: A Generalist Multi-Agent System for Solving Complex Tasks](https://arxiv.org/abs/2411.04468)
- [Multi-Agent Computer Use](https://arxiv.org/abs/2606.01533)

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

## Recommended Reading List

This survey collects and cites about 118 papers, technical reports, system cards, and official engineering articles. Instead of duplicating the full bibliography in the README, this section provides a recommended reading path organized around the **AFM Formation Stack**. The complete reference list is available at:

- [`references/references.bib`](references/references.bib)
- [`paper/agentic-foundation-model-survey.md#references`](paper/agentic-foundation-model-survey.md#references)

If you only want to understand the main framework, start with the **P0 Core Reading Path**. If you want to go deeper into a specific technical pillar, continue with the topic-specific lists below.

### P0 Core Reading Path

These materials best support the central argument of this survey: AFM capability is not a single model property, but the result of a formation stack spanning architecture, data, environments, rewards, training, RL infra, and harnesses.

- [Agentic AI: A Comprehensive Survey of Architectures, Applications, and Future Directions](https://arxiv.org/abs/2510.25445)
- [Agentic Large Language Models, a Survey](https://arxiv.org/abs/2503.23037)
- [The Landscape of Agentic Reinforcement Learning for LLMs: A Survey](https://arxiv.org/abs/2509.02547)
- [DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning](https://arxiv.org/abs/2501.12948)
- [DeepSeek-V3 Technical Report](https://arxiv.org/abs/2412.19437)
- [DeepSeek-V3.2: Pushing the Frontier of Open Large Language Models](https://arxiv.org/abs/2512.02556)
- [DeepSeek-V4: Towards Highly Efficient Million-Token Context Intelligence](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro)
- [GLM-4.5: Agentic, Reasoning, and Coding Foundation Models](https://arxiv.org/abs/2508.06471)
- [GLM-5: from Vibe Coding to Agentic Engineering](https://arxiv.org/abs/2602.15763)
- [Kimi K2: Open Agentic Intelligence](https://arxiv.org/abs/2507.20534)
- [Kimi-Researcher: End-to-End RL Training for Emerging Agentic Capabilities](https://moonshotai.github.io/Kimi-Researcher/)
- [Qwen3](https://qwenlm.github.io/blog/qwen3/)
- [Qwen3-Coder-Next Technical Report](https://arxiv.org/abs/2603.00729)
- [The MiniMax-M2 Series: Mini Activations Unleashing Max Real-World Intelligence](https://arxiv.org/abs/2605.26494)
- [Tongyi DeepResearch Technical Report](https://arxiv.org/abs/2510.24701)
- [Agent Lightning: Train ANY AI Agents with Reinforcement Learning](https://arxiv.org/abs/2508.03680)
- [AgentRL: Scaling Agentic Reinforcement Learning with a Multi-Turn, Multi-Task Framework](https://arxiv.org/abs/2510.04206)
- [AgentGym-RL: Training LLM Agents for Long-Horizon Decision Making through Multi-Turn Reinforcement Learning](https://arxiv.org/abs/2509.08755)
- [AReaL-SEA: Self-Evolving Agents with Verifiable Rewards](https://arxiv.org/abs/2601.22607)
- [Reward Model Survey: A Comprehensive Survey of Reward Models: Taxonomy, Applications, Challenges, and Future](https://arxiv.org/abs/2504.12328)
- [Agent Harness Engineering: A Survey](https://openreview.net/forum?id=3hXEPbG0dh)
- [Effective Harnesses for Long-Running Agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- [Harness Engineering](https://openai.com/index/harness-engineering/)
- [SWE-bench: Can Language Models Resolve Real-World GitHub Issues?](https://arxiv.org/abs/2310.06770)
- [WebArena: A Realistic Web Environment for Building Autonomous Agents](https://arxiv.org/abs/2307.13854)
- [OSWorld: Benchmarking Multimodal Agents for Open-Ended Tasks in Real Computer Environments](https://arxiv.org/abs/2404.07972)
- [GAIA: A Benchmark for General AI Assistants](https://arxiv.org/abs/2311.12983)

### Survey / Overview

Start here to build a high-level map of agentic AI, agentic LLMs, agentic RL, deep research, GUI/OS agents, and harness engineering.

- [Agentic AI Frameworks: Architectures, Protocols, and Design Challenges](https://arxiv.org/abs/2508.10146)
- [Agentic AI Needs a Systems Theory](https://arxiv.org/abs/2503.00237)
- [Agentic AI Workload Characteristics](https://arxiv.org/abs/2605.26297)
- [Deep Research Agents: A Systematic Examination and Roadmap](https://arxiv.org/abs/2506.18096)
- [Reinforcement Learning Foundations for Deep Research Systems: A Survey](https://arxiv.org/abs/2509.06733)
- [Large Language Model-Brained GUI Agents: A Survey](https://arxiv.org/abs/2411.18279)
- [OS Agents: A Survey on MLLM-based Agents for Computer, Phone and Browser Use](https://arxiv.org/abs/2508.04482)
- [Agent Harness for Large Language Model Agents: A Survey](https://www.preprints.org/manuscript/202604.0428)

### Model Architecture and Agentic Inference

This group explains why AFMs need long context, cache-aware inference, hybrid attention, MoE/active compute, and architecture-serving co-design.

- [DeepSeek-V4: Towards Highly Efficient Million-Token Context Intelligence](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro)
- [DeepSeek-V3 Technical Report](https://arxiv.org/abs/2412.19437)
- [DeepSeek-V3.2: Pushing the Frontier of Open Large Language Models](https://arxiv.org/abs/2512.02556)
- [Kimi K2: Open Agentic Intelligence](https://arxiv.org/abs/2507.20534)
- [Kimi K2.5: Visual Agentic Intelligence](https://arxiv.org/abs/2602.02276)
- [GLM-4.5: Agentic, Reasoning, and Coding Foundation Models](https://arxiv.org/abs/2508.06471)
- [vLLM: Easy, Fast, and Cheap LLM Serving with PagedAttention](https://arxiv.org/abs/2309.06180)
- [LMCache: An Efficient KV Cache Layer for Enterprise-Scale LLM Inference](https://arxiv.org/abs/2510.09665)
- [TokenCake: A KV-Cache-centric Serving Framework for LLM-based Multi-Agent Applications](https://arxiv.org/abs/2510.18586)
- [ThunderAgent: A Simple, Fast and Program-Aware Agentic Inference System](https://arxiv.org/abs/2602.13692)
- [Continuum: Efficient and Robust Multi-Turn LLM Agent Scheduling with KV Cache Time-to-Live](https://arxiv.org/abs/2511.02230)

### Data Pipeline and Agentic Trajectory Construction

This group covers how agentic data evolves from static corpora, tool-use data, synthetic tasks, environment trajectories, and rollout data.

- [A Survey of LLM-driven Synthetic Data Generation, Curation, and Evaluation](https://arxiv.org/abs/2406.15126)
- [APIGen: Automated Pipeline for Generating Verifiable and Diverse Function-Calling Datasets](https://arxiv.org/abs/2406.18518)
- [EnvFactory: Scaling Tool-Use Agents via Executable Environments Synthesis and Robust RL](https://arxiv.org/abs/2605.18703)
- [WebExplorer: Explore and Evolve for Training Long-Horizon Web Agents](https://arxiv.org/abs/2509.06501)
- [WebShaper: Agentically Data Synthesizing via Information-Seeking Formalization](https://arxiv.org/abs/2507.15061)
- [Tool-R0: Self-Evolving LLM Agents for Tool-Learning from Zero Data](https://arxiv.org/abs/2602.21320)
- [FlowAgent: Tools as Continuous Flow for Evolving Agentic Reasoning](https://arxiv.org/abs/2605.07339)

### Agentic Environments and Benchmarks

This group clarifies the differences among training environments, evaluation harnesses, strong verifiers, semi-verifiable environments, and product-like environments.

- [AgentBench: Evaluating LLMs as Agents](https://arxiv.org/abs/2308.03688)
- [SWE-bench: Can Language Models Resolve Real-World GitHub Issues?](https://arxiv.org/abs/2310.06770)
- [SWE-agent: Agent-Computer Interfaces Enable Automated Software Engineering](https://arxiv.org/abs/2405.15793)
- [OpenHands: An Open Platform for AI Software Developers as Generalist Agents](https://arxiv.org/abs/2407.16741)
- [R2E-Gym: Procedural Environments and Hybrid Verifiers for Scaling Open-Weights SWE Agents](https://arxiv.org/abs/2504.07164)
- [WebArena: A Realistic Web Environment for Building Autonomous Agents](https://arxiv.org/abs/2307.13854)
- [OSWorld: Benchmarking Multimodal Agents for Open-Ended Tasks in Real Computer Environments](https://arxiv.org/abs/2404.07972)
- [OpenComputer: Verifiable Software Worlds for Computer-Use Agents](https://arxiv.org/abs/2605.19769)
- [TheAgentCompany: Benchmarking LLM Agents on Consequential Real World Tasks](https://arxiv.org/abs/2412.14161)
- [tau-bench: A Benchmark for Tool-Agent-User Interaction in Real-World Domains](https://arxiv.org/abs/2406.12045)

### Reward and Verifier Systems

This group covers the reward/verifier spectrum from unit tests, rule verifiers, and state verifiers to rubrics, judges, and generative verifiers.

- [A Comprehensive Survey of Reward Models: Taxonomy, Applications, Challenges, and Future](https://arxiv.org/abs/2504.12328)
- [Generative Verifiers: Reward Modeling as Next-Token Prediction](https://arxiv.org/abs/2408.15240)
- [Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains](https://arxiv.org/abs/2507.17746)
- [AutoRubric: Scaling Rubric-Based Evaluation and Reward Modeling](https://arxiv.org/abs/2603.00077)
- [Agent-RLVR: Training Software Engineering Agents via Guidance and Environment Rewards](https://arxiv.org/abs/2506.11425)
- [R1-Code-Interpreter: Training Code Interpreter Tool Use via Multi-Turn SFT and RL](https://arxiv.org/abs/2505.21668)
- [SandboxEval: Towards Securing Test Environment for Untrusted Code](https://arxiv.org/abs/2504.00018)

### Training Pipeline and Agentic RL

This group explains the training lifecycle from pretraining, agentic CPT, SFT/cold start, preference/RFT, and RLVR to domain/mixed/general RL, distillation, unification, and self-evolution.

- [DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning](https://arxiv.org/abs/2501.12948)
- [DAPO: An Open-Source LLM Reinforcement Learning System at Scale](https://arxiv.org/abs/2503.14476)
- [Reinforcement Learning for Large Reasoning Models: A Survey](https://arxiv.org/abs/2509.08827)
- [Agent Lightning: Train ANY AI Agents with Reinforcement Learning](https://arxiv.org/abs/2508.03680)
- [AgentRL: Scaling Agentic Reinforcement Learning with a Multi-Turn, Multi-Task Framework](https://arxiv.org/abs/2510.04206)
- [AgentGym-RL: Training LLM Agents for Long-Horizon Decision Making through Multi-Turn Reinforcement Learning](https://arxiv.org/abs/2509.08755)
- [AReaL-SEA: Self-Evolving Agents with Verifiable Rewards](https://arxiv.org/abs/2601.22607)
- [Tool-R0: Self-Evolving LLM Agents for Tool-Learning from Zero Data](https://arxiv.org/abs/2602.21320)
- [WebRL: Training LLM Web Agents via Self-Evolving Online Curriculum Reinforcement Learning](https://arxiv.org/abs/2411.02337)
- [Toward Training Superintelligent Software Agents through Self-Play SWE-RL](https://arxiv.org/abs/2512.18552)

### Agentic RL Infra

This group explains why traditional RLHF/RLVR infrastructure is not enough for multi-turn agentic rollouts, and how agentic RL infra evolves around rollout, sandboxing, reward services, trajectory stores, weight sync, staleness, and KV reuse.

- [OpenRLHF: An Easy-to-use, Scalable and High-performance RLHF Framework](https://aclanthology.org/2025.acl-demo.3/)
- [ReaLHF: Optimized RLHF Training for Large Language Models through Parameter Reallocation](https://arxiv.org/abs/2406.14088)
- [HybridFlow: A Flexible and Efficient RLHF Framework](https://arxiv.org/abs/2409.19256)
- [AReaL: A Large-Scale Asynchronous Reinforcement Learning System for Language Reasoning](https://arxiv.org/abs/2505.24298)
- [AReaL-DTA: Dynamic Tree Attention for Efficient RL Training](https://arxiv.org/abs/2602.00482)
- [ROLL: A Flexible, Efficient and User-Friendly Large-Scale Reinforcement Learning Framework](https://arxiv.org/abs/2506.06122)
- [RollArt and RollArc: Disaggregated Agentic RL Infrastructure](https://arxiv.org/abs/2512.22560)
- [ROSE: Rollout On Serving GPUs via Cooperative Elasticity for Agentic RL](https://arxiv.org/abs/2605.06534)
- [OpenTinker: An Agentic RL Infrastructure](https://arxiv.org/abs/2601.07376)
- [RLFactory: A Unified Reinforcement Learning Framework for LLM Agents](https://arxiv.org/abs/2509.06980)
- [ProRL Agent: Rollout-as-a-Service for RL Training of Multi-Turn LLM Agents](https://arxiv.org/abs/2603.18815)
- [A-3PO: Staleness-aware Proximal Policy Approximation](https://arxiv.org/abs/2512.06547)

### Agent Harness and Product Runtime

This group covers product harnesses, tool interfaces, context/state management, permissions, sandboxing, telemetry, evals, and badcase triage. These sources mainly support runtime/product evidence and should not be treated as undisclosed training recipes.

- [Agent Harness Engineering: A Survey](https://openreview.net/forum?id=3hXEPbG0dh)
- [Agent Harness for Large Language Model Agents: A Survey](https://www.preprints.org/manuscript/202604.0428)
- [Code as Agent Harness](https://arxiv.org/abs/2605.18747)
- [Building Effective AI Agents](https://www.anthropic.com/engineering/building-effective-agents)
- [Effective Harnesses for Long-Running Agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- [Harness Design for Long-Running Application Development](https://www.anthropic.com/engineering/harness-design-long-running-apps)
- [Harness Engineering](https://openai.com/index/harness-engineering/)
- [Computer-Using Agent](https://openai.com/index/computer-using-agent/)
- [ChatGPT Agent System Card](https://openai.com/index/chatgpt-agent-system-card/)
- [Operator System Card](https://openai.com/index/operator-system-card/)
- [Introducing the Gemini 2.5 Computer Use Model](https://blog.google/technology/google-deepmind/gemini-computer-use-model/)
- [Writing Effective Tools for AI Agents](https://www.anthropic.com/engineering/writing-tools-for-agents)

### Scenario Agents

This group explains how AFMs become concrete scenario agents through scenario data, environments, rewards, RL infra, and harnesses across coding, deep research, GUI/computer-use, data/SQL/MLE, and multi-agent settings.

- [DeepSWE: Training a Fully Open-Sourced Coding Agent by Scaling RL](https://www.together.ai/blog/deepswe)
- [SWE-RL: Advancing LLM Reasoning via Reinforcement Learning on Open Software Evolution](https://arxiv.org/abs/2502.18449)
- [KAT-Coder-V2](https://arxiv.org/abs/2603.27703)
- [Qwen3-Coder: Agentic Coding in the World](https://qwenlm.github.io/blog/qwen3-coder/)
- [WebDancer: Towards Autonomous Information Seeking Agency](https://arxiv.org/abs/2505.22648)
- [WebSailor: Navigating Super-human Reasoning for Web Agent](https://arxiv.org/abs/2507.02592)
- [WebSailor-V2: Bridging the Chasm to Proprietary Agents via Synthetic Data and Scalable RL Training](https://arxiv.org/abs/2509.13305)
- [WebAgent-R1: Training Web Agents via End-to-End Multi-Turn Reinforcement Learning](https://arxiv.org/abs/2505.16421)
- [Agent S2: A Compositional Generalist-Specialist Framework for Computer Use Agents](https://arxiv.org/abs/2504.00906)
- [ToolCUA: GUI-Tool Path Orchestration for Computer Use Agents](https://arxiv.org/abs/2605.12481)
- [Microsoft Magma: A Foundation Model for Multimodal AI Agents](https://arxiv.org/abs/2502.13130)
- [SQL-R1: Training Natural Language to SQL Reasoning Model By Reinforcement Learning](https://arxiv.org/abs/2504.08600)
- [ML-Agent: Reinforcing LLM Agents for Autonomous Machine Learning Engineering](https://arxiv.org/abs/2505.23723)
- [AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation](https://arxiv.org/abs/2308.08155)
- [Magentic-One: A Generalist Multi-Agent System for Solving Complex Tasks](https://arxiv.org/abs/2411.04468)
- [Multi-Agent Computer Use](https://arxiv.org/abs/2606.01533)

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
