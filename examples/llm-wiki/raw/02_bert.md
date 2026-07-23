# BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding

- **Authors:** Jacob Devlin, Ming-Wei Chang, Kenton Lee, Kristina Toutanova (Google AI Language)
- **Year:** 2018 (NAACL 2019)
- **arXiv:** 1810.04805 — https://arxiv.org/abs/1810.04805
- **PDF:** https://arxiv.org/pdf/1810.04805

## Abstract
We introduce a new language representation model called BERT, which stands for Bidirectional Encoder Representations from Transformers. Unlike recent language representation models, BERT is designed to pre-train deep bidirectional representations from unlabeled text by jointly conditioning on both left and right context in all layers. As a result, the pre-trained BERT model can be fine-tuned with just one additional output layer to create state-of-the-art models for a wide range of tasks, such as question answering and language inference, without substantial task-specific architecture modifications. BERT is conceptually simple and empirically powerful. It obtains new state-of-the-art results on eleven natural language processing tasks, including pushing the GLUE score to 80.5% (7.7% point absolute improvement), MultiNLI accuracy to 86.7% (4.6% absolute improvement), SQuAD v1.1 question answering Test F1 to 93.2 (1.5 point absolute improvement) and SQuAD v2.0 Test F1 to 83.1 (5.1 point absolute improvement).

## Key points
- Uses only the **encoder** stack of the Transformer, trained to be deeply **bidirectional**.
- **Masked Language Modeling (MLM):** randomly mask ~15% of tokens and predict them from both-side context — enables bidirectionality (contrast with left-to-right GPT).
- **Next Sentence Prediction (NSP):** predict whether sentence B follows sentence A, to learn inter-sentence relationships.
- Two-stage recipe: **pre-training** on unlabeled text (BooksCorpus + English Wikipedia), then **fine-tuning** with one added output layer per task.
- Model sizes: BERT-BASE (110M params, 12 layers) and BERT-LARGE (340M params, 24 layers).
- WordPiece tokenization; special tokens [CLS] (classification) and [SEP] (separator).
