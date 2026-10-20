# BoringCache Vision

BoringCache helps builds reuse work already completed on another machine.

Builds repeatedly install dependencies and recreate compiler outputs, tool
caches, and build artifacts across CI, Docker builds, and local development.
Compatible builds can reuse those results.

BoringCache provides reusable Cache, retained Artifacts, and a private OCI
Registry in one workspace. Builds continue to run on the customer's existing
CI runners and developer machines.

The product's goals are:

- reduce repeated downloads and compilation across compatible builds;
- share build data across CI and local development;
- give Cache, Artifacts, and Registry separate lifecycle rules;
- allow restore-only access for low-trust jobs and save access for trusted jobs;
- make cache decisions and transfer results inspectable.
