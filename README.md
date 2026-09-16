# 🔍 RAG Course — Building Agentic RAG with LlamaIndex

A hands-on, notebook-based course exploring **Retrieval-Augmented Generation (RAG)** using [LlamaIndex](https://www.llamaindex.ai/) and OpenAI — progressing from basic tool calling to a full multi-document reasoning agent.

---

## Summary

This project is a step-by-step build-up of an **agentic RAG system**, starting from the smallest building block and ending with a working reasoning agent:

1. First, an LLM is given a simple external function it can call on its own (tool calling) — the foundation every agent is built on.
2. Then, a **router** is added so the system can automatically decide whether a question needs a precise vector search or a full-document summary.
3. Next, the system is scaled up to reason over **multiple research papers at once**, giving the agent its own vector + summary tool per document.
4. Finally, all of this is wrapped in an **agent reasoning loop** — the agent plans, picks a tool, observes the result, and repeats until it has a complete answer, instead of answering in a single shot.

By the end, you have an agent that can answer both narrow factual questions and broad summarization questions, across several documents, using its own judgment about which tool and which document to consult.

---

## ✨ Features

- **Custom tool calling** — define plain Python functions (`add`, `mystery`, etc.) and let the LLM decide when and how to call them
- **Router Query Engine** — automatically routes a query to a vector index (specific facts) or a summary index (whole-document summaries)
- **Per-document tool sets** — each source paper gets its own vector + summary tool, so the agent can target the right document
- **Multi-document reasoning** — ask questions that span multiple papers at once (e.g. compare two papers' approaches)
- **Agent reasoning loop** — `FunctionCallingAgentWorker` + `AgentRunner` drive a Thought → Action → Observation loop until the agent is done
- **Handwritten study notes** (`rag_notes.html`) — a notebook-style visual summary of every concept for quick revision/interview prep

---

## 📚 Course Notebooks

| # | Notebook | Description |
|---|---|---|
| 1 | [`Tool_calling.ipynb`](./Tool_calling.ipynb) | Learn how LLMs can call external functions using LlamaIndex's `FunctionTool`. Covers defining custom tools and letting the LLM decide which one to invoke based on natural language. |
| 2 | [`Router_engine.ipynb`](./Router_engine.ipynb) | Build a **Router Query Engine** that intelligently routes queries to either a vector index (specific questions) or a summary index (summarization) over the MetaGPT paper. |
| 3 | [`Building_Multidocument_Agent.ipynb`](./Building_Multidocument_Agent.ipynb) | Scale up to an agent that reasons over **3 research papers** at once (MetaGPT, LongLoRA, Self-RAG), with a per-document vector and summary tool. |
| 4 | [`Agent_Reasoning_loop.ipynb`](./Agent_Reasoning_loop.ipynb) | Dive into the **agent reasoning loop** using `FunctionCallingAgentWorker` and `AgentRunner` — how agents plan, execute, and iterate across multiple steps. |
| — | [`rag_notes.html`](./rag_notes.html) | Handwritten-style notes covering all the concepts and interview Q&A from the course, for quick revision. |

Work through the notebooks in order — each one builds on the concepts from the last.

---

## 🧩 Key Concepts Covered

- **Tool Calling** — letting LLMs invoke external functions
- **Query Routing** — directing queries to the right index type
- **Vector Search** — semantic search over document chunks
- **Summary Index** — full document summarization
- **Multi-Document Agents** — reasoning across multiple sources
- **Agent Reasoning Loop** — step-by-step agent planning and execution

---

## 🛠️ Tech Stack

| Layer | Tech |
|---|---|
| Data/agent framework | [LlamaIndex](https://www.llamaindex.ai/) |
| LLM | OpenAI GPT-3.5 Turbo — generation & tool calling |
| Embeddings | OpenAI `text-embedding-ada-002` — vector search |
| Interface | Python, Jupyter Notebooks |

---

## 📄 Research Papers Used

1. **MetaGPT** — multi-agent framework for software engineering
2. **LongLoRA** — efficient fine-tuning for long-context LLMs
3. **Self-RAG** — learning to retrieve, generate, and critique through self-reflection

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- OpenAI API key

### Installation

```bash
pip install llama-index openai nest_asyncio
```

### Set up your API key

```python
import os
os.environ["OPENAI_API_KEY"] = "your-api-key-here"
```

### Run the notebooks

```bash
jupyter notebook
```

---

## 📂 Project Structure

```
Rag_course/
├── Tool_calling.ipynb                  # Lesson 1: Function tool calling
├── Router_engine.ipynb                 # Lesson 2: Router query engine
├── Building_Multidocument_Agent.ipynb  # Lesson 3: Multi-document agent
├── Agent_Reasoning_loop.ipynb          # Lesson 4: Agent reasoning loop
├── rag_notes.html                      # Handwritten-style study notes
└── README.md                           # This file
```

---

## 📜 License

This project is for educational purposes.

---

⭐ **If you find this helpful, give it a star!**
