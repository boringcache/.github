# BoringCache Philosophy

## Cache repeated work, not workflows

BoringCache keeps reusable build state available where builds already happen.

It supports two paths:
- explicit directory caching when archive mode is enough
- native remote-cache and proxy flows when the tool already supports them

The product should stay explicit. Users choose the workspace, entries, tags, or adapter defaults.

## Keep the build where it already runs

BoringCache is not a build system, a workflow engine, a CI provider, or a remote builder.

Keep the current runners, Dockerfiles, and developer machines. Add one shared cache layer.

## Determinism over heuristics

Reuse follows content fingerprints, manifests, and verified restores.

If content matches, reuse it.
If it does not, rebuild.

No hidden invalidation rules.
No guesswork about what changed.

## Trust boundaries matter

Restore and save access are separate on purpose.

Pull requests and other low-trust jobs can stay restore-only. Trusted jobs publish updates. Workspaces define the cache boundary.

## Boring by design

Avoid background daemons, invented platform language, opaque behavior, and hard lock-in.

BoringCache should stay easy to reason about, easy to inspect, and easy to remove.
