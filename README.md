# Autonomous Business Standard (ABS)

The **Autonomous Business Standard (ABS)** is an emerging open standards project created and stewarded by Sirvisetti for defining vendor-neutral business capabilities and canonical business semantics.

Its normative specification is the **Autonomous Business Capability Specification (ABCS)**.

**Current normative specification:** ABCS Draft 0.2  
**Public site:** https://abs.sirvisetti.com

> ABS is an emerging open standard. It is not currently represented as an established industry standard, a standards-body-approved standard, or a widely adopted standard.

## Core principle

**Capability is the universal business primitive.** ABCS domains classify enduring areas of business meaning; they are not technology categories or capability types.

Scope test: **Would this capability still make business sense if humans performed the work manually and all implementation technology disappeared?** If not, it does not belong in ABCS.

A capability may be executable by an implementation, but ABCS defines the enduring **business meaning** rather than the execution technology.

## Draft 0.2 scope

ABCS Draft 0.2 establishes eight initial business domains: Procurement, Finance, Sales, Human Resources, Service, Logistics, Manufacturing, and Projects. Procurement is the reference domain; the other seven are modeled domains with canonical Business Objects, schemas, state, relationships, and representative capabilities.

## Machine-readable representations

ABCS maintains modular YAML 1.2 source definitions restricted to the JSON-compatible data model, publishes machine-facing JSON artifacts where useful, and uses JSON Schema 2020-12 as the normative validation language. See `FORMATS.md`.

The aggregate Draft 0.2 catalog is published in both `catalog/abcs-0.2.yaml` and `catalog/abcs-0.2.json` from the same logical model.

## Reference implementation

The lightweight, non-normative reference implementation is maintained separately at:

`https://github.com/sirvisetti/autonomous-business-reference`

The reference depends on ABCS. ABCS does not depend on the reference implementation.

## Provenance

ABCS follows a GREEN-only provenance policy. See `PROVENANCE.md` for reviewed open semantic references and their disposition.

## Repository layout

- `specification/` — versioned ABCS specification text
- `schemas/` — normative JSON Schema 2020-12 contracts
- `domains/` — canonical business-domain catalogs and definitions
- `catalog/` — aggregate YAML/JSON publication representations
- `examples/` — example capability and envelope documents
- root HTML/CSS — ABS public website deployed with AWS Amplify Hosting

## Relationship to Sirvisetti Autonomy

Sirvisetti Autonomy is a production-grade commercial implementation that can implement ABCS. ABS and ABCS remain open and implementation-neutral; no conforming implementation requires Sirvisetti Autonomy.

## License

ABCS specification source is made available under the Apache License 2.0. Sirvisetti and Autonomy brand assets are excluded from the specification license and remain the property of Sirvisetti.
