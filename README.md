# RL Research Papers Collection

A curated list of important research papers related to **LLM agent reasoning** and **Reinforcement Learning**.  
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
| Search-R1: Training LLMs to Reason and Leverage Search Engines with Reinforcement Learning | [Read Paper](https://arxiv.org/pdf/2503.09516) | Constantly outperforms other baselines such as CoT, IRCoT, Search-o1, RAG, SFT, R1-base, R1-instruct, Rejection Sampling on a series of datasets: NQ, TriviaQA, PopQA, HotpotQA, 1wiki, Musique, Bamboogle. Uses models Qwen2.5-3B/7B base/instruct trained with PPO/GRPO policy optimization algos with E5 retrieval model, w/ and w/o **retrieval token loss masking**. | |

## Reinforcement Learning Papers

Key papers covering reinforcement learning algorithms, theory, and practical applications.

| Paper | Link | Description | Year |
|------|------|-------------|--------|
| Human-level control through deep reinforcement learning | [Read Paper](https://web.stanford.edu/class/psych209/Readings/MnihEtAlHassibis15NatureControlDeepRL.pdf)| Introduces the **DQN** algorithm from DeepMind used to update a policy evaluated on a set of video games. | |
