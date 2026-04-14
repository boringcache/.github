# BoringCache Vision

Builds should not repeat work that is already done.

Across CI, Docker builds, and local development, teams keep reinstalling dependencies, rebuilding outputs, and recreating tool state that already exists somewhere else.

BoringCache is a shared build cache for that problem.

It is not:

- a build system
- a CI provider
- a workflow engine
- a remote builder

It keeps reusable build state available where builds already happen.

The bar for the product is straightforward:

- clear category
- explicit behavior
- grounded claims
- useful reuse across environments
