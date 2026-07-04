# AI Collaboration Best Practices

## Purpose

This document captures the working practices adopted by the project team to ensure effective collaboration between human architects and AI assistants (Kiro, ChatGPT or similar).

These practices are intended to improve consistency, traceability, repository quality and architectural governance throughout the project lifecycle.

---

# BP-001 – Separate Draft and Official Documentation

## Objective

Prevent AI assistants from generating architecture based on unapproved requirements.

## Practice

Project documentation may exist in two states:

- Draft
- Official

Draft documents shall use the `-draft` suffix.

Example:

functional-requirements-draft.md

Official documents shall not include the suffix.

Example:

functional-requirements.md

## Rule

Unless explicitly instructed otherwise, AI assistants shall always use the official version.

## Benefits

- Prevents inconsistencies.
- Preserves traceability.
- Supports collaborative work.
- Ensures architecture is based on approved requirements.

---

# BP-002 – Commit by Milestone

## Objective

Maintain a clean and recoverable Git history.

## Practice

Create a Git commit after completing a meaningful milestone instead of accumulating many unrelated changes.

Examples:

- Repository initialization
- AI Knowledge Base completed
- Initiative 1 Functional Requirements
- Initiative 1 Non-Functional Requirements
- Initiative 1 Acceptance Criteria
- C4 diagrams
- ADRs

## Benefits

- Easier rollback.
- Better traceability.
- Improved collaboration.
- Cleaner project history.

---

# BP-003 – Repository Health Check

## Objective

Validate repository consistency before generating major project artifacts.

## Practice

Before starting a significant deliverable (Requirements, ADR, C4, TO-BE alternatives, etc.), execute the Project Initialization prompt.

Review the following sections carefully:

- Repository organization
- Missing documentation
- Inconsistencies
- Ambiguities
- Cross-document dependencies

## Benefits

- Detects documentation gaps.
- Identifies architectural dependencies.
- Improves repository quality.
- Prevents propagation of inconsistencies.

---

# BP-004 – Verify AI Findings

## Objective

Validate AI observations before modifying the repository.

## Practice

AI findings should be treated as recommendations, not facts.

When the AI reports missing files, folders or inconsistencies:

- Verify the repository manually.
- Confirm the reported issue.
- Update prompts if necessary.
- Only modify the repository after validation.

## Benefits

- Prevents unnecessary repository changes.
- Improves prompt quality.
- Builds confidence in AI-assisted workflows.

---

# BP-005 – One Artifact at a Time

## Objective

Improve documentation quality and reviewability.

## Practice

Generate a single architecture artifact per interaction.

Examples:

- Functional Requirements
- Non-Functional Requirements
- Acceptance Criteria
- ADR
- C4 Level 1
- C4 Level 2

Avoid generating complete deliverables in a single request.

## Benefits

- Easier review.
- Better consistency.
- Reduced rework.
- Improved traceability.

---

# BP-006 – Architecture Before Generation

## Objective

Ensure the AI understands the project before producing documentation.

## Practice

Every new AI session shall begin with the Project Initialization prompt.

The AI must understand:

- Project context
- Architecture policy
- Repository organization
- Terminology
- Current project phase

before generating any deliverable.

## Benefits

- Reduces hallucinations.
- Improves consistency.
- Produces higher-quality documentation.

---

# BP-007 – Repository as the Single Source of Truth

## Objective

Ensure all generated artifacts are based on repository knowledge.

## Practice

The repository is the authoritative knowledge base.

AI assistants shall:

- Read existing documentation.
- Reuse repository terminology.
- Maintain traceability.
- Avoid introducing undocumented assumptions.

## Benefits

- Consistent documentation.
- Knowledge reuse.
- Better collaboration.
- Long-term maintainability.

---

# BP-008 – Document Assumptions Through ADR

## Objective

Prevent assumptions from becoming undocumented architectural decisions.

## Practice

Whenever assumptions are required:

- Clearly identify them.
- Document the rationale.
- Evaluate their potential impact.
- Record them in the corresponding Architecture Decision Record (ADR).

Assumptions shall never be presented as confirmed facts.

## Benefits

- Better architectural governance.
- Improved decision traceability.
- Easier future validation.

---

# BP-009 – AI Learns the Project Before Solving It

## Objective

Treat the AI as a project team member rather than a document generator.

## Practice

Before generating documentation, ensure the AI has:

- Read the AI Knowledge Base.
- Inspected the repository.
- Understood the project phase.
- Identified dependencies.
- Confirmed repository consistency.

Generation begins only after understanding is confirmed.

## Benefits

- Higher-quality outputs.
- Better architectural reasoning.
- Reduced prompt complexity.
- More predictable results.

---

# BP-010 – Decision Hierarchy

## Objective

Separate project governance decisions from architecture design decisions in order to maintain clear traceability and avoid mixing strategic, architectural and implementation concerns.

## Practice

Decisions shall be documented according to their scope and level of responsibility.

### Project Decisions

Project governance decisions shall be recorded in:

.ai/decisions.md

These decisions define how the project is managed, documented and governed.

Examples include:

- Repository organization
- Documentation language
- Selected methodology
- Cloud platform
- Documentation standards
- AI collaboration policies

### Architecture Decisions

Solution Architecture decisions shall be documented as Architecture Decision Records (ADR).

Location:

docs/03-solution-architecture/adr/

Examples include:

- API Management selection
- Integration style
- Event broker selection
- Authentication mechanism
- Observability platform

### Implementation Decisions

Technical implementation decisions belong to deployment or implementation documentation and shall not be recorded in Project Decisions.

## Benefits

- Clear governance model.
- Better architectural traceability.
- Separation of responsibilities.
- Easier maintenance.
- Consistent documentation.

---

# BP-011 – One Objective per Conversation

## Objetivo

Mantener el foco y evitar iteraciones innecesarias cuando se trabaja con IA.

## Práctica

Antes de comenzar una sesión, definir explícitamente un único objetivo.

### Ejemplos:

Completar el repositorio.
Diseñar el contexto para Kiro.
Generar los RF de la Iniciativa 1.
Revisar el C4 de la Alternativa A.

No mezclar varios entregables o problemas en la misma conversación.

## Beneficios

Reduce cambios de contexto.
Disminuye la probabilidad de entrar en bucles.
Facilita la validación del resultado.
Produce artefactos más consistentes
---

# BP-012 – Quality Gate Before Requirements

## Objetivo

Asegurar que existe suficiente comprensión del negocio antes de definir los requisitos.

## Práctica

Todo Business Understanding Report deberá finalizar con una evaluación de preparación (Readiness Assessment), indicando si la iniciativa está lista para pasar a la fase de Requirements Engineering.

La evaluación debe considerar, como mínimo:

Comprensión del problema de negocio.
Objetivos claramente definidos.
Alcance identificado.
Actores y aplicaciones involucradas.
Riesgos y supuestos documentados.
Información faltante que pueda afectar la calidad de los requisitos.

## Regla

Los RF no deben generarse hasta que el Business Understanding Report concluya con una recomendación explícita de GO o NO GO.

---

# BP-013 – Repository Structure First

## Objective

Prevent AI assistants from creating parallel repository structures.

## Practice

When generating or persisting documentation:

Reuse the existing repository structure.
Persist artifacts in the same initiative folder as the corresponding Architecture Brief.
Never infer or create alternative directory names.
If the target location is ambiguous, ask for clarification before creating new folders.

## Benefits

Preserves repository consistency.
Avoids duplicated documentation.
Maintains traceability.
Prevents fragmentation of project knowledge.
---

# Continuous Improvement

These practices are living guidelines.

New Best Practices should be added whenever the team identifies a repeatable improvement that enhances collaboration between architects and AI assistants.