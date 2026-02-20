# Fugue Labs

**Stateful systems for stateless models.**

---

The current trajectory of AI — scaling context windows indefinitely — is a structural dead end. Attention dilution, computational waste, behavioral drift. These aren't bugs. They're the architecture.

We're building the alternative.

Our agents operate with zero short-term memory. Context is flushed after every turn. Continuity comes from a tiered retrieval backend that handles consolidation, decay, and recall — the hippocampus — so the model can function purely as cortex.

---

## Research

Memory systems, information retrieval, agent architecture. Implemented in Go. Running in production.

- Tiered memory consolidation with adaptive decay across working, episodic, and semantic stores
- Procedural extraction from unstructured behavioral history
- Entity resolution across noisy, high-cardinality datasets
- Graph-augmented retrieval with hybrid ranking

---

## Open Source

**[Gollem](https://github.com/fugue-labs/gollem)** — Production-grade, type-safe Go framework for LLM agents. Durable execution, streaming, strict structured output. Native [Temporal](https://temporal.io) integration.

---

> *Infinite context is a crutch for poor retrieval. True intelligence requires the ability to forget.*
