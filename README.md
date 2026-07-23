<h1 align="center">Hi, I'm Krishna</h1>
<h3 align="center"> Data / AI Engineer</h3>

---

### About Me

- Building **AI agents, agent memory systems & RAG** — from scratch, in Python
- Going deep on **memory & retrieval infrastructure** — one of the most important, least-solved problems in AI engineering
- Data engineer by trade — I work at the intersection of **data pipelines, ML, and LLMs**
- Learning in public: I ship the simplest version first, then build it up
- Ask me about **agents, RAG, vector databases, and data pipelines**

---

### Tech Stack

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)

**AI / LLM**

![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
![Claude](https://img.shields.io/badge/Anthropic%20Claude-D97757?style=for-the-badge&logo=anthropic&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-3B1F8C?style=for-the-badge&logo=langchain&logoColor=white)
![MCP](https://img.shields.io/badge/MCP-Model%20Context%20Protocol-FF6B35?style=for-the-badge)
![RAG](https://img.shields.io/badge/RAG-Retrieval%20Augmented%20Generation-orange?style=for-the-badge)

**Data & ML**

![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-337AB7?style=for-the-badge)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

**Databases & Vector Stores**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![pgvector](https://img.shields.io/badge/pgvector-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6F61?style=for-the-badge)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)

**Tools**

![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

---

### Featured Projects

| Project | What it is |
| :------ | :--------- |
| **[agents-from-first-principles](https://github.com/chy0010/agent-stack-learning)** | Built the core mechanics behind LLM agents by hand no framework to see exactly what tools like the Agents SDK or LangChain abstract away. Progresses from single-call chat through tool calling, an MCP server exposing those tools over a standard protocol, a full agentic loop, and RAG from scratch scaled to pgvector.<br><br><b>Where this maps to real use cases:</b><ul><li><b>Tool-calling agents</b> - pulls live data or runs a API before answering. Same shape as an ops bot checking inventory or a finance assistant checking a live price.</li><li><b>MCP server + agentic loop</b> - tools live behind one reusable server the agent calls repeatedly until it has enough information, instead of a single fixed call. The shape behind multi-step requests like "check my account, calculate the refund, then answer."</li><li><b>RAG, in-memory → pgvector</b> - answers questions from a document. pgvector is the production path: persisted and queryable at scale, versus a single run that re-embeds every time.</li></ul>|
| **[langgraph-from-scratch](https://github.com/chy0010/langgraph-from-scratch)** |After <code>agents-from-first-principles</code>, wanted to see how a framework like LangGraph encodes the same ideas ,state, control flow, tool loops as reusable graph structure instead of bespoke code. The first two scripts expose a real gap before fixing it: a chat agent that never saves its own reply back into state, then a hand-threaded fix for it. From there, three agents share one core pattern ,bind tools, let the model decide, execute, loop or stop.<br><br><b>Where this maps to real use cases:</b><ul><li><b>ReAct agent</b> - reasons, calls a tool, reasons again before answering. The same shape a support or ops bot needs to check a balance or inventory before responding, instead of a fixed script.</li><li><b>Drafter agent</b> - edits and saves a document through its own tool calls. The backbone of AI writing assistants that persist real edits, not just chat replies.</li><li><b>RAG agent</b> - decides for itself how many times to search a document before answering, at <code>temperature=0</code> for grounded, deterministic answers. A direct blueprint for Q&A over reports or policy docs where citations matter.</li></ul>|
| **[memory-infra](https://github.com/chy0010/memory-infra)** | Wanted to tackle memory and retrieval directly ,one of the least-solved problems in production AI systems as real infrastructure, not a demo script. Built a Postgres + pgvector store (a <code>conversations</code> table: content, embedding, tags, source, metadata) with a write path, a bulk ingest path, and a query path with distance threshold and tag filtering.<br><br><b>Where this maps to real use cases:</b><ul><li><b>Tag + source filtering</b> - the same fields a support agent needs to scope memory to one customer or trust only verified sources.</li><li><b>Bulk ingest from a live API</b> - pulls real Hacker News data through the schema, proving it holds up past a handful of toy inserts, the step before pointing this at real conversation logs.</li><li><b>Distance threshold</b> - stops an agent from confidently reciting a barely-related memory just because it was the nearest neighbor available.</li></ul>|
| **[research-agent](https://github.com/chy0010/research-agent)** | Multi-agent research app - FastAPI + Claude + Tavily web search with a Next.js/TypeScript frontend. Breaks a topic into sub-questions, researches each, and streams answers. |
| **[MarketPulse](https://github.com/chy0010/marketpulse)** | Daily consumer-intelligence pipeline: 2,500+ YouTube comments across 71 channels into Claude, producing stock signals and sentiment-vs-price divergences. |
| **[Ask Data](https://github.com/chy0010/Ask_Data)** | RAG from scratch - query your documents in plain English using LangChain, ChromaDB and SentenceTransformers. |

---

<p align="center"><i>Building in public — starting simple and leveling up.</i></p>
