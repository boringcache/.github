# BoringCache

Hey 👋 We're BoringCache.

We believe builds shouldn't repeat work that's already done. So we made a cache that's delightfully boring — no daemons, no magic, no surprises. Just directories in, directories out.

**Cache once. Reuse everywhere.**

---

BoringCache is a **universal build artifact cache for CI, Docker, and local development**.
It stores and restores directories you choose so build outputs, dependencies, and tool caches can be reused across environments.

BoringCache **does not run builds** and is **not tied to any build tool**. It works with any language, framework, or workflow by caching directories explicitly selected by the user.

Caches are **content-addressed and verified before restore**. If identical content already exists, uploads are skipped. The same cache can be reused in GitHub Actions, Docker/BuildKit, and on developer machines using the same CLI.

---

## What problem does this solve?

Most CI caching systems:

- Re-upload identical content on every key change
- Can’t be reused across CI providers, Docker, and local machines
- Offer no reliable way to verify what’s being restored
- Store opaque blobs that are hard to inspect or reason about

BoringCache makes caching **explicit, predictable, and reusable**.

---

## Core ideas

- **Directory-based caching**  
  You decide exactly what directories to cache.

- **Content-addressed deduplication**  
  Upload once. If the content matches, uploads are skipped.

- **Verified restores**  
  Archives are always verified before extraction.

- **Platform-aware by default**  
  OS and architecture are included to keep binary caches safe.

- **One cache layer everywhere**  
  Same cache works in CI, Docker/BuildKit, and local development.

---

## Quick example

```bash
# Save a cache
boringcache save my-org/app "deps:node_modules"

# Save again (no re-upload if content matches)
boringcache save my-org/app "deps:node_modules"

# Restore the same cache anywhere
boringcache restore my-org/app "deps:node_modules"
Same commands. Same cache. Anywhere you build.
```

## GitHub Actions
The maintained GitHub Actions surface is `boringcache/one@v1`:

```yaml
- uses: boringcache/one@v1
  with:
    preset: node
    workspace: my-org/app
  env:
    BORINGCACHE_RESTORE_TOKEN: ${{ secrets.BORINGCACHE_RESTORE_TOKEN }}
    BORINGCACHE_SAVE_TOKEN: ${{ github.event_name == 'pull_request' && '' || secrets.BORINGCACHE_SAVE_TOKEN }}

```

`boringcache/one` handles CLI bootstrap, cache restore/save orchestration, and the common runtime presets. If you only need the CLI binary in a later step, use `setup: none`.

## CLI usage

The same CLI works in CI, Docker, and on developer machines:

```bash
boringcache save my-org/app "deps:node_modules,build:dist"
boringcache restore my-org/app "deps:node_modules,build:dist"
```
You can use the CLI directly or via `boringcache/one`.

## Repositories
### Maintained

- cli – BoringCache CLI (save/restore directories anywhere)
- one – Unified GitHub Actions surface for setup, restore/save, and proxy-backed modes
- action-core – Shared implementation package used by maintained actions

### Legacy compatibility repos

Older wrapper actions are being retired. New workflows should use `boringcache/one@v1`.

## Where it works
- GitHub Actions
- GitLab CI
- CircleCI
- Jenkins
- Buildkite
- Docker / BuildKit
- Dagger
- Local development

Any CI. Any build system. Just point at directories.

## What BoringCache is not
- ❌ Not a build system
- ❌ Not a workflow engine
- ❌ Not a compiler-specific cache

BoringCache only saves and restores directories you explicitly choose.

---

## Get Started

Accelerate your Docker image builds and GitHub Actions workflows. Easily integrate with your existing CI provider and dev workflows to save hours of build time.

**Free tier available. No credit card required.**

[**→ Get started free**](https://boringcache.com/signup) · [Read the docs](https://boringcache.com/docs) · [hello@boringcache.com](mailto:hello@boringcache.com)

---

## Documentation

- 📖 Docs: https://boringcache.com/docs
- 🌐 Website: https://boringcache.com
- 🛒 GitHub Actions Marketplace: https://github.com/marketplace/actions/boringcache

## License

MIT · Built by BoringTech Ltd.
