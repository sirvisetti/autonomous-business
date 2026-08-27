# ABCS machine-readable formats

ABCS uses one logical information model with multiple representations rather than maintaining independent YAML and JSON specifications.

## Policy

- **YAML 1.2** is the maintained authoring representation for modular domain catalogs, Business Object descriptors, and Capability descriptors.
- YAML documents are restricted to the JSON-compatible data model so they can round-trip cleanly to JSON.
- **JSON** is the preferred machine-exchange representation and is used for generated aggregate catalogs, examples, invocation envelopes, and other machine-facing artifacts.
- **JSON Schema 2020-12** is the normative validation language for canonical ABCS payloads and ABCS definition structures.
- A generated JSON representation must be semantically equivalent to its YAML source. Any mismatch is a publication defect.

This approach follows common machine-readable specification practice: a specification document can be modeled as a JSON object while being represented in JSON or YAML. ABCS keeps one maintained source to prevent representation drift.

## Publication

Draft 0.2 publishes an aggregate business catalog as both:

- `catalog/abcs-0.2.yaml`
- `catalog/abcs-0.2.json`

Modular source definitions remain under `domains/`, while validation schemas remain under `schemas/`.
