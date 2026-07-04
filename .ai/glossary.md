# Project Glossary

## Purpose

This glossary defines the official terminology used throughout the project.

The AI assistant shall use these definitions consistently across all generated artifacts.

Industry-standard terminology shall be preserved whenever possible.

---

# Business Terms

## Business Initiative

A strategic business capability selected to improve Fiberlink's current architecture.

Each initiative represents a major transformation objective and is the starting point for Requirements Engineering.

---

## Business Objective

A measurable business outcome expected from one or more initiatives.

Every architecture decision shall support at least one Business Objective.

---

## Business Capability

A business function that enables Fiberlink to deliver value to its customers.

Capabilities are independent from technology implementation.

---

# Requirements Engineering

## Functional Requirement (FR)

A requirement describing a business capability or system behavior.

Functional Requirements describe **what** the solution must do.

---

## Non-Functional Requirement (NFR)

A requirement describing quality attributes of the solution.

Examples include:

- Availability
- Security
- Performance
- Scalability
- Maintainability

---

## Acceptance Criteria

Conditions that determine whether a Functional Requirement has been successfully implemented.

Acceptance Criteria shall be written using Gherkin syntax.

---

## Gherkin

Behavior specification language using:

Given

When

Then

Used to define Acceptance Criteria.

---

# Enterprise Architecture

## AS-IS

Current state of the enterprise architecture.

Represents the existing business, application and technology landscape.

---

## TO-BE

Target architecture proposed by the project.

Represents the desired future state.

---

## Gap Analysis

Comparison between AS-IS and TO-BE architectures.

Used to identify required changes.

---

# TOGAF

## TOGAF

The Open Group Architecture Framework.

The methodology adopted for this project.

---

## ADM

Architecture Development Method.

TOGAF methodology used to develop the architecture.

---

## Migration Planning

ADM phase responsible for defining implementation initiatives and migration roadmap.

The selected initiatives originate from this phase.

---

# Architecture Documentation

## Architecture Brief

A high-level description of an initiative.

It serves as the primary source for generating:

- Functional Requirements
- Non-Functional Requirements
- Acceptance Criteria

---

## Architecture Guideline

A recommendation that influences architectural decisions.

Guidelines are not mandatory rules but should normally be followed.

---

## Architecture Pattern

A reusable architectural solution addressing a recurring design problem.

Examples:

- API Gateway
- Event-Driven Architecture
- Microservices
- Layered Architecture

---

## Architecture Principle

A fundamental rule governing all architectural decisions.

Principles have higher priority than guidelines.

---

## Architecture Decision Record (ADR)

A document recording a significant architectural decision.

Every ADR includes:

- Context
- Decision
- Consequences
- Alternatives Considered

---

## Assumption

A statement accepted as true until verified.

Architectural assumptions shall always be documented through an ADR.

Assumptions shall never be treated as confirmed facts.

---

# Solution Architecture

## Alternative A

Cloud Native architecture emphasizing Event-Driven Architecture, scalability and loose coupling.

---

## Alternative B

Enterprise Architecture based on Managed Platforms emphasizing operational simplicity, maintainability and cost-benefit.

---

## C4 Model

Architecture visualization model adopted by the project.

Required levels:

- Context
- Containers
- Components

---

## Mermaid

Text-based diagram notation used to version architecture diagrams.

Preferred notation for architecture documentation.

---

# Integration

## API

Application Programming Interface.

Primary integration mechanism.

---

## API Gateway

Centralized component exposing, securing and governing APIs.

---

## Enterprise Integration Platform

Central platform responsible for application interoperability.

---

## Event

A business occurrence communicated asynchronously between applications.

---

## Event-Driven Architecture (EDA)

Architecture style based on event publication and consumption.

Used only where it provides measurable value.

---

## Loose Coupling

Architectural characteristic minimizing dependencies between systems.

---

# Security

## Zero Trust

Security model assuming no implicit trust.

Authentication and authorization are always required.

---

## OAuth2

Authorization protocol used to secure APIs.

---

## OpenID Connect (OIDC)

Authentication layer built on OAuth2.

---

# Observability

## Observability

Capability to understand the internal state of a system using:

- Metrics
- Logs
- Traces

---

## Metrics

Numerical measurements describing system behavior.

---

## Logs

Chronological records of application events.

---

## Traces

End-to-end execution records across distributed components.

---

## Alert

Notification generated when predefined operational conditions are met.

---

## MTTR

Mean Time To Recovery.

Average time required to restore a service.

---

## MTTD

Mean Time To Detect.

Average time required to detect an incident.

---

# Cloud

## Microsoft Azure

Preferred cloud platform for this project.

---

## Azure Architecture Icons

Official Microsoft icons used in presentation-quality diagrams.

---

# Repository

## Repository

The complete Git repository containing project documentation.

Acts as the single source of truth.

---

## Workspace

Local copy of the repository opened by Kiro.

The AI assistant works on the Workspace, not directly on GitHub.

---

## GitHub

Remote repository used for version control and collaboration.

---

## Single Source of Truth

The repository is the authoritative source for all project documentation.

All generated artifacts shall remain consistent with the repository.

---

# Naming Convention

The following abbreviations shall be used consistently.

| Abbreviation | Meaning |
|--------------|---------|
| FR | Functional Requirement |
| NFR | Non-Functional Requirement |
| ADR | Architecture Decision Record |
| API | Application Programming Interface |
| EDA | Event-Driven Architecture |
| C4 | Context, Containers, Components, Code |
| SLA | Service Level Agreement |
| MTTR | Mean Time To Recovery |
| MTTD | Mean Time To Detect |
| OSS | Operations Support System |
| CRM | Customer Relationship Management |
| ERP | Enterprise Resource Planning |
| GIS | Geographic Information System |
| NMS | Network Management System |

---

# Terminology Policy

The AI assistant shall:

- Reuse the terminology defined in this glossary.
- Avoid introducing alternative names for existing concepts.
- Preserve industry-standard terminology in English.
- Maintain consistency across all project documentation.