# BoringCache Vision

BoringCache exists because builds should not repeat work that is already done.

Modern builds keep recreating dependency installs, compiler outputs, tool caches, and build artifacts across CI, Docker builds, and local development even when that work already happened somewhere else.

BoringCache is build data that follows your compute: reusable Cache, durable
Artifacts, and a private OCI Registry in one workspace.

It does not replace CI. It does not replace Docker. It does not run builds somewhere else.

It keeps reusable build state, retained outputs, and deployable images available
across the places builds already run.

The goal is simple:

- less repeated work
- one workspace across environments
- separate lifecycle rules for Cache, Artifacts, and Registry
- restore-only access for low-trust jobs and save access for trusted jobs
- explicit, verified reuse instead of opaque cache glue
