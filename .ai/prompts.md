# Project Prompts

# P-001 – Project Initialization

## Objective

You are joining an ongoing Solution Architecture project for the "Arquitectura de Solución Multinube" program.

Your first responsibility is to understand the project, the repository organization, the architecture policies, the terminology and the current project phase before generating any documentation.

Do not create, modify or delete any file during this initialization.

---

## Step 1 – Read the AI Knowledge Base

Read and understand the following documents located in the `.ai` folder:

- context.md
- architecture.md
- glossary.md

These documents define:

- Project context
- Architecture methodology
- Architecture policies
- Documentation standards
- Repository organization
- Terminology
- AI collaboration rules

These documents are the authoritative source for understanding how this project is organized.

---

## Step 2 – Inspect the Repository

Perform a recursive inspection of the entire repository.

Do not limit your analysis to the currently opened files.

Inspect every directory and every Markdown document available in the repository.

Assume that relevant project information may exist anywhere within the repository.

Repository inspection is mandatory.

If any referenced document or folder cannot be found, explicitly indicate the path(s) that were inspected before reporting it as missing.

Do not modify the repository structure.

Understand the purpose of every major folder before generating documentation.

Identify existing requirements artifacts before concluding that documentation is missing.

Respect the workflow defined in `.ai/workflow.md` when determining the current project phase.

---

## Step 3 – Understand the Current Project Phase

The project is currently focused on **Deliverable 2 – Requirements Engineering**.

The objective of this deliverable is to define the business and solution requirements for each selected initiative.

The repository already contains an Architecture Brief (`README.md`) for each initiative.

These Architecture Briefs represent the primary business input for Requirements Engineering.

The expected Requirements Engineering artifacts for each initiative are:

- Business Understanding Report
- Assumptions Register
- Functional Requirements (FR)
- Non-Functional Requirements (NFR)
- Acceptance Criteria

Business Understanding and the Assumptions Register provide the business context required to derive the Functional Requirements.

Whenever these artifacts already exist and have been approved, they become the official source of requirements for all subsequent deliverables, especially Deliverable 3 (Solution Architecture).

Until they are available, the Architecture Brief shall be considered the authoritative source of information.

---

## Step 4 – Documentation Precedence

Always use the following order of precedence when analyzing project documentation:

1. Official project documentation
2. Approved repository documentation
3. Architecture Briefs (README.md)
4. Draft documents (`*-draft.md`) only when explicitly requested

If both draft and official versions exist, always use the official version unless instructed otherwise.

Never replace approved documentation.

Never generate alternative versions unless explicitly requested.

---

## Step 5 – Working Rules

Before generating any artifact, you shall:

- Read existing repository documentation.
- Reuse repository terminology.
- Preserve repository structure.
- Maintain end-to-end traceability.
- Follow the Architecture Policy defined in `.ai/architecture.md`.
- Respect the repository organization.
- Distinguish between facts, assumptions and architectural decisions.

You shall not:

- Invent business requirements.
- Modify approved documentation.
- Change the repository organization.
- Generate deliverables that have not been requested.
- Present assumptions as confirmed facts.

When repository information is insufficient to continue the analysis:

- Formulate explicit assumptions only when necessary.
- Assign a unique identifier to every assumption.
- Document assumptions in the corresponding `assumptions.md` file.
- Include rationale, affected artifacts, impact and confidence level.
- Ensure assumptions remain fully traceable throughout the repository.

---

## Step 6 – Initialization Assessment

Do not generate any project documentation.

Instead, analyze the repository and confirm your understanding by providing:

1. Executive Summary of the project.
2. Current project phase.
3. Selected business initiatives.
4. Objective of Deliverable 2.
5. Expected outputs of Deliverable 2.
6. Repository organization.
7. Primary documentation that will be used during Requirements Engineering.
8. Inconsistencies, ambiguities or missing information detected.
9. Cross-document dependencies.
10. Risks or recommendations affecting future deliverables.
11. Potential assumptions that should be documented in the corresponding Assumptions Register before Requirements Engineering begins.

This assessment is informational only.

Do not modify any file.

Wait for the next instruction before generating or modifying project documentation.