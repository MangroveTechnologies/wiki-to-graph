# Training Language Models to Follow Instructions with Human Feedback (InstructGPT / RLHF)

- **Authors:** Long Ouyang, Jeff Wu, Xu Jiang, Diogo Almeida, ... John Schulman, Paul Christiano, Jan Leike, Ryan Lowe (OpenAI)
- **Year:** 2022
- **arXiv:** 2203.02155 — https://arxiv.org/abs/2203.02155
- **PDF:** https://arxiv.org/pdf/2203.02155

## Abstract
Making language models bigger does not inherently make them better at following a user's intent. For example, large language models can generate outputs that are untruthful, toxic, or simply not helpful to the user. In other words, these models are not aligned with their users. In this paper, we show an avenue for aligning language models with user intent on a wide range of tasks by fine-tuning with human feedback. Starting with a set of labeler-written prompts and prompts submitted through the OpenAI API, we collect a dataset of labeler demonstrations of the desired model behavior, which we use to fine-tune GPT-3 using supervised learning. We then collect a dataset of rankings of model outputs, which we use to further fine-tune this supervised model using reinforcement learning from human feedback. We call the resulting models InstructGPT. In human evaluations on our prompt distribution, outputs from the 1.3B parameter InstructGPT model are preferred to outputs from the 175B GPT-3, despite having 100x fewer parameters. Moreover, InstructGPT models show improvements in truthfulness and reductions in toxic output generation while having minimal performance regressions on public NLP datasets.

## Key points
- Introduces **RLHF** (Reinforcement Learning from Human Feedback) applied to align LLMs, producing **InstructGPT**.
- Three-step pipeline:
  1. **SFT** — supervised fine-tuning of GPT-3 on labeler demonstrations.
  2. **Reward model** — train a model to predict human preference rankings over outputs.
  3. **RL (PPO)** — optimize the policy against the reward model using Proximal Policy Optimization.
- Central alignment goals: make models **helpful, honest, and harmless**.
- Key result: 1.3B InstructGPT is preferred by humans over 175B GPT-3 — **alignment can beat raw scale** on intent-following.
- Directly counters the "bigger is better" implication of GPT-3; the bridge from raw LLMs to modern assistants (ChatGPT).
