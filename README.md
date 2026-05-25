# Livepeer

> Decentralized video infrastructure and AI video on Ethereum + Arbitrum.

[Livepeer](https://livepeer.org) is the open, permissionless protocol for video transcoding, streaming, and AI video inference, coordinated on Ethereum mainnet and Arbitrum One via the **Livepeer Token (LPT)**. The company commercializes the network through **Livepeer Studio** — a managed REST API for live streaming, on-demand video, multistream, rooms, access control, recording, metrics, and AI generate — and the open **Livepeer AI Network**, where any GPU operator can serve text-to-image, image-to-video, live video-to-video, LLM, audio-to-text, text-to-speech, upscale, and segmentation pipelines for fees settled in ETH via probabilistic micropayments.

This repository is the API Evangelist catalog entry for Livepeer.

## APIs

This catalog covers three distinct API surfaces:

| API | Base URL | Auth | Operations |
|-----|----------|------|-----------:|
| **Livepeer Studio** | `https://livepeer.studio/api` | Bearer (API key) | 64 |
| **Livepeer AI Network** (community + Studio gateway) | `https://dream-gateway.livepeer.cloud` / `https://livepeer.studio/api/beta/generate` | Bearer (API key) | 13 |
| **Livepeer Node CLI HTTP** (go-livepeer local API) | `http://127.0.0.1:7935` | Loopback | 12 |

Total: **89 operations** across 4 OpenAPI specifications.

### Livepeer Studio surface (by tag)

- **stream** — 11 ops (create, retrieve, update, delete, terminate, start-pull, multistream targets, clip)
- **asset** — 6 ops (list, request-upload, upload-by-URL, retrieve, patch, delete)
- **webhook** — 8 ops (CRUD + logs + resend)
- **multistream** — 5 ops (target CRUD)
- **session** — 4 ops (list, retrieve, recorded sessions, clips)
- **room** — 9 ops (WebRTC rooms + users + egress)
- **transcode** — 1 op (file transcode)
- **playback** — 1 op (retrieve playback info)
- **accessControl** — 5 ops (signing key CRUD)
- **task** — 2 ops (list, retrieve)
- **metrics** — 5 ops (realtime + historical viewership, usage)
- **generate** — 7 ops (text-to-image, image-to-image, image-to-video, upscale, audio-to-text, segment-anything-2, llm)

### Livepeer AI Network surface

10 generation pipelines:

- `POST /text-to-image`
- `POST /image-to-image`
- `POST /image-to-video`
- `POST /upscale`
- `POST /audio-to-text`
- `POST /segment-anything-2`
- `POST /llm` (OpenAI chat-completion compatible)
- `POST /image-to-text`
- `POST /live-video-to-video`
- `POST /text-to-speech`

Plus runner introspection: `/health`, `/hardware/info`, `/hardware/stats`.

### Livepeer Node CLI HTTP

12 endpoints exposed by `go-livepeer` for operators: status, protocol parameters, registered orchestrators, bond / unbond / rebond, orchestrator activation, broadcaster config, max price per capability, reward, ETH/LPT transfers, message signing.

## Repository contents

| Folder | What lives there |
|---|---|
| [`apis.yml`](./apis.yml) | APIs.json 0.19 entry indexing every API and artifact |
| [`openapi/`](./openapi/) | OpenAPI 3.1 specs for Studio, AI Worker, AI Gateway, CLI |
| [`rules/`](./rules/) | Spectral rulesets enforcing Studio + AI conventions |
| [`capabilities/`](./capabilities/) | Naftiko capability YAMLs (one per business surface) |
| [`vocabulary/`](./vocabulary/) | Domain vocabulary covering protocol, Studio, AI, tokens |
| [`json-ld/`](./json-ld/) | JSON-LD context for Livepeer resources |
| [`json-schema/`](./json-schema/) | Stream, Asset, Task, Webhook, AI pipeline schemas |
| [`json-structure/`](./json-structure/) | Operational structures (platform, stream) |
| [`examples/`](./examples/) | Example request/response payloads |
| [`plans/`](./plans/) | API Commons 0.1 Plans (Sandbox / Growth / Enterprise) |
| [`rate-limits/`](./rate-limits/) | API Commons 0.1 Rate Limits |
| [`finops/`](./finops/) | FOCUS-aligned FinOps mapping |
| [`review.yml`](./review.yml) | API Evangelist apis.yml lint review |

## Why Livepeer matters

- **Tier-1 decentralized infrastructure provider**: The largest non-financial public good built on Ethereum that delivers measurable user-facing utility (video).
- **First production AI compute market**: Livepeer's AI Subnet is one of the only crypto networks where AI inference workloads, not speculation, drive on-chain fee revenue (~60–72% of fees per recent quarterly metrics).
- **Two posture options for the same workload**: Builders can start with the managed Studio API (familiar SaaS, fiat billing) and graduate to the open Gateway when they want to choose Orchestrators, pay in ETH, and operate trust-minimized.
- **Open governance**: LPT holders steer treasury spend, protocol parameters, and upgrades via LIPs.

## Naftiko capability surface

Every API surface is decomposed into shared per-domain Naftiko capabilities, each exposing:

- A **REST adapter** (one resource per consumed OpenAPI path)
- An **MCP adapter** (one tool per consumed operation)

These capabilities are designed to be composed into governed AI workflows (e.g., "ingest creator livestream → record session → transcode VOD → generate text-to-image thumbnail → push to multistream"). Authentication is bound to `LIVEPEER_API_KEY` via environment.

## Maintainer

[Kin Lane](https://apievangelist.com) — `kin@apievangelist.com`

---

_Generated and curated by API Evangelist. Last refreshed 2026-05-25._
