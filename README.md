# 🍿 Homelab Jellyfin

Self-hosted media streaming system for movies, TV series, music, and home recordings.

Part of the [homelab-core](https://github.com/kiskaadee/homelab-core) cluster ecosystem.

---

## 🏗️ Architecture & Storage

- **Container Image**: `jellyfin/jellyfin:latest`
- **Proxy**: Traefik (with rate limiting middleware attached to `proxy-net`)
- **Media Path**: `/media` (read-only bind mount)
- **Runtime Data**: `./config` and `./cache` (runtime app state, gitignored)

---

## ⚙️ Environment Variables

| Variable | Description | Default / Example |
| :--- | :--- | :--- |
| `JELLYFIN_DOMAIN` | Streaming Web UI FQDN | `jellyfin.arch-services.mywire.org` |
| `MEDIA_PATH` | Host path to media libraries | `/media` |
| `PUID` / `PGID` | User and Group execution IDs | `1000:1000` |

---

## 🚀 Deployment

### Via Orchestrator (`appctl`)
```bash
appctl up homelab-jellyfin
```

### Manual Deployment
```bash
docker compose up -d
```
