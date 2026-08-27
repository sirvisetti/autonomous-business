# ABCS Changelog

## Draft 0.2

Draft 0.2 expands ABCS from the initial Procurement proof set into a business-semantics foundation.

- Establishes Capability as the universal executable primitive.
- Replaces Resource terminology with Business Object.
- Defines Business Domain as classification/namespace, not a capability type.
- Adds initial business-domain catalogs for Procurement, Finance, Sales, HR, Service, Logistics, Manufacturing, and Projects.
- Deepens Procurement with canonical Purchase Requisition, Purchase Order, Supplier, and Receipt definitions.
- Deepens Finance with canonical Invoice, Payment, Journal Entry, and Payment Run definitions and representative detailed capabilities.
- Deepens Sales with canonical Customer, Quote, Sales Order, and Return definitions and representative detailed capabilities.
- Deepens Human Resources with canonical Worker, Position, Leave Request, and Payroll Run definitions and representative detailed capabilities.
- Clarifies Customer and Supplier as contextual Party roles rather than unrelated universal identities.
- Demonstrates business scheduling through Payment Run and Payroll Run while keeping generic scheduler/job semantics outside ABCS.
- Adds reusable Party, Identifier, Address, Monetary Amount, Quantity, Business Object Reference, and Approval Input schemas.
- Adds Capability Invocation, Response, and Discovery schemas.
- Introduces Discover, Describe, and Invoke semantics with HTTP only as an optional binding convention.
- Clarifies the hard business-only scope boundary and GREEN provenance policy.
- Adds explicit compatibility/versioning guidance.

## Draft 0.1

Initial public proof release establishing canonical capability identifiers, a capability schema, governance principles, and a small Procurement capability set.
