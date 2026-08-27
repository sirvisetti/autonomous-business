# ABCS Governance

The Autonomous Business Capability Specification (ABCS) is created and stewarded by Sirvisetti and developed in the open.

## Business-only scope gate

Every proposed domain, capability, Business Object, field, relationship, process, policy, or event must express enduring business meaning rather than implementation technology.

Primary test: **Would this still make business sense if humans performed the work manually and all implementation technology disappeared?**

Middleware, integration infrastructure, generic automation, transports, schedulers, vendor APIs, databases, message brokers and similar implementation concerns are outside canonical ABCS.

## Capability principle

Capability is the universal executable primitive. Business Domains classify capability meaning and provide namespaces; they do not create different capability types.

## Domain maturity

- **Reference** — modeled in depth and used to demonstrate the full ABCS pattern.
- **Modeled** — has canonical Business Objects, schemas, business keys/state/relationships, and representative Capability definitions.
- **Initial** — vocabulary/catalog only; not yet modeled in depth.

Maturity labels describe specification completeness, not market adoption.

## Provenance

ABCS follows a GREEN-only provenance policy. Canonical content must be original work or based on clearly permissive/open material whose terms allow the intended use. Proprietary or licensing-ambiguous frameworks must not be used as canonical source material. See `PROVENANCE.md`.

## Representations

ABCS maintains one logical model. YAML is the maintained human-authoring representation for modular definitions, JSON is the preferred machine publication/interchange representation, and JSON Schema 2020-12 is the normative validation language. See `FORMATS.md`.

## Compatibility

Canonical identifiers retain their established business meaning. Breaking semantic changes require explicit version treatment and must not silently redefine an existing identifier.

## Positioning

ABCS may be described as an open, vendor-neutral specification created and open-sourced by Sirvisetti. It must not be described as an industry standard or as widely adopted without supporting evidence.

## Stewardship

Sirvisetti maintains the public repository, reviews proposed canonical changes, and publishes draft/release versions. Contributions and independent implementations are welcome.
