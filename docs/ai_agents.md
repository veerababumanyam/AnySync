# AnySync: Multi-Agent Architecture & Agent Teams

This document details the comprehensive **Multi-Agent Architecture** required to power the AnySync platform. AnySync is an Agentic AI Enterprise Orchestration Platform that utilizes a federated, multi-agent model to execute complex tasks, run conversational BI, and integrate with legacy systems (like HIMS, ERPs, and CRMs).

---

## 1. Architectural Principles

AnySync’s agent ecosystem operates within the **Intelligence Plane** of the AnySync three-plane architecture (Action, Intelligence, Data). The architecture is driven by the following principles:
- **Agent-First:** Every feature is invokable by AI agents, not just humans.
- **Federation over Isolation:** Agents collaborate using standard protocols (**A2A** for agent-to-agent, **MCP** and **FastMCP** for agent-to-tool/data connectivity).
- **Strict Read-Only Data Plane:** Agents operate with the `AnySync_readonly` role.
- **Human-in-the-loop (HITL):** Write-backs to the Action Plane or external systems require explicit user approval.
- **PII Masking:** Microsoft Presidio sidecars ensure privacy before context reaches the intelligence plane.

---

## 2. Core Orchestration Team
This team acts as the "brain" and traffic controller of the AnySync platform, ensuring requests are understood, planned, and routed correctly.

| Agent Name | Functionality | Communication / Protocols |
| :--- | :--- | :--- |
| **`MasterOrchestratorAgent`** | Receives user NL input, reasons about intent, breaks requests into sub-tasks (execution plans), and delegates to domain teams. It performs semantic mapping across datasets (e.g., joining `Patient_ID` and `Customer_ID`). | Receives via Action Plane (CopilotKit), delegates via **A2A**. |
| **`FederationRouterAgent`** | Manages external agent federation. When a task requires external intelligence (e.g., Microsoft Copilot, SAP Joule, Salesforce AgentForce), it handles the handshake, authentication (OIDC), and context passing. | Communicates via **A2A / MCP**. |
| **`SecurityGuardianAgent`** | Validates every generated execution plan before data fetching. Ensures all queries are `SELECT`-only and enforces RBAC (Role-Based Access Control) rules based on the user's JWT. | Acts as middleware between Orchestrator and Data Plane. |

---

## 3. Clinical & Healthcare Operations Team
This team focuses on the HIMS integration and clinical workflows, automating tasks that typically cause "click fatigue" for medical professionals.

| Agent Name | Functionality | Features & Tasks |
| :--- | :--- | :--- |
| **`ClinicalContextAgent`** | Discovers patient history and synthesizes medical context. | Retrieves EHR data, alerts on abnormal lab values (FHIR standard deviations), and pushes drafts to the Action Plane for physician approval. |
| **`CarePlanGeneratorAgent`** | Evaluates patient history against current clinical guidelines to propose treatment plans. | Drafts SOAP notes, proposes prescriptions, and lab orders for human review. |
| **`MedicalImagingAgent`** | A specialized multimodal agent that analyzes X-Rays/MRIs and compares them to historical scans. | Provides textual anomaly summaries to the `ClinicalContextAgent`. |

---

## 4. Facility & Operational Management Team
This team is responsible for optimizing hospital or enterprise operations, giving administrators predictive insights.

| Agent Name | Functionality | Features & Tasks |
| :--- | :--- | :--- |
| **`OpsOrchestratorAgent`** | Monitors bed capacity, patient flow, and staffing ratios across departments. | Generates predictive capacity models, identifies bottlenecks, and proposes preemptive staff shifts to administrators. |
| **`SupplyChainAgent`** | Automates inventory tracking and replenishment. | Monitors pharmaceutical and equipment usage, proposing automated POs (Purchase Orders) when thresholds are breached. |
| **`AnomalyDetectionSidecar`** | A proactive monitoring agent running as a Go routine. | Scans real-time metrics for standard deviation breaches and triggers the Orchestrator to generate an alert narrative via NATS JetStream. |

---

## 5. Finance & Revenue Cycle Team
This team focuses on the financial health of the organization, preventing revenue leakage and automating billing.

| Agent Name | Functionality | Features & Tasks |
| :--- | :--- | :--- |
| **`RevenueReconciliationAgent`** | Connects clinical actions to billing codes (ICD/CPT). | Cross-references performed procedures in the EHR with billing ledgers to detect missed charges or revenue leakage. Constructs "Audit Flag Reports". |
| **`ClaimsGenerationAgent`** | Prepares final insurance claims based on reconciled data. | Formats data to meet payer specifications and awaits HITL approval to push to legacy billing systems. |
| **`PredictiveForecastingAgent`** | Analyzes financial trends and external market data. | Generates financial forecasts, answering queries like "Compare revenue by dept for Q1" with narrative insights. |

---

## 6. Data Integration & Knowledge Team
This team provides the foundational data access and long-term memory for the system.

| Agent Name | Functionality | Communication / Protocols |
| :--- | :--- | :--- |
| **`LegacyEtlAgent`** | Bridges the gap between old and new semantic models. | Intercepts legacy HL7 v2 messages, parses them, and maps them to FHIR R4 resources dynamically. |
| **`EnterpriseRagAgent`** | Powers semantic search over unstructured enterprise data (PDFs, SharePoint policies, SOPs). | Uses `pgvector` and Graph/Corrective RAG patterns to ground Orchestrator responses in official policy. |
| **`FastMcpGatewayAgent`** | Handles pure data-fetching tool calls. | Connects directly to Postgres, SQL Server, and Oracle DBs without intermediate APIs, enabling dynamic SQL synthesis. |

---

## 7. Presentation & UX Team
This team ensures the output is always delivered in the premium "Liquid Glass" aesthetic and is easily digestible.

| Agent Name | Functionality | Features & Tasks |
| :--- | :--- | :--- |
| **`NarrativeSynthesizerAgent`** | Translates raw JSON data from domain agents into human-readable business insights. | E.g., translates `{ "change": 15, "dept": "Cardiology" }` into "Cardiology revenue is up 15%, likely due to high cardiac camp volume." |
| **`GenerativeUiMapperAgent`** | Works with CopilotKit to determine the best visualization strategy. | Decides whether a response warrants a Bar Chart, a Data Grid, or a timeline, dynamically generating the React components for the Action Plane. |
| **`ActionBubbleAgent`** | Infers user "next steps" post-report generation. | Generates context-aware interactive buttons (e.g., "Export to PDF", "Drill Down into Q2") for seamless workflow continuation. |

---

## 8. Agent-to-Agent Communication Flow Example

Here is a typical interaction pattern when a user asks: *"Show me the correlation between ER wait times and unbilled claims today."*

1. **User Request -> `MasterOrchestratorAgent`**: Analyzes the intent and realizes it needs Operational data (wait times) and Financial data (unbilled claims).
2. **Task Delegation (parallel)**:
   - Orchestrator requests `OpsOrchestratorAgent` to fetch ER wait times.
   - Orchestrator requests `RevenueReconciliationAgent` to fetch unbilled ER claims.
3. **Data Fetching**:
   - Both domain agents use **FastMCP** tools to query the respective read-only database schemas.
4. **Synthesis**:
   - `OpsOrchestratorAgent` identifies a 45-minute wait time spike.
   - `RevenueReconciliationAgent` identifies 12 unbilled claims in that exact window.
   - Both return JSON + Narrative to the `MasterOrchestratorAgent`.
5. **Consolidation**: The Orchestrator joins the data semantically and hands the combined payload to the `NarrativeSynthesizerAgent`.
6. **Presentation**: `GenerativeUiMapperAgent` receives the final summary and chooses to render a dual-axis line chart (Wait Time vs. Unbilled Claims) using the Liquid Glass design system on the frontend.
