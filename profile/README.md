# BoringCache

> Universal build cache for CI, Docker, and local development.

**BoringCache speeds up builds by caching expensive parts—dependencies, toolchains, and build outputs—and reusing them across environments.**

If something was already built, installed, or downloaded, BoringCache helps you avoid doing it again.

## What it’s good at

- Speeding up CI pipelines
- Persisting Docker BuildKit caches
- Sharing caches between CI and developer machines
- Speeding up custom build steps

## How it works

1. You choose directories to cache
2. A content manifest is built
3. Identical content uploads once
4. Verified archives are restored where needed

The same cache works in CI, Docker, and local development.

## Repositories

- `cli` — Universal CLI
- `action` — GitHub Actions integration
- `nodejs`, `ruby`, `rust` — Language setup + caching
- `docker`, `buildkit` — Docker BuildKit cache reuse

## Learn more

- Docs: https://boringcache.com/docs
- Website: https://boringcache.com
