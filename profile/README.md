# BoringCache

**Stop rebuilding. Start reusing.**

BoringCache keeps the work your last build finished available across CI,
Docker builds, and local development. Keep your current runners, pipelines,
and tools. Add one shared build cache.

[Install the CLI](https://boringcache.com/docs/installation) ·
[Watch the demo](https://boringcache.com/demo) ·
[View benchmarks](https://boringcache.com/benchmarks) ·
[See pricing](https://boringcache.com/pricing)

## Start in your repo

```bash
curl -sSL https://install.boringcache.com/install.sh | sh
cd your-project
boringcache onboard
```

Onboard connects the workspace and writes `.boringcache.toml`. Commit that
plan so local builds and trusted CI share the same cache decisions.

Then use the shortest command for the tool:

```bash
# Docker command from the repo plan
boringcache docker

# Explicit dependency or build directory
boringcache run -- bundle install

# Native Xcode compilation cache
boringcache xcode -- xcodebuild -workspace App.xcworkspace -scheme App build
```

## One product, native cache paths

- Docker BuildKit layers, persistent cache mounts, and compiler cache
- Bazel, Gradle, Maven, Nx, Turborepo, Go, Cargo, ccache, sccache, Xcode, and Nix
- Explicit directory cache through `run`, `save`, and `restore`
- Restore-only access for pull requests; publication from trusted jobs
- Cache sessions, hits, misses, storage, and token access you can inspect

## Results you can open

- [2.8× faster in a Mastodon Docker run with every instruction rerun](https://github.com/boringcache/mastodon/actions/runs/31704136355)
- [2.5× faster in the measured PostHog Docker build](https://github.com/boringcache/benchmark-posthog/actions/runs/31569900357)
- [36% less runner time across 12 Immich base-image rebuilds](https://github.com/boringcache/base-images/actions/runs/31700820652)
- [1,333 Cargo compiler-cache hits on Deno](https://github.com/boringcache/benchmark-deno/actions/runs/31538912668)

Results vary by workload. The [benchmark page](https://boringcache.com/benchmarks)
keeps the measured values beside the exact public runs.

## Repositories

- [`cli`](https://github.com/boringcache/cli) — CLI, onboard flow, repo plan, and tool adapters
- [`one`](https://github.com/boringcache/one) — GitHub Action for the same repo plan
- [`buildkit`](https://github.com/boringcache/buildkit) — signed managed BuildKit image
- [`benchmarks`](https://github.com/boringcache/benchmarks) — public benchmark index and checks
- [`ruby`](https://github.com/boringcache/ruby) — prebuilt Ruby distributions

[Read the docs](https://boringcache.com/docs) ·
[Visit boringcache.com](https://boringcache.com)
