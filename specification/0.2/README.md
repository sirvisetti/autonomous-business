# ABCS Draft 0.2 — Business Semantics Foundation

The Autonomous Business Capability Specification (ABCS) is an open, vendor-neutral specification for describing business capabilities so humans, agents, applications, and autonomous systems can discover and perform business operations consistently without depending on a particular application vendor or implementation technology.

Status: **Draft / pre-1.0**.

## 1. Scope

ABCS standardizes business meaning. It defines canonical capability identities, canonical Business Objects, business keys and state, relationships, machine-readable contracts, and the minimum invocation/discovery semantics needed to exchange those business meanings consistently.

ABCS does not standardize middleware, integration technology, automation technology, schedulers, workflow engines, agent frameworks, databases, message brokers, authentication products, EDI transports, or vendor-specific APIs.

Normative scope test: a proposed ABCS capability SHOULD still have clear business meaning if humans performed the work manually and all implementation technology disappeared.

## 2. Universal primitive

A **Capability** is the universal executable primitive of ABCS. A Capability represents something meaningful the business can do.

A **Business Domain** classifies capabilities into enduring areas of business responsibility and provides the first identifier namespace segment. Domains do not define different capability types.

Draft 0.2 initial domains are: `procurement`, `finance`, `sales`, `hr`, `service`, `logistics`, `manufacturing`, and `projects`.

Integration, automation, middleware, transport, scheduling infrastructure, and similar technology disciplines are not ABCS business domains.

### Domain maturity in Draft 0.2

- **Reference** — a deep canonical domain used to prove the specification end to end. Procurement is the first reference domain.
- **Modeled** — canonical Business Objects, schemas, keys, relationships, state dimensions, and representative detailed capabilities are defined. Finance, Sales, and Human Resources are modeled domains in Draft 0.2.
- **Initial** — representative capability vocabulary is published while deeper Business Object modeling remains future work. Service, Logistics, Manufacturing, and Projects are initial domains.

Maturity describes the depth of the current ABCS definition, not the importance of the business domain.

## 3. Canonical identifiers

Capability identifiers use:

`<domain>.<business-subject>.<operation>`

Examples:

- `procurement.purchase-order.submit`
- `finance.payment.approve`
- `sales.sales-order.create`
- `hr.leave-request.approve`
- `logistics.shipment.notify`
- `manufacturing.work-order.release`

Business Object identifiers use:

`<domain>.<business-object>`

Examples: `procurement.purchase-order`, `finance.invoice`, `sales.sales-order`, and `hr.worker`.

Segments use lower-case kebab-case.

## 4. Business Objects

A Business Object defines canonical business information used by capabilities. It is not an execution primitive.

A Business Object definition may specify:

- canonical identifier and business definition
- JSON Schema 2020-12 instance schema
- business keys and key scope
- canonical fields
- typed relationships
- lifecycle/state dimensions
- related capabilities
- version and provenance

Canonical schemas MUST NOT embed application-vendor fields or implementation routing/configuration.

Draft 0.2 deeply models:

- Procurement — Purchase Requisition, Supplier, Purchase Order, Receipt
- Finance — Invoice, Payment, Journal Entry, Payment Run
- Sales — Customer, Quote, Sales Order, Return
- Human Resources — Worker, Position, Leave Request, Payroll Run

## 5. Parties and roles

A Party represents a business participant such as an organization or person. Supplier, Customer, Buyer, Seller, Payer, Payee, and Carrier are contextual business roles. Domain objects may expose these domain-specific views while preserving a reusable Party identity/reference model.

A Customer and Supplier therefore MUST NOT be assumed to be unrelated identities merely because they occur in different domains. The same Party may play multiple business roles.

## 6. Capability definition

A capability definition identifies the business operation, its domain, optional associated Business Objects, input/output contracts, and optional business preconditions/effects.

Implementation details are excluded. A capability may be fulfilled by humans, APIs, workflows, autonomous agents, ERP transactions, custom software, or combinations of these without changing its canonical ABCS meaning.

## 7. Scheduling distinction

Scheduling may be a valid business operation when the scheduled subject itself has business meaning, for example `hr.payroll-run.schedule` or `finance.payment-run.schedule`.

Generic technical scheduling such as scheduling a cron job, container job, batch executable, or middleware task is outside ABCS.

Delayed execution of an arbitrary capability is an implementation/runtime concern unless the scheduling action itself has independent business meaning.

## 8. Processes, Policies, and Events

Processes, Policies, Events, Roles, and Relationships are supporting business semantics rather than peer execution primitives.

If a process or decision must be externally executable, it is exposed through a Capability whose identifier describes the business action, not the implementation mechanism.

## 9. Capability invocation envelope

Draft 0.2 defines a small transport-neutral Capability Invocation Envelope containing the ABCS version, canonical capability identifier, request identity, optional business participants, and canonical payload.

The envelope is transport-neutral. HTTP, messaging, EDI transport, authentication, certificates, routing, retries, and middleware are implementation concerns.

## 10. Discovery model

ABCS defines three logical interactions:

- **Discover** — determine which canonical business capabilities are supported.
- **Describe** — obtain the definition and contracts for a capability.
- **Invoke** — request performance of a capability using the canonical envelope.

An optional HTTP binding may map these to `GET /capabilities`, `GET /capabilities/{id}`, and `POST /capabilities`. These paths are conventions, not requirements of the core business semantics.

## 11. Compatibility and versioning

Canonical identifiers MUST preserve their established business meaning.

Compatible changes may add optional fields or additional non-breaking metadata. Breaking changes include removing required fields, changing field meaning, changing business effects, or redefining an established canonical identifier.

Specification version, capability-definition version, and Business Object schema version are separate concerns and MUST NOT be treated as interchangeable.

## 12. Provenance

ABCS follows a GREEN-only source/provenance policy: canonical semantics are based on original work and clearly permissive/open sources whose terms permit reuse. Proprietary or licensing-ambiguous frameworks MUST NOT be used as source material for canonical definitions.

Open standards such as OASIS UBL may be used selectively as semantic references when useful, but ABCS intentionally defines concise business models rather than reproducing external document formats wholesale.

## 13. Conformance

An implementation conforms to an ABCS capability when it declares the canonical capability identifier, preserves the defined business semantics, satisfies the applicable canonical contracts, and clearly exposes any limitations that affect those semantics.

ABCS conformance does not require Sirvisetti Autonomy or any particular technology stack.
