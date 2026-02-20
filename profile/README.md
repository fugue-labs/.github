# 🧠 Fugue Labs

**Building the Cognitive Infrastructure for Zero-State Agents.**

---

We believe the current trajectory of AI—relying on ever-expanding context windows—is a **structural dead end**. It leads to attention dilution, computational waste, and behavioral drift.

Fugue Labs is engineering the alternative: **Stateful Systems for Stateless Models.**

Our architecture enables agents to operate with **zero short-term memory** (flushing context after every turn) by relying entirely on a high-speed, tiered retrieval backend. We provide the *"Hippocampus"* so the LLM can act as the *"Cortex."*

---

## 🔬 Core Research & Architecture

Our systems are built on four fundamental pillars, implemented in high-performance Go:

- **Tiered Memory Consolidation:** Data decays and evolves across Working, Episodic, and Semantic tiers using Ebbinghaus-inspired forgetting curves (`AdaptiveDecay`).
- **Procedural Extraction:** We don't just store facts; we extract behavioral patterns (code style, workflows) from unstructured history to enforce agent consistency.
- **Transitive Entity Resolution:** Custom Hierarchical Agglomerative Clustering (HAC) pipelines to resolve identity variance across massive datasets.
- **Graph-Augmented Retrieval:** Multi-hop reasoning backed by PostgreSQL and Apache AGE, fused with HNSW vector search via Reciprocal Rank Fusion (RRF).

---

## 📦 Open Source

We are open-sourcing the execution layer of our architecture.

- **[Gollem](https://github.com/fugue-labs/gollem):** A production-grade, type-safe Go framework for LLM agents. Built for durability, streaming, and strict structured output. *(Includes native [Temporal.io](https://temporal.io) integration for long-running agents).*

---

## 🔒 Enterprise Platform *(Private Beta)*

- **Fugue Memory Service (gRPC):** The distributed cognitive backend that powers our agents. Features include Thompson Sampling routing, automatic belief revision, and the "Lazarus" GDPR ingestion pipeline.
- **Amnesia / Recall:** Our internal zero-state coding agents that interface with the Memory Service.

> *Enterprise access to the Memory Service is currently restricted to design partners.*

---

## ⚡ The Fugue Philosophy

> *"Infinite context is a crutch for poor retrieval. True intelligence requires the ability to forget."*
