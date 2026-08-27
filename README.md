# Autonomous Business Capability Specification (ABCS)

ABCS is an open, vendor-neutral specification created and open-sourced by Sirvisetti for describing business capabilities independently of application vendors and implementation technologies.

**Current status:** Draft 0.2

Public site: https://abcs.sirvisetti.com

## Core principle

**Capability is the universal executable primitive.** ABCS domains classify enduring areas of business meaning; they are not technology categories or capability types.

ABCS standardizes business meaning: canonical capability identities, Business Objects, relationships, business state, contracts, and the minimum semantics needed to discover and invoke capabilities consistently.

ABCS does **not** standardize middleware, integration technology, automation engines, schedulers, workflow engines, agents, databases, message brokers, authentication products, EDI transports, or application-vendor APIs.

Scope test: **Would this capability still make business sense if humans performed the work manually and all implementation technology disappeared?** If not, it does not belong in ABCS.

## Draft 0.2 scope

Draft 0.2 establishes eight initial business domains: Procurement, Finance, Sales, Human Resources, Service, Logistics, Manufacturing, and Projects. Procurement is the reference domain; the other seven are modeled domains with canonical Business Objects, schemas, state, relationships, and representative capabilities.

## Machine-readable representations

ABCS maintains modular YAML 1.2 source definitions restricted to the JSON-compatible data model, publishes machine-facing JSON artifacts where useful, and uses JSON Schema 2020-12 as the normative validation language. See `FORMATS.md`.

The aggregate Draft 0.2 catalog is published in both `catalog/abcs-0.2.yaml` and `catalog/abcs-0.2.json` from the same logical model.

## Provenance

ABCS follows a GREEN-only provenance policy. See `PROVENANCE.md` for the reviewed open semantic references and their disposition.

## Repository layout

- `specification/` — versioned specification text
- `schemas/` — machine-readable JSON Schema 2020-12 definitions
- `domains/` — canonical business-domain catalogs and definitions
- `catalog/` — generated aggregate publication representations
- `examples/` — example capability and envelope documents
- root HTML/CSS — static public site deployed by Netlify

## Relationship to Sirvisetti Autonomy

Sirvisetti Autonomy is a reference and commercial implementation of ABCS. ABCS itself is open and implementation-neutral; no ABCS implementation requires Sirvisetti Autonomy.

## License

ABCS specification source is made available under the Apache License 2.0. Sirvisetti and Autonomy brand assets are excluded from the specification license and remain the property of Sirvisetti.
