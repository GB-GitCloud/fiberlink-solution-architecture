# Project Context

## Project Overview

**Project Name:** Fiberlink Solution Architecture

This repository contains the complete documentation for the Final Integrative Project of the **Arquitectura de Solución Multinube** program.

The repository serves as the **single source of truth** for architecture documentation, requirements, design decisions and deliverables.

The objective is to design a modern cloud-ready Target Architecture (TO-BE) for the Fiberlink Telecom case study following TOGAF ADM and Enterprise Architecture best practices.

---

# Business Context

Fiberlink Telecom is evolving its technology landscape to improve operational efficiency, business agility and customer experience.

The organization currently operates multiple enterprise applications with limited interoperability, manual operational processes and fragmented monitoring capabilities.

The proposed architecture addresses these challenges through three strategic initiatives.

---

# Selected Business Initiatives

## Initiative 1

Enterprise Integration Platform

Purpose

Implement a centralized integration platform based on APIs and Event-Driven Architecture to eliminate point-to-point integrations and improve interoperability.

---

## Initiative 2

Operations Automation

Purpose

Automate operational processes across CRM, OSS and supporting platforms to reduce manual effort, increase operational efficiency and improve SLA compliance.

---

## Initiative 3

Observability Platform

Purpose

Implement a centralized observability platform providing metrics, logs, traces and events to improve monitoring, incident response and operational visibility.

---

# Methodology

The project follows the TOGAF ADM methodology.

Relevant ADM phases include:

- Preliminary
- Architecture Vision
- Business Architecture
- Information Systems Architecture
- Technology Architecture
- Opportunities and Solutions
- Migration Planning

The current repository focuses primarily on the outputs of Migration Planning and Solution Architecture.

---

# Project Deliverables

## Deliverable 1

Current Architecture (AS-IS)

Includes:

- Business Architecture
- Application Architecture
- Technology Architecture
- Enterprise Architecture Diagrams
- Current Capability Assessment
- Architecture Initiatives

Status

Completed.

---

## Deliverable 2

Requirements Engineering

Includes:

- Architecture Brief per Initiative
- Functional Requirements (RF)
- Non-Functional Requirements (RNF)
- Acceptance Criteria (Gherkin)

Requirements are organized independently for each selected initiative.

---

## Deliverable 3

Solution Architecture

For the selected initiatives, develop two TO-BE solution alternatives.

Each alternative includes:

- Solution Description
- C4 Model
    - Level 1 (Context)
    - Level 2 (Containers)
    - Level 3 (Components)
- Architecture Guidelines
- Architecture Patterns
- Architectural Decision Records (ADR)
- APIs (when applicable)
- Solution Comparison
- Final Recommendation

---

## Deliverable 4

Cloud Demonstration

The selected TO-BE architecture shall be validated through a deployment demonstration.

The implementation may use mock services where business systems are unavailable.

Expected artifacts include:

- Deployment Architecture
- Cloud Resources
- API Mock Services
- Monitoring Demonstration
- Deployment Documentation
- Demo Evidence

---

# Repository Structure

The repository is organized as follows.

docs/

01-contexto

02-enterprise-architecture

03-solution-architecture

04-reference-architecture

05-entregables

06-presentations

Supporting folders

.ai

diagrams

templates

images

---

# Primary Sources

For Deliverable 2

Primary source:

README.md located inside each initiative folder.

Those documents represent the Architecture Brief.

They are the only input required for generating:

- Functional Requirements
- Non-Functional Requirements
- Acceptance Criteria

For Deliverable 3

Primary sources include:

- Initiative Architecture Brief
- Requirements
- Acceptance Criteria
- ADR
- Architecture Guidelines
- Architecture Patterns

Enterprise Architecture diagrams should only be consulted when additional architectural context is required.

---

# Architecture Representation

The preferred architecture notation is:

1. Mermaid
2. C4 Model
3. Draw.io

Architecture diagrams shall also be exported to PNG and SVG when required for presentations.

---

# Cloud Platform

The preferred cloud provider for this project is Microsoft Azure.

Architecture diagrams shall use Azure services and official Azure Architecture Icons whenever graphical diagrams are produced.

Mermaid diagrams shall identify Azure services using their official service names.

---

# Traceability

Every architecture artifact shall maintain end-to-end traceability.

Business Initiative

↓

Requirements

↓

Acceptance Criteria

↓

Architecture Decisions

↓

Architecture Guidelines

↓

Architecture Patterns

↓

C4 Solution Architecture

↓

Cloud Demonstration

↓

Final Presentation

---

# Project Objective

Produce a complete, consistent and traceable Solution Architecture that satisfies the business initiatives and can be demonstrated through a cloud deployment using architecture best practices.