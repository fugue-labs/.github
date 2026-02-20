# Fugue Labs

**Stateful systems for stateless models.**

---

The current trajectory of AI — scaling context windows indefinitely — is a structural dead end. Attention dilution, computational waste, behavioral drift. These aren't bugs. They're the architecture.

We're building the alternative.

Our agents operate with zero short-term memory. Context is flushed after every turn. Continuity comes from a tiered retrieval backend that handles consolidation, decay, and recall — the hippocampus — so the model can function purely as cortex.

---

## Open Source

### [Gollem](https://github.com/fugue-labs/gollem)

**The production agent framework for Go.** Type-safe agents with compile-time guarantees that Python frameworks can't offer. Zero core dependencies. Single-binary deployment. 561+ tests.

- **Generic `Agent[T]`** — Output type checked at compile time. Schema generation, validation, and deserialization are automatic. No runtime surprises.
- **4 LLM providers** — Anthropic, OpenAI, Google Gemini (Vertex AI), Claude via Vertex AI. All interchangeable behind a single `Model` interface.
- **Structured output** — "final_result" tool pattern with auto-repair. Malformed output gets fixed by a repair model before retrying.
- **Reflection-based tools** — `FuncTool[P]` generates JSON Schema from Go structs. Type-safe parameters, typed dependency injection via `GetDeps[D]`, per-tool timeouts.
- **Streaming** — Go 1.23+ `iter.Seq2` iterators. Delta, accumulated, and debounced modes for real-time token delivery.
- **Guardrails** — Input validation (prompt length, content filtering), turn limits, tool result validators, and typed output validators. Defense in depth.
- **Agent middleware** — Composable chain wrapping model calls. Built-in timing, logging, token limits. Custom middleware can short-circuit the model entirely.
- **Message interceptors** — PII redaction, audit logging, and custom filters applied before messages leave your system or after responses arrive.
- **Cost tracking & usage quotas** — Per-model pricing, per-run cost breakdowns, cumulative totals. Hard limits on requests, tokens, and spend with auto-termination.
- **Multi-agent orchestration** — `AgentTool` delegation, `Handoff` pipelines with context filters, typed event bus for pub-sub coordination.
- **Composable pipelines** — `Pipeline` chains with `Then`, `ParallelSteps`, and `ConditionalStep`. Fan-out/fan-in with automatic result joining.
- **Graph workflow engine** — Typed state machines with conditional branching, cycle detection, and Mermaid export.
- **Model routing** — Threshold routing, capability-based routing. Route prompts to the right model based on content, length, or required capabilities.
- **Resilience** — Retry with exponential backoff and jitter, token-bucket rate limiting, SHA-256 response caching with TTL.
- **Deep context management** — Three-tier compression, planning tools, and checkpointing for agents that operate over massive context windows.
- **Temporal durable execution** — Fault-tolerant agents with automatic checkpointing and retries via [Temporal](https://temporal.io).
- **MCP integration** — Stdio and SSE transports, multi-server manager with namespaced tools.
- **Eval framework** — Datasets, built-in evaluators (`ExactMatch`, `Contains`, `JSONMatch`), LLM-as-judge scoring.
- **State snapshots** — Capture, serialize, branch, and replay agent state for time-travel debugging.
- **Conversation memory** — Sliding window, token budget, summary-based, and auto-compression strategies.
- **TUI debugger** — Terminal UI with step-mode execution, tool call formatting, and color-coded messages.
- **Full test mock** — `TestModel` with canned responses and call recording. Test agents without real LLM calls.

### [monty-go](https://github.com/fugue-labs/monty-go)

**Pure-Go embedded Python execution via WebAssembly.** LLMs write Python that calls your Go functions — no containers, no CGO, no subprocess. Built on [Pydantic's Monty](https://github.com/pydantic/monty) interpreter and [wazero](https://wazero.io).

---

## Research

Memory systems, information retrieval, agent architecture. Implemented in Go. Running in production.

- Tiered memory consolidation with adaptive decay across working, episodic, and semantic stores
- Procedural extraction from unstructured behavioral history
- Entity resolution across noisy, high-cardinality datasets
- Graph-augmented retrieval with hybrid ranking

---

> *Infinite context is a crutch for poor retrieval. True intelligence requires the ability to forget.*
