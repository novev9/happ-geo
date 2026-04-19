# happ-geo

Personal mirror of pinned geo routing files for the [Happ](https://www.happ.su) iOS/macOS client.

## Why

The upstream geo files are served from a third-party repository with auto-updating release tags. Mirroring them here:

- Removes dependency on the upstream author and CDN staying alive.
- Guarantees that the files never change silently — they are pinned to specific git commits in this repo.
- Makes the routing profile shareable with a stable link.

## Files

| File | Size | Source snapshot |
|------|------|-----------------|
| `geosite.dat` | 66 KB | [hydraponique/roscomvpn-geosite@202604152235](https://github.com/hydraponique/roscomvpn-geosite/tree/202604152235) |
| `geoip.dat`   | 409 KB | [hydraponique/roscomvpn-geoip@202604190535](https://github.com/hydraponique/roscomvpn-geoip/tree/202604190535) |

SHA-256:

```
765b86e4b6aed5da1a206304b5500c7668687fa1df8e8322c8a4961e1b672190  geosite.dat
dfcc620ca91fa3d3f1dd945bf8d43381d8e74352bbfd967462a827a0b496bb06  geoip.dat
```

## Happ deeplink

Blacklist-style profile (everything routes through the VPN except Russian/Belarusian services and Apple/Microsoft/Steam/etc). DNS: Cloudflare (`1.1.1.1` over DoH) for both remote and domestic traffic.

Tap the link on your iPhone (or paste into Happ → Routing → Import from clipboard):

```
happ://routing/onadd/eyJOYW1lIjoiUm9zY29tVlBOLVBlcnNvbmFsIiwiR2xvYmFsUHJveHkiOiJ0cnVlIiwiVXNlQ2h1bmtGaWxlcyI6InRydWUiLCJSZW1vdGVEbnMiOiIxLjEuMS4xIiwiRG9tZXN0aWNEbnMiOiIxLjEuMS4xIiwiUmVtb3RlRE5TVHlwZSI6IkRvSCIsIlJlbW90ZUROU0RvbWFpbiI6Imh0dHBzOi8vMS4xLjEuMS9kbnMtcXVlcnkiLCJSZW1vdGVETlNJUCI6IjEuMS4xLjEiLCJEb21lc3RpY0ROU1R5cGUiOiJEb0giLCJEb21lc3RpY0ROU0RvbWFpbiI6Imh0dHBzOi8vMS4xLjEuMS9kbnMtcXVlcnkiLCJEb21lc3RpY0ROU0lQIjoiMS4xLjEuMSIsIkdlb2lwdXJsIjoiaHR0cHM6Ly9jZG4uanNkZWxpdnIubmV0L2doL25vdmV2OS9oYXBwLWdlb0BiYjk2YzE3M2ZhNzMxYjkxMDk3NDZlNGIyNWI3NTJkNzg0MzBlNmVjL2dlb2lwLmRhdCIsIkdlb3NpdGV1cmwiOiJodHRwczovL2Nkbi5qc2RlbGl2ci5uZXQvZ2gvbm92ZXY5L2hhcHAtZ2VvQGJiOTZjMTczZmE3MzFiOTEwOTc0NmU0YjI1Yjc1MmQ3ODQzMGU2ZWMvZ2Vvc2l0ZS5kYXQiLCJMYXN0VXBkYXRlZCI6IjE3NzY1NzkwMDAiLCJEbnNIb3N0cyI6eyJsa2ZsMi5uYWxvZy5ydSI6IjIxMy4yNC42NC4xNzUiLCJsa25wZC5uYWxvZy5ydSI6IjIxMy4yNC42NC4xODEifSwiUm91dGVPcmRlciI6ImJsb2NrLXByb3h5LWRpcmVjdCIsIkRpcmVjdFNpdGVzIjpbImdlb3NpdGU6cHJpdmF0ZSIsImdlb3NpdGU6Y2F0ZWdvcnktcnUiLCJnZW9zaXRlOndoaXRlbGlzdCIsImdlb3NpdGU6bWljcm9zb2Z0IiwiZ2Vvc2l0ZTphcHBsZSIsImdlb3NpdGU6ZXBpY2dhbWVzIiwiZ2Vvc2l0ZTpyaW90IiwiZ2Vvc2l0ZTplc2NhcGVmcm9tdGFya292IiwiZ2Vvc2l0ZTpzdGVhbSIsImdlb3NpdGU6dHdpdGNoIiwiZ2Vvc2l0ZTpwaW50ZXJlc3QiLCJnZW9zaXRlOmZhY2VpdCJdLCJEaXJlY3RJcCI6WyJnZW9pcDpwcml2YXRlIiwiZ2VvaXA6ZGlyZWN0Il0sIlByb3h5U2l0ZXMiOlsiZ2Vvc2l0ZTpnb29nbGUtcGxheSIsImdlb3NpdGU6Z2l0aHViIiwiZ2Vvc2l0ZTp0d2l0Y2gtYWRzIiwiZ2Vvc2l0ZTp5b3V0dWJlIiwiZ2Vvc2l0ZTp0ZWxlZ3JhbSJdLCJQcm94eUlwIjpbXSwiQmxvY2tTaXRlcyI6WyJnZW9zaXRlOndpbi1zcHkiLCJnZW9zaXRlOnRvcnJlbnQiLCJnZW9zaXRlOmNhdGVnb3J5LWFkcyJdLCJCbG9ja0lwIjpbXSwiRG9tYWluU3RyYXRlZ3kiOiJJUElmTm9uTWF0Y2giLCJGYWtlRE5TIjoiZmFsc2UifQ==
```

Geo file URLs embedded in the deeplink (pinned by commit SHA, immutable):

```
https://cdn.jsdelivr.net/gh/novev9/happ-geo@bb96c173fa731b9109746e4b25b752d78430e6ec/geosite.dat
https://cdn.jsdelivr.net/gh/novev9/happ-geo@bb96c173fa731b9109746e4b25b752d78430e6ec/geoip.dat
```

## What you still need

A Happ-compatible VPN subscription (Xray/VLESS/etc). This repository only provides the routing rules — it does not include a VPN server. Get one from any Happ-compatible provider and import its subscription separately.

## Credits

- `geosite.dat` — originally compiled by the V2Ray / [v2fly/domain-list-community](https://github.com/v2fly/domain-list-community) project, adapted for RF blocklist context by [hydraponique/roscomvpn-geosite](https://github.com/hydraponique/roscomvpn-geosite).
- `geoip.dat` — aggregated IP ranges mirrored from [hydraponique/roscomvpn-geoip](https://github.com/hydraponique/roscomvpn-geoip).
- Happ client: [happ.su](https://www.happ.su), [@Happ-proxy on GitHub](https://github.com/Happ-proxy).

## License

MIT — see [LICENSE](./LICENSE). Copyright (c) 2018-2019 V2Ray (preserved from the upstream geosite project).
