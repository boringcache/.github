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

# Adapter command from repo config
boringcache nx

# One-off adapter command
boringcache docker --tag docker-cache -- docker buildx build .

# Long-lived local proxy
boringcache cache-registry my-org/app registry-cache --port 5000
```

Archive mode commands (`run`, `save`, and `restore`) are for explicit directory caches. Adapter commands are for supported remote-cache tools. Use `cache-registry` when the repo already has a checked-in local endpoint setup or another process should keep the proxy alive.

## GitHub Actions

```yaml
- uses: boringcache/one@v1
  with:
    workspace: my-org/app
    cache-profiles: bundle-install
  env:
    BORINGCACHE_RESTORE_TOKEN: ${{ secrets.BORINGCACHE_RESTORE_TOKEN }}
    BORINGCACHE_SAVE_TOKEN: ${{ secrets.BORINGCACHE_SAVE_TOKEN }}
```

Pull requests can stay restore-only. Trusted jobs publish updates.

## Repositories

- `cli` - CLI, repo config, onboard flow, adapter commands
- `web` - app, docs, billing, workspaces, tokens
- `one` - main GitHub Action
- `action-core` - shared action helpers
- `ruby` - prebuilt Ruby distributions

## Docs

- https://boringcache.com
- https://boringcache.com/docs
