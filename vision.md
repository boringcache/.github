# BoringCache Vision

BoringCache exists because builds should not repeat work that is already done.

Modern builds keep recreating dependency installs, compiler outputs, tool caches, and build artifacts across CI, Docker builds, and local development even when that work already happened somewhere else.

BoringCache is a shared build cache for CI, Docker builds, and local development.

It does not replace CI. It does not replace Docker. It does not run builds somewhere else.

It keeps reusable build state available across the places builds already run.

The goal is simple:

- less repeated work
- one workspace across environments
- restore-only access for low-trust jobs and save access for trusted jobs
- explicit, verified reuse instead of opaque cache glue
