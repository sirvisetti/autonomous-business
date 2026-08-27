# Autonomous Business Capability Specification (ABCS)

ABCS is an open, vendor-neutral specification created and open-sourced by Sirvisetti for describing business capabilities independently of application vendors and implementation technologies.

**Current status:** Draft 0.2

Public site: https://abcs.sirvisetti.com

## Core principle

**Capability is the universal executable primitive.** ABCS domains classify enduring areas of business meaning; they are not technology categories or capability types.

ABCS standardizes business meaning: canonical capability identities, business objects, business relationships, business state, contracts, and the minimum semantics needed to discover and invoke capabilities consistently.

ABCS does **not** standardize middleware, integration technology, automation engines, schedulers, workflow engines, agents, databases, message brokers, authentication products, EDI transports, or application-vendor APIs.

A useful scope test is: **Would this capability still make business sense if humans performed the work manually and all implementation technology disappeared?** If not, it does not belong in ABCS.

## Draft 0.2 scope

Draft 0.2 establishes:

- Capability as the universal executable primitive.
- Business Domain as classification and namespace.
- Canonical Business Objects, keys, fields, relationships, and multidimensional state.
- Initial business domains: Procurement, Finance, Sales, HR, Service, Logistics, Manufacturing, and Projects.
- Procurement as the first deep reference domain.
- Finance, Sales, and Human Resources as modeled domains with canonical Business Objects and representative detailed capability definitions.
- A reusable Party model so Customer, Supplier, Buyer, Seller, Payer, Payee and similar concepts can preserve contextual business roles without duplicating identity.
- Business scheduling semantics for meaningful subjects such as Payment Runs and Payroll Runs while excluding generic scheduler/job concepts.
- A small transport-neutral Capability Invocation Envelope and response envelope.
- Discovery, description, and invocation semantics, with HTTP shown only as an optional binding convention.
- Compatibility/versioning and GREEN-source provenance rules.

## Domain maturity

- **Reference** — deep canonical model used to prove the specification end to end. Procurement is the first reference domain.
- **Modeled** — canonical Business Objects, schemas, relationships, state, and representative detailed capabilities are defined. Finance, Sales, and Human Resources are modeled in Draft 0.2.
- **Initial** — representative capability vocabulary is published but deeper object modeling remains future work.

## Repository layout

- `specification/` — versioned specification text
- `schemas/` — machine-readable JSON Schema 2020-12 definitions
- `domains/` — canonical business-domain catalogs and definitions
- `examples/` — example capability and envelope documents
- root HTML/CSS — static public site deployed by Netlify

## Relationship to Sirvisetti Autonomy

Sirvisetti Autonomy is a reference and commercial implementation of ABCS. ABCS itself is open and implementation-neutral; no ABCS implementation requires Sirvisetti Autonomy.

## License

ABCS specification source is made available under the Apache License 2.0. Sirvisetti and Autonomy brand assets are excluded from the specification license and remain the property of Sirvisetti.
