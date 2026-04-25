# RL Research Papers Collection

A curated list of important research papers related to **LLM axfgent reasoning** and **Reinforcement Learning**.  
Each paper includes a link and a short description.

---

## LLM Agents Reasoning Papers

Research focused on reasoning, planning, tool use, and decision-making capabilities in large language model agents.

| Paper | Link | Description | Year |
|------|------|-------------|-----|
| Agentic Reasoning: A Streamlined Framework for Enhancing LLM Reasoning with Agentic Tools | [Read Paper](https://aclanthology.org/2025.acl-long.1383.pdf) | Introduces a framework based on three tools: **Memory agent (Mind-Map)** - that uses a graph-construction LLM to extract entities from the reasoning chain to identify semantic reltionships between related entities, following a process similar to that used in GraphRAG (used for retrieval); **Web-Seach agent** - that uses Google or Bing search engines to retrieve web pages for refined queries than applies a re-ranking model (Cohere Rerank 3.5) based on the alignment with the original query and context and then applies RAG to generate a natural language response; **Coding Agent** - delegates coding tasks to a specialized coding LLM (claude-3.5-sonnet). This framework offers modular reasoning, task delegation, and structured integration. _Implementation details:_ Hugging Face's default agent toolbox with seven tools and LangChain with 109 tools. | |
| Agentic Reasoning for Large Language Models | [Read paper](https://arxiv.org/pdf/2601.12538) | Most up to date survey regarding reasoning agents with appllications where they are used. Key frameworks introduced for IR and RL: **DeepResearcher, Search-R1, PaperQA/PaperQA2**, RAGEN, DYSTIL, . Key terms: reasoning traces, MDP (Markov Decision Process), POMDP, Monte Carlo Tree Search, Theory of Mind, GLM (Generalized Linear Models)  | Jan 2026 |


## Information Retrieval

Research focused on Information Retrieval systems based on LLM enhanced with reasoning capabilities to use tools through RL

| Paper | Link | Description | Year |
|------|------|-------------|-------|
| Search-R1: Training LLMs to Reason and Leverage Search Engines with Reinforcement Learning | [Read Paper](https://arxiv.org/pdf/2503.09516) | Constantly outperforms other baselines such as CoT, IRCoT, Search-o1, RAG, SFT, R1-base, R1-instruct, Rejection Sampling on a series of datasets: NQ, TriviaQA, PopQA, HotpotQA, 1wiki, Musique, Bamboogle. Uses models Qwen2.5-3B/7B base/instruct trained with PPO/GRPO policy optimization algos with E5 retrieval model, w/ and w/o **retrieval token loss masking**. Uses **Ray** for distributed training. | COLM 2025 |
|FlashRAG: A Modular Toolkit for Efficient Retrieval-Augmented Generation Research| [Read Paper](https://arxiv.org/pdf/2405.13576) | Introduces a toolkit that consists of a collection of benchmark datasets, SOTA RAG methods, utilities for corpus pre-processing, and a set of evaluation **metrics** (recall@k, precision@k, F1@k, MAP - for retrieval; token-level F1 score, exact match, accuracy, BLEU, and ROUGE-L - for generation. **Takeaways**: When comparing dense retrievers E5, BGE, with sparse retrievers BM25, the difference in accuracy between the 2 categories is the gratest at top-1 (dense retrievers better than sparse ones), best results in all cases at top-5, and the difference between dense and sparse retuces once the retrieved number of documents increases. In terms of **chunking**, regardless of the chunk size, the optimal results are achieved at aprox 350-450 words of retrieved text. So for big chunks it would make more sense to retrieve less documents. Discusses OpenAI's **CLIP** model for multimodel retrieval (text and images).| May 2025 ACM on Web Conference |
|On the Theoretical Limitations of Embedding-Based Retrieval | [Read Paper](https://arxiv.org/abs/2508.21038)| In an information retrieval setup, the more documents we get, the higher dimensionality we need for the embedded vectors.  The community should reconsider how instruction-based retrieval will impact future retrievers. For a fixed embedding dimension, there will be some set of documents such that certain sets are unattainable as top-k sets. This essentially applies for single vector models, and it's worth to try multi-vector models, as these are not particularly used in retrieval applications as of now. |  ICLR 2026 |
| The Curse of Dense Low-Dimensional Information Retrieval for Large Index Sizes | [Read Paper](https://arxiv.org/abs/2012.14210)| Dense representations have been introduced to overcome the issue of the lexical gap problem of TF_IDF and BM25, but the outperformance happens for fixed, rather small indexes. For MS MARCO dataset, the retrieval can be done over an index of 8.8 million text passages; however, in production scenarios, index sizes quickly reach 100 million documents. For a small index, 100k documents, a dense approach might clearly outperform sparse approaches, but with a larger index of several million documents, the sparse approach can outperform the dense approach. Using a few dimensions as possible is desirable, as it decreases the memory requirement to store (an index) of millions of vectors and leads to faster retrieval. However, lower-dimensional representations can have issues with large indices. Mentions the popular **DPR system**, a BERT-based dense retriever trained on the NQ dataset.| ACL Aug 2021 |
| Dense Passage Retrieval for Open-Domain Question Answering | [Read Paper](https://arxiv.org/pdf/2004.04906)| Introduces DPR, where a retrieval can be implemented using dense representations alone, where embeddings are learned from a small number of questions and passages by a simple dual-encoder framework. Compared against a strong **Lucene-BM25** system. | Sept 2020 |




## Reinforcement Learning Papers

Key papers covering reinforcement learning algorithms, theory, and practical applications.

| Paper | Link | Description | Year |
|------|------|-------------|--------|
| Human-level control through deep reinforcement learning | [Read Paper](https://web.stanford.edu/class/psych209/Readings/MnihEtAlHassibis15NatureControlDeepRL.pdf)| Introduces the **DQN** algorithm from DeepMind used to update a policy evaluated on a set of video games. | |

## Datasets

Key datasets used in the context of information retrieval. 

| Paper | Link | Description | Year |
|------|------|-------------|--------|
| LongMemEval: Benchmarking Chat Assistants on Long-Term Interactive Memory | [Read Paper](https://arxiv.org/pdf/2410.10813)| Tackles problems such as long context inputs, the lost-in-the-middle phenomenon, and text summarization. Key takeaways: Chain-of-Note and JSON format for input. | ICLR 2025 |

## Utilities 

A few important papers addressing LLM-related topics that can serve as a foundation for analysis in other contexts.

| Paper | Link | Description | Year |
|------|------|-------------|--------|
| Matryoshka Representation Learning | [Read Paper](https://arxiv.org/abs/2205.13147)| MRL learns representations of varying capacities within the same high-dimensional vector through explicit optimization of O(log(d)) lower-dimensional vectors in nested fashion (Matryoshka), flexible representation that can adapt to multiple downstream tasks with varying computational resources. MRL and Adaptive Retrieval prove to have potential for large-scale multi-stage search systems. MRL learns course-to-fine representations that are at least as accurate and rich as independently trained low-dimensional representations. | NeurIPS 2022 |
| Did You Read the Instructions? Rethinking the Effectiveness of Task Definitions in Instruction Learning | [Read Paper](https://arxiv.org/abs/2306.01150)| Framing instructions as a structured input/action/output triplet is potentially a more efficient and effective way of creating task definitions (JSON format). Using only basic metadata and the label space (without label definitions) in a structured format, we achieve similar, or even better, performance as with full definitions. Adding a meta-tuning stage for adapting models to the writing styles of definitions improves the performance. This takes effect only in the generation or classification phase with an LLM, after the retrieval is performed. | June 2023 |

