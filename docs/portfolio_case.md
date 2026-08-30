# Case study: field operations workflow

**Status:** Arquitetura documentada — anonymized public reference.

## Context

The case addresses the collection and closure of daily field activity through a
multi-step workflow that works across desktop and mobile contexts.

## Responsibility

I structured the report lifecycle, screen-to-state flow, data relationships,
validation strategy, submission lock, document-snapshot boundary, and test
scenarios represented in this public reference.

## Evidence

- [Architecture and state model](architecture.md)
- [Synthetic report schema](../models/field_report.schema.json)
- [Synthetic example](../samples/field_report.sample.json)
- [Test scenarios](test_scenarios.md)

## Limitations

The public case is not a runnable production application. It makes no claim
about a specific customer, deployment, business metric, or production dataset.
