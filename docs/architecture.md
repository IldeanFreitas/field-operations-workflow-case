# Architecture

## Context flow

```mermaid
flowchart LR
    U[Field operator] --> A[Responsive report workflow]
    A --> S[(Operational report store)]
    A --> E[Evidence store]
    A --> D[Document generation workflow]
    D --> P[Printable report snapshot]
```

The client workflow owns form state and step validation. The operational store
persists reports and child records. The document workflow receives an approved
snapshot and returns a printable representation; it must not mutate a submitted
report.

## State model

```mermaid
stateDiagram-v2
    [*] --> Draft
    Draft --> Draft: Save progress
    Draft --> ReadyForReview: Required steps complete
    ReadyForReview --> Draft: Missing or corrected information
    ReadyForReview --> Submitted: Submit confirmation
    Submitted --> DocumentReady: Generate snapshot
    Submitted --> [*]: Retained as immutable record
    DocumentReady --> [*]
```

## Design decisions

| Decision | Rationale |
|---|---|
| Draft-first workflow | A field report may be completed across multiple interactions. |
| Child records for workforce and services | Repeating business entities should not be stored as concatenated text. |
| Immutable submitted state | Preserves the audit boundary after confirmation. |
| Parent-owned validation | Each step exposes completion rules before submission. |
| Separate document generation | Keeps report persistence independent from presentation output. |
