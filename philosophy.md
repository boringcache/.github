# BoringCache – Philosophy

## Cache parts, not systems

BoringCache caches directories, not build graphs or workflows.
Users explicitly choose what to cache.

If something requires guessing user intent, it does not belong.

## Portability over cleverness

A cache is only valuable if it can be reused.
Portability across CI, Docker, and local environments is more important than optimizing for one platform.

Defaults must be safe.
Advanced behavior must be opt-in.

## Determinism over heuristics

Reuse is driven by content fingerprints and manifests.
If content matches, reuse is safe.
If it does not, rebuild.

No heuristics.
No hidden invalidation rules.

## Boring by design

Avoid:
- background daemons
- opaque formats
- magic behavior
- platform lock-in

BoringCache should be easy to reason about and easy to replace.

## Security is baseline

Integrity verification is always on.
Encryption is opt-in.
Workspace scoping prevents cache poisoning.
