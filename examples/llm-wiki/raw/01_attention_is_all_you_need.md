# Attention Is All You Need

- **Authors:** Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N. Gomez, Łukasz Kaiser, Illia Polosukhin (Google Brain / Google Research / U. Toronto)
- **Year:** 2017 (NeurIPS 2017)
- **arXiv:** 1706.03762 — https://arxiv.org/abs/1706.03762
- **PDF:** https://arxiv.org/pdf/1706.03762

## Abstract
The dominant sequence transduction models are based on complex recurrent or convolutional neural networks that include an encoder and a decoder. The best performing models also connect the encoder and decoder through an attention mechanism. We propose a new simple network architecture, the Transformer, based solely on attention mechanisms, dispensing with recurrence and convolutions entirely. Experiments on two machine translation tasks show these models to be superior in quality while being more parallelizable and requiring significantly less time to train. Our model achieves 28.4 BLEU on the WMT 2014 English-to-German translation task, improving over the existing best results, including ensembles, by over 2 BLEU. On the WMT 2014 English-to-French translation task, our model establishes a new single-model state-of-the-art BLEU score of 41.8 after training for 3.5 days on eight GPUs.

## Key points (from full text)
- Introduces the **Transformer**, the first sequence transduction model based entirely on attention, with no recurrence or convolution.
- **Scaled dot-product attention:** Attention(Q,K,V) = softmax(QKᵀ/√dₖ)V. Scaling by 1/√dₖ prevents softmax saturation for large dₖ.
- **Multi-head attention:** h=8 heads, dₖ=dᵥ=dmodel/h=64, letting the model attend to different representation subspaces.
- Encoder and decoder are each stacks of N=6 identical layers with residual connections + layer normalization; dmodel=512, feed-forward inner dim d_ff=2048.
- **Positional encoding** via fixed sine/cosine functions injects order information (no recurrence).
- Decoder uses masked self-attention to preserve the auto-regressive property.
- Self-attention connects all positions with O(1) sequential operations vs O(n) for recurrent layers — hence much more parallelizable.
- Trained with Adam and a warmup learning-rate schedule (warmup_steps=4000); regularization via residual dropout (0.1) and label smoothing (0.1).
