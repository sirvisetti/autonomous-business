# ABCS Changelog

## Draft 0.2

Draft 0.2 expands ABCS from the initial Procurement proof set into a business-semantics foundation.

- Establishes Capability as the universal executable primitive.
- Replaces Resource terminology with Business Object.
- Defines Business Domain as classification/namespace, not a capability type.
- Establishes eight initial business domains: Procurement, Finance, Sales, HR, Service, Logistics, Manufacturing, and Projects.
- Deepens Procurement as the reference domain.
- Models Finance, Sales, HR, Service, Logistics, Manufacturing, and Projects with canonical Business Objects, schemas, business keys, state, relationships, and representative capabilities.
- Adds reusable Party, Identifier, Address, Monetary Amount, Quantity, and Business Object Reference schemas.
- Adds Capability Invocation, Response, and Discovery schemas.
- Introduces Discover, Describe, and Invoke semantics with HTTP only as an optional binding convention.
- Defines YAML/JSON representation policy with JSON Schema 2020-12 as the normative validation language.
- Publishes an aggregate business catalog in both YAML and JSON.
- Adds a GREEN provenance register and explicit handling of open semantic references.
- Clarifies the hard business-only scope boundary and compatibility/versioning guidance.

## Draft 0.1

Initial public proof release establishing canonical capability identifiers, a capability schema, governance principles, and a small Procurement capability set.
