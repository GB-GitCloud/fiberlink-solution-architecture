# AI-Assisted Solution Architecture Workflow

## Purpose

This document defines the end-to-end workflow adopted by the project team to develop the Solution Architecture deliverables using AI assistants.

Each phase produces one or more architecture artifacts that become the input for the following phase.

Human validation is mandatory before advancing to the next step.

---

# Workflow

| Step | Phase | Objective | Prompt | Input | Output | Validation | Status |
|------|-------|-----------|--------|-------|--------|------------|--------|
| W-001 | Repository Initialization | Understand the project and repository | **P-001 – Project Initialization** | Repository + AI Knowledge Base | Repository Assessment | Team | ✅ |
| W-002 | Architecture Brief | Define the business initiative | Manual / Team | Business Initiative | `README.md` | Team | ✅ |
| W-003 | Business Understanding | Demonstrate understanding of the business problem and identify explicit assumptions | **P-002 – Business Understanding Report** | Architecture Brief + AI Knowledge Base | `business-understanding.md` + `assumptions.md` | Team | 🔄 |
| W-004 | Functional Requirements | Transform business understanding into User Stories | **P-003 – Functional Requirements** | Approved Business Understanding Report + Approved Assumptions Register | `functional-requirements.md` | Team | ⏳ |
| W-005 | Non-Functional Requirements | Define measurable quality attributes | **P-004 – Non-Functional Requirements** | Functional Requirements + Business Understanding Report + Approved Assumptions Register | `non-functional-requirements.md` | Team | ⏳ |
| W-006 | Acceptance Criteria | Define business validation scenarios | **P-005 – Acceptance Criteria** | Functional Requirements + Non-Functional Requirements + Approved Assumptions Register | `acceptance-criteria.md` | Team | ⏳ |
| W-007 | Requirements Quality Review | Verify consistency, traceability and completeness | **P-006 – Requirements Review** | FR + NFR + AC + Assumptions Register | Review Report | Team | ⏳ |
| W-008 | Solution Architecture | Design Alternative A | P-007 | Approved Requirements | TO-BE Alternative A | Team | ⏳ |
| W-009 | Solution Architecture | Design Alternative B | P-008 | Approved Requirements | TO-BE Alternative B | Team | ⏳ |
| W-010 | Architecture Decisions | Document Architecture Decision Records (ADR) | P-009 | TO-BE Alternatives + Validated Assumptions | ADR | Team | ⏳ |
| W-011 | Architecture Diagrams | Generate C4 Context Diagram | P-010 | ADR + TO-BE | C4 Level 1 | Team | ⏳ |
| W-012 | Architecture Diagrams | Generate C4 Container Diagram | P-011 | ADR + TO-BE | C4 Level 2 | Team | ⏳ |
| W-013 | Architecture Diagrams | Generate C4 Component Diagram | P-012 | ADR + TO-BE | C4 Level 3 | Team | ⏳ |
| W-014 | Alternative Comparison | Compare both architecture alternatives | P-013 | Alternative A + Alternative B | Comparison Matrix | Team | ⏳ |
| W-015 | Final Recommendation | Recommend the preferred architecture | P-014 | Comparison Matrix | Final Recommendation | Team | ⏳ |

---

# Workflow Principles

## Human Validation

Every generated artifact shall be reviewed and approved before advancing to the next workflow step.

Human validation is mandatory.

---

## Repository First

Every approved artifact shall be persisted in the repository.

The repository is the Single Source of Truth.

AI conversations are considered temporary working sessions.

---

## Traceability

Every artifact shall be traceable to the previous one.

Business Initiative

↓

Architecture Brief

↓

Business Understanding Report

↓

Assumptions Register

↓

Readiness Assessment

↓

APPROVED

↓

Functional Requirements

↓

Non-Functional Requirements

↓

Acceptance Criteria

↓

Architecture Decision Records (ADR)

↓

Architecture Guidelines

↓

Architecture Patterns

↓

TO-BE Architecture

↓

C4 Diagrams

↓

Architecture Comparison

↓

Final Recommendation

---

## Quality Gates

The workflow contains mandatory approval points.

- Architecture Brief
- Business Understanding Report
- Assumptions Register
- Functional Requirements
- Non-Functional Requirements
- Acceptance Criteria
- TO-BE Architecture
- Architecture Decision Records (ADR)
- Final Recommendation

The workflow shall not continue until the current artifact has been approved.

---

## Assumptions Lifecycle

When repository information is insufficient to continue the analysis, explicit assumptions are permitted.

Every assumption shall:

- Receive a unique identifier.
- Be documented in `assumptions.md`.
- Include a rationale.
- Identify where it applies.
- Identify the affected artifacts.
- Indicate its impact.
- Indicate its confidence level.
- Be reviewed during validation.

An assumption may eventually:

- Become a confirmed fact.
- Become an Architecture Decision Record (ADR).
- Be discarded.

Assumptions shall never be presented as confirmed facts.

---

## Repository Rule

Generated artifacts shall always be stored in the same initiative folder where the corresponding Architecture Brief (`README.md`) resides.

The Assumptions Register shall be maintained together with the other requirements artifacts of the corresponding initiative.

AI assistants shall never create parallel folder structures unless explicitly instructed.

