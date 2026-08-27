# Publishing ABCS

ABCS uses GitHub as the source of truth and Netlify for continuous production deployment.

## Production flow

1. Requested ABCS changes are applied to `sirvisetti/autonomous-business`.
2. Production-ready changes are committed to `main`.
3. Netlify automatically deploys `main`.
4. The production site is published at `https://abcs.sirvisetti.com`.

## Chat-driven updates

When Sirvisetti requests an ABCS update through ChatGPT and the connected GitHub and Netlify integrations are available, ChatGPT may apply the requested production-ready change directly to `main` and verify the resulting Netlify deployment.

For substantial semantic changes to the specification, compatibility rules, governance, licensing, or versioned schemas, use a review branch or pull request unless Sirvisetti explicitly requests immediate publication.

## Source of truth

The repository is authoritative. Generated site files, schemas, examples, and domain definitions should remain synchronized in the same commit whenever a change affects more than one representation.
