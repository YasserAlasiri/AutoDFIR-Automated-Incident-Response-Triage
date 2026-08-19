# AutoDFIR-Automated-Incident-Response-Triage
#Track A: Supervisor + Workers
Student name: MOHAMMED ABDULLAH ALHAMMADI , YASSER AHMED ALASSIRI
Programme / cohort: SDAIA Academy – DAICO | Agentic AI Systems Program | August 2026
This project is an Automated Digital Forensics and Incident Response (AutoDFIR) triage system. It implements the **Track A: Supervisor (Multi-Agent Collaboration)** architecture to evaluate security alerts, check asset criticality, and search internal playbooks before recommending action.

### Rubric Checklist
* **Rubric 1 (Agent Fundamentals):** Triage tools (`get_asset_context`, `extract_observables`, `calculate_risk_score`) are built using strict Pydantic schemas.
* **Rubric 2 (Track A):** A Supervisor node uses structured output to route tasks between a Triage Worker and an Evidence Worker.
* **Rubric 3 (RAG Pipeline):** Ingests local `.txt` playbooks, chunks them, and stores them in an `InMemoryVectorStore` accessed via the `search_dfir_knowledge` tool.
* **Rubric 4 (Context & State):** Uses `InMemorySaver` for thread-level short-term memory and `InMemoryStore` for cross-thread long-term memory (storing analyst preferences).
* **Rubric 5 (Human-in-the-Loop):** The graph dynamically pauses using `interrupt()` for high-severity actions, requiring human approval before resuming.
* **Rubric 6 (Reliability):** Implements `RetryPolicy` on LLM tasks and a safe fallback task for error handling.
* **Rubric 7 (Workflow Pattern):** Built entirely using the LangGraph Functional API (`@task` and `@entrypoint`).
* **Rubric 8 (Observability):** LangSmith tracing is fully enabled.
