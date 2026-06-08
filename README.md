# From Language Models to Agentic Foundation Models: Architecture, Data, Environments, Rewards, Training, Agentic RL Infra, and Harnesses

Authors: darwin.mathsfan@gmail.com

This repository hosts the first public draft of a survey paper on Agentic Foundation Models (AFMs). The survey argues that agentic capability is best understood as a training-and-systems formation stack that combines model architecture, data pipelines, agentic environments, reward/verifier systems, training, agentic RL infrastructure, and harnesses.

## Current Version

- Version: `v0.1.0`
- Release PDF: [`releases/v0.1.0/agentic-foundation-model-survey-v0.1.0.pdf`](releases/v0.1.0/agentic-foundation-model-survey-v0.1.0.pdf)
- Latest paper PDF: [`paper/agentic-foundation-model-survey.pdf`](paper/agentic-foundation-model-survey.pdf)
- Latest paper Markdown: [`paper/agentic-foundation-model-survey.md`](paper/agentic-foundation-model-survey.md)
- Community post: [`community/community-post.md`](community/community-post.md)

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

## Evidence Discipline

The paper distinguishes technical-report evidence, official product/runtime evidence, local synthesis, and cautious inference. Product system cards and runtime blogs are used for harness and product-runtime claims, not as undisclosed training-recipe evidence. DeepSeek-V4 is used as a long-context architecture and infrastructure substrate anchor, not as a complete agent-training recipe.

## Versioning Notes

The first PDF snapshot is stored under `releases/v0.1.0/`. Future versions should add a new release directory, for example `releases/v0.2.0/`, while keeping `paper/` as the latest editable/public copy.
