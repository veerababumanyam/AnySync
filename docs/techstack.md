# Technology Stack: AnySync Agentic AI Platform (Feb 2026 Update)

This document defines the cutting-edge open-source technology stack for **AnySync**. Following the 3-plane architecture (Action, Intelligence, Data), these selections represent the most stable and performant tools available as of **February 2026**.

---

## 🏗️ Core Architecture (3-Plane Design)

AnySync adheres to the AnySync architectural standard, ensuring separation of concerns across the enterprise AI ecosystem.

### 1. Action Plane (Frontend & UI)
The interactive interface for agents, data visualization, and human-in-the-loop (HITL) workflows.

| Component | Technology | Rationale |
| :--- | :--- | :--- |
| **Framework** | [React 19.2.4](https://react.dev/) + [Vite](https://vitejs.dev/) | Latest production-grade React with patched security and optimized RSC. |
| **Generative UI** | [CopilotKit v1.51.4](https://github.com/CopilotKit/CopilotKit) | Industry standard for canvas-based agentic interfaces and runtime UI generation. |
| **Agent Protocol** | [WebMCP (Draft 2026-02-23)](https://webmachinelearning.github.io/webmcp) | Emerging W3C/WML standard for exposing web apps as structured agent tools. |
| **Styling** | Vanilla CSS (iOS 26 Liquid Glass) | Ultra-premium aesthetic utilizing modern CSS features (Subgrid, Container Queries). |

### 2. Intelligence Plane (Agents & LLM Gateway)
The orchestration layer for reasoning, multi-agent handoffs, and tool execution.

#### LLM Gateway & Connectivity
AnySync employs a unified gateway to abstract provider complexities, providing high availability, automatic failover, and detailed cost tracking.

- **Recommended Gateway**: [Bifrost](https://github.com/maxim-ai/bifrost) (Go-native) - High-performance LLM gateway with OpenAI-compatible API, semantic caching, and observability.
- **Alternative**: [LiteLLM Proxy](https://github.com/BerriAI/litellm) - Managed service/proxy for 100+ model providers.

#### Supported LLM Providers (2026)
| Provider | Native Support | Gateway Support | Key Models |
| :--- | :---: | :---: | :--- |
| **OpenAI** | ✅ | ✅ | o1, GPT-4.5 (preview) |
| **Anthropic** | ✅ | ✅ | Claude 3.5 Sonnet / 3.7 |
| **Google Gemini** | ✅ | ✅ | Gemini 1.5 Pro / 2.0 |
| **Grok (xAI)** | ✅ | ✅ | Grok 4.1 Fast / 4.2 Beta |
| **OpenRouter** | ❌ | ✅ | Unified access to 100+ models |
| **Ollama** | ✅ | ✅ | Llama 3.3, Mistral (Local) |
| **LM Studio** | ✅ | ✅ | Local inference for agentic testing |

#### Agent Frameworks
| Framework | Version | LLM Providers | Key Features |
| :--- | :--- | :--- | :--- |
| **Backend Runtime** | Go 1.26+ | Performance, concurrency, clean architecture |
| **Google ADK** | 1.0 (LTS) | 100+ connectors, Interactions API, multi-agent hierarchies |
| **Google Genkit** | 1.29.0 (Node) / 1.0 (Go) | Gemini, Vertex AI, Mature production graphs |
| **Anthropic Agent SDK** | `v0.2.53` | Native MCP support, Claude 3.5/3.7 integration |
| **Orchestration** | CrewAI, AutoGen, LangGraph | Role-based collaboration, stateful graphs |
| **Agent SDK Go** | 1.1+ | Lightweight, optimized for Go tool calling |

### 3. Data Plane (Storage & Protocols)
The Data Plane provides standardized access to all enterprise data via **FastMCP**.

| Component | Technology | Version | Role |
|-----------|------------|---------|------|
| **MCP SDK** | **FastMCP** | **3.0** | High-performance MCP server development |
| **Primary DB** | PostgreSQL | 18.2 | Main operational database (via sqlx) |
| **Vector DB** | pgvector | 0.8.1 | Semantic search & RAG storage |
| **Semantic Cache**| **Redis** | **7.4+** | High-performance agent memory & cache |

---

## 📡 Messaging, Async Execution & Autonomous Workflows
- **Primary Bus**: [NATS JetStream 2.11+](https://nats.io/) - Fast, lightweight messaging with persistence for agent signals.
- **Workflow Orchestration**: [Temporal](https://temporal.io/) or [Watermill v1.3+](https://watermill.io/) - Robust, fault-tolerant execution of long-running autonomous AI workflows and scheduled report generation.
- **Distributed Cron / Scheduling**: [Asynq](https://github.com/hibiken/asynq) (Redis-backed) or [GoCron](https://github.com/go-co-op/gocron) - Handles reliable, distributed execution of AI-driven scheduled reports and continuous anomaly detection tasks.
- **Anomaly Detection Engine**: Native Go routines integrated with `pgvector` and lightweight time-series analysis for continuous data scanning.
- **Sidecar Framework**: [Dapr v1.15+](https://dapr.io/) - Standardizes state, secrets, and observability across microservices.

---

## 🛠️ Infrastructure & DevSecOps
- **Edge Router**: [Traefik v3.6.9](https://traefik.io/) - Modern HTTP reverse proxy & Cloud Native load balancer.
- **Observability**: [OpenTelemetry](https://opentelemetry.io/) for trace-based agent debugging.
- **Authentication**: [Authelia](https://www.authelia.com/) - Secure Single Sign-On for enterprise tenants.
- **PII Guard**: [Microsoft Presidio](https://github.com/microsoft/presidio) - Real-time de-identification of health data for AI processing.
- **Delivery**: [Argo CD v2.15.0](https://argoproj.github.io/argo-cd/) - GitOps-driven deployment on Kubernetes.
