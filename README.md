# RL Research Papers Collection

A curated list of important research papers related to **LLM agent reasoning** and **Reinforcement Learning**.  
Each paper includes a link and a short description.

---

## LLM Agents Reasoning Papers

Research focused on reasoning, planning, tool use, and decision-making capabilities in large language model agents.

| Paper | Link | Description |
|------|------|-------------|
| Agentic Reasoning: A Streamlined Framework for Enhancing LLM Reasoning with Agentic Tools | [Read Paper](https://aclanthology.org/2025.acl-long.1383.pdf) | Introduces a framework based on three tools: **Memory agent (Mind-Map)** - that uses a graph-construction LLM to extract entities from the reasoning chain to identify semantic reltionships between related entities, following a process similar to that used in GraphRAG (used for retrieval); **Web-Seach agent** - that uses Google or Bing search engines to retrieve web pages for refined queries than applies a re-ranking model (Cohere Rerank 3.5) based on the alignment with the original query and context and then applies RAG to generate a natural language response; **Coding Agent** - delegates coding tasks to a specialized coding LLM (claude-3.5-sonnet). This framework offers modular reasoning, task delegation, and structured integration. _Implementation details:_ Hugging Face's default agent toolbox with seven tools and LangChain with 109 tools. |

## Reinforcement Learning Papers

Key papers covering reinforcement learning algorithms, theory, and practical applications.

| Paper | Link | Description |
|------|------|-------------|
| Human-level control through deep reinforcement learning | [Read Paper](https://web.stanford.edu/class/psych209/Readings/MnihEtAlHassibis15NatureControlDeepRL.pdf)| Introdduces the DQN algorithm used to update a policy evaluated on a set of video games. |
