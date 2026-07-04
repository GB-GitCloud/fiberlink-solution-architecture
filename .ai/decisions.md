# Project Decisions

## Purpose

This document records the strategic decisions that govern the project.

These decisions define the project's working model, documentation standards and architectural governance.

Project Decisions are **not** Architecture Decision Records (ADR).

Architectural design decisions shall be documented separately within the ADR repository.

---

# Decision Classification

Project Decisions establish:

- Project governance
- Documentation standards
- Repository policies
- AI collaboration rules
- Architecture governance

They do not define specific technology implementations.

---

# PD-001 – Selected Cloud Platform

**Status**

Approved

**Decision**

Microsoft Azure is the selected cloud platform for this project.

**Rationale**

The course allows AWS, Azure or Google Cloud Platform. The project team selected Azure to maintain consistency across all deliverables and demonstrations.

**Impact**

- Architecture diagrams shall use Azure terminology.
- Presentation diagrams shall use official Azure Architecture Icons.
- Cloud services referenced throughout the repository shall correspond to Azure services.

---

# PD-002 – Repository as the Single Source of Truth

**Status**

Approved

**Decision**

The GitHub repository is the authoritative source for all project documentation.

**Rationale**

Centralizing documentation improves collaboration, traceability and version control.

**Impact**

All project artifacts shall be maintained and versioned within the repository.

---

# PD-003 – Architecture Methodology

**Status**

Approved

**Decision**

The project follows the TOGAF Architecture Development Method (ADM).

**Rationale**

The methodology is required by the course and provides a structured architecture development process.

**Impact**

Deliverables shall remain aligned with the corresponding ADM phases.

---

# PD-004 – Repository Organization

**Status**

Approved

**Decision**

The repository structure is considered stable.

**Rationale**

Maintaining a stable structure improves collaboration and reduces documentation fragmentation.

**Impact**

New folders shall only be created when explicitly approved by the project team.

---

# PD-005 – Documentation Language

**Status**

Approved

**Decision**

Documentation language is defined as follows:

- `.ai` documentation → English
- `docs/` documentation → Spanish

Industry-standard terminology shall remain in English whenever appropriate.

**Rationale**

This separation optimizes AI understanding while maintaining readable project deliverables.

---

# PD-006 – Architecture Representation

**Status**

Approved

**Decision**

The project shall adopt the following architecture documentation standards:

- Markdown
- Mermaid
- C4 Model
- Draw.io (presentation-quality diagrams)

**Rationale**

These standards provide version control, readability and consistent architectural representation.

---

# PD-007 – Requirements Governance

**Status**

Approved

**Decision**

Official requirements shall always take precedence over draft documents.

**Rationale**

Solution Architecture must be based on validated requirements.

**Impact**

AI assistants shall always consume official documentation unless explicitly instructed otherwise.

---

# PD-008 – Traceability Policy

**Status**

Approved

**Decision**

Every project artifact shall maintain end-to-end traceability.

**Expected traceability**

Business Initiative

↓

Functional Requirements

↓

Non-Functional Requirements

↓

Acceptance Criteria

↓

Architecture Decision Records

↓

Architecture Guidelines

↓

Architecture Patterns

↓

Solution Architecture

↓

Cloud Demonstration

↓

Final Presentation

**Rationale**

Maintaining traceability improves architectural governance and simplifies validation.

---

# PD-009 – Assumption Management

**Status**

Approved

**Decision**

Architectural assumptions shall never be treated as confirmed facts.

Whenever assumptions are required, they shall be documented through the corresponding ADR.

**Rationale**

Assumptions directly influence architectural quality and must remain visible and reviewable.

---

# PD-010 – TO-BE Alternatives

**Status**

Approved

**Decision**

Deliverable 3 shall produce two alternative TO-BE Solution Architectures.

Both alternatives shall satisfy the same approved Functional Requirements, Non-Functional Requirements and Acceptance Criteria.

**Rationale**

The objective is to compare architectural approaches rather than redefine business requirements.

---

# PD-011 – AI Collaboration

**Status**

Approved

**Decision**

AI assistants are considered architecture collaborators.

They shall:

- Read repository documentation before generating artifacts.
- Follow project policies.
- Reuse repository terminology.
- Preserve traceability.
- Respect repository organization.

AI assistants shall not redefine business objectives or approved architectural decisions.

**Rationale**

The repository is designed as an AI-assisted Architecture Knowledge Base.

---

# Document Maintenance

This document shall only contain strategic project decisions.

Technology-specific design decisions shall be documented as Architecture Decision Records (ADR).

Project Decisions are expected to remain stable throughout the project lifecycle.