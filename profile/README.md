# BoringCache

BoringCache is a shared build cache for CI, Docker builds, and local development.

Builds should not repeat work that is already done. Keep your current runners and pipelines. Add one shared cache layer.

## Start here

```bash
curl -sSL https://install.boringcache.com/install.sh | sh
cd your-project
boringcache onboard
```

## Common paths

```bash
# Archive mode (run/save/restore)
boringcache run -- bundle install

# Docker adapter from repo config
boringcache docker
```

Archive mode commands (`run`, `save`, and `restore`) are for explicit directory
caches. Adapter commands are the normal path for supported remote-cache tools.

## GitHub Actions

Commit cache identity in `.boringcache.toml`:

```toml
workspace = "my-org/app"

[entries.bundler]
path = "vendor/bundle"
tag = "bundler-gems"

[profiles.bundle-install]
entries = ["bundler"]
```

Then keep the Action surface small:

```yaml
- uses: boringcache/one@6b7033721b37075b2138fd0c769bf088e0836ce6 # v1.14.0
  with:
    trust-policy: auto
    setup: none
    mode: archive
    cache-profiles: bundle-install
  env:
    BORINGCACHE_RESTORE_TOKEN: ${{ secrets.BORINGCACHE_RESTORE_TOKEN }}
    BORINGCACHE_SAVE_TOKEN: ${{ github.event_name != 'pull_request' && secrets.BORINGCACHE_SAVE_TOKEN || '' }}
```

Pull requests can stay restore-only. Trusted jobs publish updates.

## Repositories

- `cli` - CLI, repo config, onboard flow, adapter commands
- `one` - GitHub Action distribution
- `buildkit` - managed BuildKit image metadata
- `benchmarks` - public benchmark results and methodology
- `ruby` - prebuilt Ruby distributions

## Docs

- https://boringcache.com
- https://boringcache.com/docs
