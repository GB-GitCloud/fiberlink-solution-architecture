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
| W-003 | Business Understanding | Demonstrate understanding of the business problem before defining requirements | **P-002 – Business Understanding Report** | Architecture Brief + AI Knowledge Base | `business-understanding.md` | Team | 🔄 |
| W-004 | Functional Requirements | Transform business understanding into User Stories | **P-003 – Functional Requirements** | Approved Business Understanding Report | `functional-requirements.md` | Team | ⏳ |
| W-005 | Non-Functional Requirements | Define measurable quality attributes | **P-004 – Non-Functional Requirements** | Functional Requirements + Business Understanding Report | `non-functional-requirements.md` | Team | ⏳ |
| W-006 | Acceptance Criteria | Define business validation scenarios | **P-005 – Acceptance Criteria** | Functional Requirements + Non-Functional Requirements | `acceptance-criteria.md` | Team | ⏳ |
| W-007 | Requirements Quality Review | Verify consistency, traceability and completeness | **P-006 – Requirements Review** | FR + NFR + AC | Review Report | Team | ⏳ |
| W-008 | Solution Architecture | Design Alternative A | P-007 | Approved Requirements | TO-BE Alternative A | Team | ⏳ |
| W-009 | Solution Architecture | Design Alternative B | P-008 | Approved Requirements | TO-BE Alternative B | Team | ⏳ |
| W-010 | Architecture Decisions | Document Architectural Decision Records | P-009 | TO-BE Alternatives | ADR | Team | ⏳ |
| W-011 | Architecture Diagrams | Generate C4 Context | P-010 | ADR + TO-BE | C4 Level 1 | Team | ⏳ |
| W-012 | Architecture Diagrams | Generate C4 Containers | P-011 | ADR + TO-BE | C4 Level 2 | Team | ⏳ |
| W-013 | Architecture Diagrams | Generate C4 Components | P-012 | ADR + TO-BE | C4 Level 3 | Team | ⏳ |
| W-014 | Alternative Comparison | Compare both architecture alternatives | P-013 | Alternative A + B | Comparison Matrix | Team | ⏳ |
| W-015 | Final Recommendation | Recommend the preferred architecture | P-014 | Comparison Matrix | Final Recommendation | Team | ⏳ |

---

# Workflow Principles

## Human Validation

Every generated artifact must be reviewed and approved before the next workflow step begins.

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

Readiness Assessment

↓

APROBADO

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
- Functional Requirements
- Non-Functional Requirements
- Acceptance Criteria
- TO-BE Architecture
- ADR
- Final Recommendation

The workflow shall not continue until the current artifact has been approved.

---

## Repository Rule

Generated artifacts shall always be stored in the same initiative folder where the corresponding Architecture Brief (`README.md`) resides.

AI assistants shall never create parallel folder structures unless explicitly instructed.