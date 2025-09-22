# 🔹 Research & Summarization Agent — LangGraph Implementation

This project demonstrates how to build an **Agentic AI system** using **LangGraph** that combines **Retrieval-Augmented Generation (RAG)**, **role-based access control (RBAC)**, and **web search fallback** to provide secure, context-rich responses.  

The design extends my earlier RAG-based chatbot implementation into a **graph-based agent workflow**, giving modularity, observability, and memory-driven conversational continuity.  

---

## ✅ Key Features

- **Role-Aware Query Handling**  
  - Queries are classified into categories:  
    - `employee`  
    - `engineer`  
    - `hr`  
    - `finance`  
    - `marketing`  
  - Ensures users only receive responses relevant to their role.

- **Web Search Fallback**  
  - If no relevant internal documents are found in the vectorstore, the query is routed to **web search** for external context.

- **Context & Memory**  
  - Maintains conversational history to handle follow-up questions.  
  - Supports pronoun resolution (e.g., *"Where was he born?"* → links back to previously mentioned CEO).

- **Graph-Oriented Workflow**  
  - Uses **LangGraph** to define explicit nodes and transitions:  
    - `categorize_inquiry` → role-specific response generators  
    - `search_web` → for external queries  
    - All converge into `generate_answer`  

---

## 🔹 Architecture

Below is the **LangGraph workflow** for this agent:  

![LangGraph Workflow](./docs/langgraph_workflow.png)  
*(Generated via LangGraph visualization — shows routing from inquiry categorization to specialized nodes or web search, ending with a unified answer.)*

---

## ⚙️ Tech Stack

- [LangGraph](https://github.com/langchain-ai/langgraph)  
- [LangChain](https://github.com/langchain-ai/langchain)  
- **Vectorstore**: ChromaDB (for RAG retrieval)  
- **Web Search**: Tavily API  
- **LLM**: OpenAI (can be swapped with any compatible provider)  
- Python 3.10+

---
  
