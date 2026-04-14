# BoringCache Philosophy

BoringCache is a shared build cache. The job is to reuse build state across CI, Docker builds, and local development without hiding how it works.

## Cache parts, not systems

BoringCache caches directories and native remote-cache flows. It does not model the whole build system for the user.

If something depends on guessing intent, it does not belong in the default path.

## Portability over cleverness

A cache is only useful if it can be reused where builds actually run.

That means:

- CI
- Docker builds
- local development

Defaults should stay safe. Advanced behavior should stay explicit.

## Determinism over heuristics

Reuse should come from content, manifests, and explicit cache boundaries.

If content matches, reuse is safe.
If it does not, rebuild.

No hidden invalidation rules.
No guesswork.

## Boring by design

Avoid:

- background daemons
- opaque formats
- platform lock-in
- magic behavior

The system should be easy to reason about and easy to replace.

## Trust is part of the product

Verified restores, workspace scoping, and clear read/write boundaries are part of making shared cache usable in practice.
