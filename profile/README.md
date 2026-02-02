# BoringCache

**Cache once. Reuse everywhere.**

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
BoringCache provides a drop-in replacement for actions/cache:

```yaml
- uses: boringcache/action@v1
  with:
    workspace: my-org/app
    entries: deps:node_modules,build:dist
  env:
    BORINGCACHE_API_TOKEN: ${{ secrets.BORINGCACHE_API_TOKEN }}

```

Caches are restored at job start and saved at job end, with content-addressed deduplication and verified restores.

## CLI usage

The same CLI works in CI, Docker, and on developer machines:

```bash
boringcache save my-org/app "deps:node_modules,build:dist"
boringcache restore my-org/app "deps:node_modules,build:dist"
```
You can use the CLI directly or via GitHub Actions wrappers.

## Repositories
### Core

- cli – BoringCache CLI (save/restore directories anywhere)
- action – GitHub Actions cache (drop-in for actions/cache)
- save / restore – Explicit save and restore actions
- setup-boringcache – Install the CLI in GitHub Actions

### Language & tooling actions

- nodejs-action – Node.js toolchain + dependency caching
- ruby-action – Ruby toolchain + bundle caching
- rust-action – Rust toolchain + Cargo caching
- docker-action – Docker / BuildKit cache integration
- buildkit-action – BuildKit daemon with shared caching

All actions use the same cache format and underlying CLI.

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

## Documentation

- 📖 Docs: https://boringcache.com/docs
- 🌐 Website: https://boringcache.com

🧠 GitHub Actions Marketplace: https://github.com/marketplace/actions/boringcache

## License

MIT

Built by BoringTech Ltd.
