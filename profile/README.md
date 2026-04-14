# BoringCache

BoringCache is a shared build cache for CI, Docker builds, and local development.

Start locally:

```bash
curl -sSL https://install.boringcache.com/install.sh | sh
cd your-project
boringcache onboard
```

That gives the repo a workspace, auth, and `.boringcache.toml` when the CLI can infer it.

Then use [`boringcache/one@v1`](https://github.com/boringcache/one) in GitHub Actions so local runs, Docker builds, and CI share the same repo config.

Use:

- `boringcache run` for archive caching
- adapter commands like `boringcache nx` or `boringcache docker` when the tool already supports remote cache
- `run --proxy` for unsupported or custom tools

Repos:

- [`cli`](https://github.com/boringcache/cli)
- [`one`](https://github.com/boringcache/one)
- [`web`](https://github.com/boringcache/web)
- [`action-core`](https://github.com/boringcache/action-core)
- [`benchmarks`](https://github.com/boringcache/benchmarks)
- [`ruby`](https://github.com/boringcache/ruby)

Links:

- [Docs](https://boringcache.com/docs)
- [Website](https://boringcache.com)
- [GitHub Actions Marketplace](https://github.com/marketplace/actions/boringcache)
