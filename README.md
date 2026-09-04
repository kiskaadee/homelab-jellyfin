# 🍿 Homelab Jellyfin (Media Server)

Hardware-accelerated media server and streaming platform for movies, television, and music.

---

## 🏗️ Architecture & Requirements

- **Proxy Network**: Attached to external `proxy-net`
- **Domain**: `jellyfin.roadtotech.me`
- **Authelia Protected**: Yes (ForwardAuth SSO)
- **Target Port**: `8096`
- **Media Path**: `/media` (read-only)

---

## ⚙️ Configuration & Metadata (`app.yaml`)

```yaml
name: "jellyfin"
aliases:
  - "media"
domain: "jellyfin.roadtotech.me"
description: "Media Server & Streaming Hub"
visible: true
auth: true
networks:
  - proxy-net
env:
  MEDIA_PATH: "/media"
homepage:
  title: "Jellyfin"
  group: "Media & Productivity"
  icon: "jellyfin.png"
  container: "jellyfin"
  weight: 10
```

---

## 🚀 Deployment

### Via Orchestrator (`appctl`)
```bash
appctl up jellyfin
# or using shortcut alias
appctl up media
```

### Manual Deployment
```bash
docker compose up -d
```

---

## 📄 License
This repository is released into the public domain under the [Unlicense](LICENSE).
