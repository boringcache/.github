# BoringCache Philosophy

## Share build data across existing workflows

BoringCache keeps reusable build state, retained build outputs, and deployable
images available where builds already happen.

It supports two paths:

- explicit directory caching when archive mode is enough;
- native remote-cache and proxy flows when the tool supports them.

Cache, Artifacts, and Registry have distinct lifecycle rules within a workspace.
Customers choose which data can be reclaimed, which outputs need retention,
and which images remain available until deletion.

## Keep builds on existing compute

Customers keep their runners, Dockerfiles, and developer machines. BoringCache
stores and transfers build data used by those builds.

## Make reuse decisions inspectable

Directory caching uses the repository plan and content fingerprints. Native
adapters use the build tool's cache identities and compatibility rules. A cache
miss allows the build tool to produce the result; a matching entry can be reused.

Reports and diagnostics should identify cache hits, misses, and transfer errors
so customers can understand what happened in a build.

## Separate read and write access

Pull requests and other low-trust jobs can stay restore-only. Trusted jobs
publish updates. Workspaces define the cache boundary.

## Keep setup and removal understandable

Document configuration files, credentials, local processes, and stored data.
Use the build tool's existing interfaces where possible, and explain how to
inspect or remove the integration.
