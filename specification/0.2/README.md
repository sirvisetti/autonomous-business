# ABCS Draft 0.2 — Business Semantics Foundation

The Autonomous Business Capability Specification (ABCS) is an open, vendor-neutral specification for describing business capabilities so humans, agents, applications, and autonomous systems can discover and perform business operations consistently without depending on a particular application vendor or implementation technology.

Status: **Draft / pre-1.0**.

## 1. Scope

ABCS standardizes business meaning. It defines canonical Capability identities, canonical Business Objects, business keys and state, relationships, machine-readable contracts, and the minimum invocation/discovery semantics needed to exchange those business meanings consistently.

ABCS does not standardize middleware, integration technology, automation technology, schedulers, workflow engines, agent frameworks, databases, message brokers, authentication products, EDI transports, or vendor-specific APIs.

Normative scope test: a proposed ABCS capability SHOULD still have clear business meaning if humans performed the work manually and all implementation technology disappeared.

## 2. Universal primitive

A **Capability** is the universal business primitive of ABCS. A Capability represents something meaningful the business can do. Implementations may make a Capability executable, but execution technology does not define its business meaning.

A **Business Domain** classifies capabilities into enduring areas of business responsibility and provides the first identifier namespace segment. Domains do not define different capability types.

Draft 0.2 initial domains are: `procurement`, `finance`, `sales`, `hr`, `service`, `logistics`, `manufacturing`, and `projects`.

Integration, automation, middleware, transport, scheduling infrastructure, and similar technology disciplines are not ABCS business domains.

## 3. Domain maturity

Draft 0.2 uses three specification-completeness labels:

- **Reference** — modeled in depth and used to demonstrate the full ABCS pattern.
- **Modeled** — canonical Business Objects, schemas, business keys/state/relationships, and representative Capability definitions are present.
- **Initial** — vocabulary/catalog only.

Procurement is the Draft 0.2 reference domain. Finance, Sales, HR, Service, Logistics, Manufacturing, and Projects are modeled domains. Maturity is not a statement of market adoption.

## 4. Canonical identifiers

Capability identifiers use `<domain>.<business-subject>.<operation>`. Business Object identifiers use `<domain>.<business-object>`. Segments use lower-case kebab-case.

Examples include `procurement.purchase-order.submit`, `finance.payment.approve`, `hr.payroll-run.schedule`, `service.customer-case.resolve`, `logistics.shipment.dispatch`, `manufacturing.work-order.release`, and `projects.project-time.approve`.

## 5. Business Objects

A Business Object defines canonical business information used by capabilities. It is not an execution primitive. A Business Object definition may specify canonical identity, JSON Schema 2020-12 instance schema, business keys and key scope, canonical fields, typed relationships, lifecycle/state dimensions, related capabilities, version, and provenance.

Canonical schemas MUST NOT embed application-vendor fields or implementation routing/configuration.

## 6. Parties and roles

A Party represents a business participant such as an organization or person. Supplier, Customer, Buyer, Seller, Payer, Payee, Carrier, Worker, Sponsor, and similar terms may represent contextual business roles or domain-specific relationships.

## 7. Capability definition

A Capability definition identifies the business operation, its domain, optional associated Business Objects, input/output contracts, and optional business preconditions/effects. Implementation details are excluded.

## 8. Scheduling distinction

Scheduling may be a valid business operation when the scheduled subject itself has business meaning, for example `hr.payroll-run.schedule` or `finance.payment-run.schedule`. Generic technical scheduling remains outside ABCS.

## 9. Processes, Policies, and Events

Processes, Policies, Events, Roles, and Relationships are supporting business semantics rather than peer business primitives. If a process or decision must be externally performed, it is exposed through a Capability whose identifier describes the business action, not the implementation mechanism.

## 10. Capability invocation envelope

Draft 0.2 defines a small transport-neutral Capability Invocation Envelope containing the ABCS version, canonical capability identifier, request identity, optional business participants, and canonical payload. HTTP, messaging, EDI transport, authentication, certificates, routing, retries, and middleware are implementation concerns.

## 11. Discovery model

ABCS defines three logical interactions: **Discover**, **Describe**, and **Invoke**. An optional HTTP binding may map these to `GET /capabilities`, `GET /capabilities/{id}`, and `POST /capabilities`.

## 12. Representation and validation

ABCS defines one logical machine-readable model rather than separate YAML and JSON semantics.

- Modular definition source is maintained in YAML 1.2 restricted to the JSON-compatible data model.
- JSON is the preferred machine publication/interchange representation.
- JSON Schema 2020-12 is the normative validation language for canonical payloads and definition structures.
- Generated JSON MUST be semantically equivalent to the maintained YAML source; a mismatch is a publication defect.

The aggregate Draft 0.2 business catalog is published in both YAML and JSON.

## 13. Compatibility and versioning

Canonical identifiers MUST preserve their established business meaning. Compatible changes may add optional fields or additional non-breaking metadata. Breaking changes include removing required fields, changing field meaning, changing business effects, or redefining an established canonical identifier.

Specification version, Capability-definition version, and Business Object schema version are separate concerns.

## 14. Provenance

ABCS follows a GREEN-only source/provenance policy. Canonical semantics are based on original work and clearly open sources whose terms allow the intended use. Proprietary or licensing-ambiguous frameworks MUST NOT be used as source material.

Open references are used selectively for semantic cross-checking rather than copied wholesale. The repository `PROVENANCE.md` records reviewed sources and their disposition.

## 15. Conformance

An implementation conforms to an ABCS capability when it declares the canonical capability identifier, preserves the defined business semantics, satisfies the applicable canonical contracts, and clearly exposes any limitations that affect those semantics.

ABCS conformance does not require Sirvisetti Autonomy or any particular technology stack.
