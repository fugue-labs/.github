# Fugue Labs

**Stateful systems for stateless models.**

---

Large context windows gave agents a bigger desk. Memory gives them a brain.

Models are getting better at processing long contexts. But processing isn't remembering. An agent that re-reads its entire history every turn is doing linear search over its own life. That works at 8K tokens. At 1M, it's expensive. At the scale agents need to operate, weeks, months, continuously, it's untenable.

We're building the memory layer.

Our agents operate with zero short-term memory. Context is flushed after every turn. Continuity comes from a tiered retrieval backend that handles consolidation, decay, and recall — the hippocampus — so the model can function purely as cortex. This allows agents to operate continuously for months without behavioral drift.

Context windows and memory aren't competing architectures. They're complementary. The window is working memory. We build everything else.

---

## Open Source

### [Gollem](https://github.com/fugue-labs/gollem)

**The production agent framework for Go.** Type-safe agents with compile-time guarantees. Zero core dependencies. Single-binary deployment. 561+ tests.

- **Generic `Agent[T]`** — Output type checked at compile time. Schema generation, validation, and deserialization are automatic.
- **5 LLM providers** — Anthropic, OpenAI, Google Gemini (Vertex AI), Claude via Vertex AI. All interchangeable behind a single `Model` interface.
- **Structured output** — "final_result" tool pattern with auto-repair. Malformed output gets fixed by a repair model before retrying.
- **Reflection-based tools** — `FuncTool[P]` generates JSON Schema from Go structs. Typed dependency injection via `GetDeps[D]`, per-tool timeouts.
- **Guardrails** — Input validation, turn limits, tool result validators, typed output validators. Defense in depth.
- **Multi-agent orchestration** — `AgentTool` delegation, `Handoff` pipelines with context filters, typed event bus for coordination.
- **Composable pipelines** — `Pipeline` chains with `Then`, `ParallelSteps`, and `ConditionalStep`.
- **Cost tracking & usage quotas** — Per-model pricing, per-run breakdowns, hard limits with auto-termination.
- **Conversation memory** — Sliding window, token budget, summary-based, and auto-compression strategies.
- **Temporal durable execution** — Fault-tolerant agents with automatic checkpointing via [Temporal](https://temporal.io).
- **Eval framework** — Datasets, built-in evaluators, LLM-as-judge scoring.
- **Code mode** — Via [monty-go](https://github.com/fugue-labs/monty-go). LLM writes a single Python script, N tool calls execute in 1 model round-trip.

### [monty-go](https://github.com/fugue-labs/monty-go)

**Pure-Go embedded Python execution via WebAssembly.** LLMs write Python that calls your Go functions — no containers, no CGO, no subprocess. Built on [Pydantic's Monty](https://github.com/pydantic/monty) interpreter and [wazero](https://wazero.io).

---

## Research

Memory systems, information retrieval, agent architecture. Implemented in Go. Running in production.

- 4-tier memory architecture (working/episodic/semantic/procedural) with adaptive decay
- Self-RAG intelligence router with Thompson Sampling for adaptive retrieval system selection
- Episodic-to-semantic consolidation via embedding clustering
- Belief revision and contradiction detection across the knowledge graph
- Automatic tier evolution based on strength, access patterns, and content classification
- Entity resolution with hierarchical agglomerative clustering

---

The best models in the world still forget everything between turns. We're fixing that.
