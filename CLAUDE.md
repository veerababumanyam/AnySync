# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**AnySync** is an **Agentic AI Enterprise Orchestration Platform** that unifies legacy data systems, AI agents, and protocols into a single autonomous interface. The project is transitioning from a Conversational BI tool to a multi-agent ecosystem.

### Product Vision
- **Autonomous Agent Orchestration**: Multi-agent hierarchies (Google ADK, Genkit, Claude SDK)
- **Protocol Standardization**: Native support for A2A, MCP, and Agent Cards
- **External Agent Federation**: Bidirectional integration with MS Copilot, SAP Joule, Salesforce AgentForce
- **Enterprise RAG**: Advanced RAG patterns (Adaptive, Corrective, Graph)
- **Universal Database Integration**: Direct access to 30+ database types (SQL, NoSQL, warehouses, vector stores, graph, time-series, data lakes)
- **Healthcare-Focused Security**: HIPAA/GDPR compliance with Microsoft Presidio PII management

### Current Status
- **Documentation Phase**: PRD v2.1.0 and design system completed
- **Implementation Readiness**: Core platform architecture and security standards defined

## Documentation Structure

### `/docs/PRD.md` - Product Requirements Document
- Version 2.1.0 (last updated Feb 25, 2026)
- Agentic AI Platform Edition: A2A/MCP protocols, external federation, RAG architecture
- Security: OWASP Top 10 for Agentic Applications, Presidio PII admin
- Technical Architecture: Universal database integration, Text-to-SQL codes

### `/docs/design.md` - Design System
- **Visual Language**: iOS 26 Liquid Glass aesthetic
- **Accessibility**: WCAG 3.0 Bronze compliance
- **Color System**: 3-color brand system extracted from logo
  - Primary: `#1B3FA0` (Royal Blue) - Authority, data intelligence
  - Secondary: `#17B5A6` (Teal-Cyan) - Flow, connectivity
  - Accent: `#1CD760` (Emerald) - Vitality, action
- **Typography**: Inter font family
- **Components**: Glass surfaces, gradient tokens, animation system

## Asset Management

### `/public/icons/` - Multi-Platform Icon Assets
- Favicon set (16x16, 32x32, 48x48)
- PWA icons (72-512px)
- iOS iconset for App Store
- Android mipmap resources
- Logo variants (64-512px)

**Regeneration**: `python3 scripts/generate_logos.py` (requires Pillow)

## BMAD Framework

This project uses **BMAD (Business-driven Model for AI Development)** v6.0.3 for AI-assisted development:

### Available Agents (via cursor/claude commands)
- `bmad-help` - Development guidance and next steps
- `bmad-brainstorming` - Creative ideation sessions
- `bmad-review-adversarial-general` - Critical code/design review
- `bmad-editorial-review-prose` - Copy editing and communication
- `bmad-editorial-review-structure` - Document structure review
- `bmad-shard-doc` - Split large documents into smaller files
- `bmad-index-docs` - Generate documentation indexes
- `bmad-party-mode` - Multi-agent collaborative discussions

### Framework Structure
- `/_bmad/_config/` - BMAD configuration and manifests
- `/_bmad/core/` - Core agents, tasks, and workflows
- `.cursor/commands/` - Cursor IDE command definitions
- `.claude/commands/` - Claude Code command definitions

## Technical Architecture (Planned)

Based on PRD specifications, the future implementation should include:

### Frontend
- React/TypeScript with modern component library
- Real-time data visualization (charts, maps, tables)
- Natural language query interface
- Dashboard builder with drag-and-drop
- Responsive design (mobile-first)

### Backend
- **Runtime**: Go 1.26+ (Clean Architecture)
- **Frameworks**: `go-chi` (Routing), `sqlx` (Database bridging)
- **APIs**: REST layer for data source integration, A2A/MCP protocols
- **Intelligence**: Google Genkit Flows, Multi-agent orchestration
- **Security**: SELECT-only SQL validation, PII masking via Presidio

### Data Layer
- **Databases**: PostgreSQL 18.2 (Primary), pgvector (Vector Store)
- **Caching**: Redis 7.4+ (Semantic caching & agent memory)
- **Connectors**: FastMCP 3.0 for legacy HIS/ERP systems
- **Multi-tenancy**: Role-based data isolation

### Infrastructure
- **Edge Router**: Traefik v3.6.9 (Ingress & Load Balancing)
- **Messaging**: NATS JetStream 2.11+ (Event-driven signals)
- **Deployment**: Kubernetes with Argo CD (GitOps)
- **Observability**: OpenTelemetry + AgentOps tracking

## Development Workflow

### Documentation-First Approach
1. All features must be specified in PRD.md before implementation
2. Design decisions should align with design.md system
3. Use BMAD agents for brainstorming and review
4. Maintain comprehensive documentation

### When Adding New Features
1. Update PRD.md with feature specification
2. Review design.md for visual/UX alignment
3. Use `bmad-brainstorming` for ideation if needed
4. Use `bmad-review-adversarial-general` for critical review
5. Ensure accessibility (WCAG 3.0) and compliance requirements

### Code Organization (Future)
- Follow established project structure once created
- Maintain separation of concerns
- Write comprehensive tests
- Document APIs and components

## Key Design Principles

### Accessibility First
- WCAG 3.0 Bronze compliance minimum
- Screen reader optimization
- Keyboard navigation support
- Color contrast requirements

### Healthcare Focus
- HIPAA/GDPR compliance
- Multi-language support (English/Arabic)
- Medical-grade data accuracy
- Audit trail requirements

### User Experience
- Conversational interface over SQL queries
- Zero-code dashboard building
- Mobile-first responsive design
- iOS 26 Liquid Glass visual language

## Important Notes

- **No Build System Yet**: Don't assume npm, go, or other tooling until implementation begins
- **No Tests Yet**: Test infrastructure will be established during implementation
- **No CI/CD Yet**: Deployment pipeline to be defined
- **Documentation as Source of Truth**: PRD.md and design.md guide all decisions

## Brand Guidelines

- Use logo assets from `/public/icons/` for all platforms
- Follow color system from design.md
- Maintain "structured data → flowing transition → living pulse → forward momentum" narrative
- Apply Liquid Glass aesthetic consistently
