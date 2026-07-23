# Training Compute-Optimal Large Language Models (Chinchilla)

- **Authors:** Jordan Hoffmann, Sebastian Borgeaud, Arthur Mensch, ... Oriol Vinyals, Laurent Sifre (DeepMind)
- **Year:** 2022
- **arXiv:** 2203.15556 — https://arxiv.org/abs/2203.15556
- **PDF:** https://arxiv.org/pdf/2203.15556

## Abstract
We investigate the optimal model size and number of tokens for training a transformer language model under a given compute budget. We find that current large language models are significantly undertrained, a consequence of the recent focus on scaling language models whilst keeping the amount of training data constant. By training over 400 language models ranging from 70 million to over 16 billion parameters on 5 to 500 billion tokens, we find that for compute-optimal training, the model size and the number of training tokens should be scaled equally: for every doubling of model size the number of training tokens should also be doubled. We test this hypothesis by training a predicted compute-optimal model, Chinchilla, that uses the same compute budget as Gopher but with 70B parameters and 4× more data. Chinchilla uniformly and significantly outperforms Gopher (280B), GPT-3 (175B), Jurassic-1 (178B), and Megatron-Turing NLG (530B) on a large range of downstream evaluation tasks. Chinchilla reaches a state-of-the-art average accuracy of 67.5% on the MMLU benchmark, greater than a 7% improvement over Gopher.

## Key points
- **Central finding:** most large LMs (including GPT-3, Gopher) are **significantly undertrained** — too many parameters for too little data.
- **Compute-optimal rule ("Chinchilla scaling"):** for a fixed compute budget, model size and training tokens should scale **equally** — double the parameters, double the data.
- **Chinchilla:** 70B parameters, 4× more data than Gopher, same compute as Gopher (280B); outperforms Gopher, GPT-3 (175B), Jurassic-1, and Megatron-Turing NLG.
- Reframes "scaling" from *parameters-first* to *data-and-parameters-balanced*.
- Smaller compute-optimal models are cheaper to fine-tune and serve at inference.
