# Publishing ABS and ABCS

The Autonomous Business Standard (ABS) project uses GitHub as the source of truth and Netlify for continuous production deployment. Its normative specification is the Autonomous Business Capability Specification (ABCS).

## Production flow

1. Requested standard/specification changes are applied to `sirvisetti/autonomous-business-standard`.
2. Production-ready changes are committed to `main`.
3. Netlify automatically deploys `main`.
4. The production standards site is published at `https://abs.sirvisetti.com`.

## Reference implementation

The non-normative reference implementation is maintained separately in `sirvisetti/autonomous-business-reference` and deployed from its own Netlify project. The reference may depend on published ABCS definitions; the standard repository must not depend on reference implementation code.

## Chat-driven updates

When Sirvisetti requests an ABS/ABCS update through ChatGPT and the connected GitHub and Netlify integrations are available, ChatGPT may apply requested production-ready changes directly to `main` and verify the resulting Netlify deployment.

For substantial semantic changes to the specification, compatibility rules, governance, licensing, or versioned schemas, use a review branch or pull request unless Sirvisetti explicitly requests immediate publication.

## Source of truth

The standards repository is authoritative for ABS/ABCS. Generated site files, schemas, examples, and domain definitions should remain synchronized in the same commit whenever a change affects more than one representation.
