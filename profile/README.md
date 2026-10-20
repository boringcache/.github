# BoringCache

BoringCache provides shared build cache, retained artifacts, and a private OCI
registry for CI, Docker builds, coding agents, and local development. Use your
existing runners and build tools to reuse compatible build results across
machines and keep the outputs you need to distribute.

| Product | What it does |
|---|---|
| [Cache](https://boringcache.com/build-cache) | Reuses dependency downloads, compiler results, task outputs, and Docker layers. Cache data is reclaimable under the workspace's cache policy. |
| [Artifacts](https://boringcache.com/artifacts) | Keeps immutable build outputs for an explicit retention period. |
| [Registry](https://boringcache.com/registry) | Publishes private OCI images and other OCI content until deleted. |

## Install and connect a repository

```bash
curl -sSL https://install.boringcache.com/install.sh | sh
cd your-project
boringcache onboard
```

Onboarding connects a workspace and writes `.boringcache.toml`. Commit that plan
so local builds and CI use the same configuration. Keep pull requests and other
low-trust jobs restore-only; let trusted jobs publish cache updates.

[Installation guide](https://boringcache.com/docs/installation) ·
[Supported tools and setup](https://boringcache.com/docs/adapters) ·
[GitHub Actions guide](https://boringcache.com/docs/github-actions)

## Build results

The [benchmarks](https://boringcache.com/benchmarks) include measured workloads,
comparison conditions, and links to the public runs. The
[demo](https://boringcache.com/demo) shows recorded builds and workspace reports.

## Repositories

- [`cli`](https://github.com/boringcache/cli) — CLI downloads and installation
- [`one`](https://github.com/boringcache/one) — GitHub Action for cache and artifact transfers
- [`buildkit`](https://github.com/boringcache/buildkit) — signed managed BuildKit image
- [`benchmarks`](https://github.com/boringcache/benchmarks) — public benchmark index and checks
- [`ruby`](https://github.com/boringcache/ruby) — prebuilt Ruby distributions
- [`builder`](https://github.com/boringcache/builder) — application builds with Dagger, Rails, and Mise

[Documentation](https://boringcache.com/docs) ·
[Pricing](https://boringcache.com/pricing) ·
[Support](mailto:support@boringcache.com) ·
[Security](https://boringcache.com/security) ·
[boringcache.com](https://boringcache.com)
