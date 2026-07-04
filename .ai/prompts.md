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

---

## Step 3 – Understand the Current Project Phase

The project is currently focused on **Deliverable 2 – Requirements Engineering**.

The objective of this deliverable is to define the Functional Requirements (FR), Non-Functional Requirements (NFR) and Acceptance Criteria for the selected business initiatives.

The repository already contains an Architecture Brief (`README.md`) for each initiative.

These Architecture Briefs are the authoritative business input for Requirements Engineering.

Functional Requirements, Non-Functional Requirements and Acceptance Criteria may or may not exist at this stage of the project.

When they exist, they shall be considered the official source of requirements and shall be used as the primary input for all subsequent deliverables, especially Deliverable 3 (Solution Architecture).

Until they are available, the Architecture Brief shall be considered the primary source of information.

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

- Read existing documentation.
- Reuse repository terminology.
- Preserve document structure.
- Maintain end-to-end traceability.
- Follow the Architecture Policy defined in `.ai/architecture.md`.
- Respect the repository organization.

You shall not:

- Invent business requirements.
- Modify approved documentation.
- Change the repository organization.
- Generate deliverables that have not been requested.
- Treat assumptions as confirmed facts.

Whenever assumptions are necessary, they shall be explicitly identified and documented according to the Architecture Policy.

---

## Step 6 – Initialization Assessment

Do not generate any project documentation.

Instead, analyze the repository and confirm your understanding by providing:

1. Executive summary of the project.
2. Current project phase.
3. Selected business initiatives.
4. Objective of Deliverable 2.
5. Expected outputs of Deliverable 2.
6. Repository organization.
7. Primary documentation that will be used to generate the current deliverables.
8. Inconsistencies, ambiguities or missing information detected in the repository.
9. Cross-document dependencies identified.
10. Risks or recommendations that may affect future deliverables.

This assessment is informational only.

Do not modify any file.

Wait for the next instruction before generating or modifying any documentation.