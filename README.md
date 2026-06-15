# Livepeer (livepeer-com)

Livepeer is the open, permissionless protocol for video transcoding, streaming, and AI video inference, coordinated on Ethereum mainnet and Arbitrum One via the Livepeer Token (LPT). The company commercializes the network through Livepeer Studio (a managed REST API for live streaming, VOD, multistream, recording, rooms, access control, and AI generate) and the Livepeer AI Network, where any GPU operator can serve text-to-image, image-to-video, live video-to-video, LLM, audio-to-text, text-to-speech, upscale, and segmentation pipelines for fees settled in ETH via probabilistic micropayments. The reference Go implementation (go-livepeer), official SDKs in TypeScript, Python, and Go, the React UI Kit, the AI worker, and the Gateway are all open source under the Livepeer GitHub organization.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/livepeer-com/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/livepeer-com/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- Video
- Live Streaming
- Video On Demand
- AI Video
- Decentralized Compute
- GPU Network
- Ethereum
- Arbitrum
- Web3

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Livepeer Studio API

Managed REST API for the Livepeer network. Create and run live streams via RTMP/SRT/WHIP, ingest VOD assets, run transcode tasks, configure multistream destinations, drive WebRTC rooms, manage signing keys for token-gated playback, query usage and viewership metrics, and submit AI generate jobs to the network — all behind a single Bearer-authenticated API on https://livepeer.studio/api.

- **Human URL:** [https://livepeer.studio](https://livepeer.studio)
- **Base URL:** `https://livepeer.studio/api`

#### Tags

- Live Streaming
- Video On Demand
- Transcoding
- Multistream
- Recording
- Rooms
- Webhooks
- Access Control
- Playback
- Metrics
- AI Generate
- Assets
- Tasks

#### Properties

- [Documentation](https://docs.livepeer.org)
- [API Reference](https://docs.livepeer.org/api-reference)
- [Getting Started](https://docs.livepeer.org/quickstart)
- [Authentication](https://docs.livepeer.org/developers/authentication)
- [OpenAPI](openapi/livepeer-studio-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/livepeer-studio.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/livepeer-studio.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Spectral Ruleset](rules/livepeer-studio-rules.yml)
- [JSON Schema](json-schema/livepeer-stream-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/livepeer-asset-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/livepeer-task-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/livepeer-webhook-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Structure](json-structure/livepeer-stream-structure.json)
- [Example](examples/livepeer-create-stream-example.json)
- [Example](examples/livepeer-create-webhook-example.json)

### Livepeer AI Network

Open AI inference gateway exposing text-to-image, image-to-image, image-to-video, live video-to-video, upscale, audio-to-text, text-to-speech, LLM (OpenAI-compatible), image-to-text, and Segment Anything 2 pipelines against a permissionless network of GPU Orchestrators. Two interchangeable endpoints: the community gateway at https://dream-gateway.livepeer.cloud and Livepeer Studio's managed gateway at https://livepeer.studio/api/beta/generate. Fees settle in ETH on Arbitrum One via probabilistic micropayment tickets.

- **Human URL:** [https://docs.livepeer.org/ai](https://docs.livepeer.org/ai)
- **Base URL:** `https://dream-gateway.livepeer.cloud`

#### Tags

- AI Inference
- Generative AI
- Text To Image
- Image To Image
- Image To Video
- Live Video To Video
- Upscale
- Audio To Text
- Text To Speech
- LLM
- Image To Text
- Segmentation
- GPU Network

#### Properties

- [Documentation](https://docs.livepeer.org/ai)
- [API Reference](https://docs.livepeer.org/ai/api-reference)
- [OpenAPI](openapi/livepeer-ai-worker-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/livepeer-ai-worker.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/livepeer-ai-worker.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [OpenAPI](openapi/livepeer-gateway-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/livepeer-gateway.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/livepeer-gateway.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Spectral Ruleset](rules/livepeer-ai-rules.yml)
- [JSON Schema](json-schema/livepeer-ai-text-to-image-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/livepeer-ai-image-to-video-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/livepeer-ai-text-to-image-example.json)
- [Example](examples/livepeer-image-to-video-example.json)

### Livepeer Node CLI HTTP API

Local loopback HTTP API exposed by go-livepeer for Orchestrator and Gateway operators. Endpoints cover node status, protocol parameters, registered orchestrators, bond/unbond/rebond actions, orchestrator activation, broadcaster configuration, max price for capability, reward calls, ETH/LPT transfers, and message signing — used by the official Livepeer CLI and dashboards.

- **Human URL:** [https://docs.livepeer.org/orchestrators](https://docs.livepeer.org/orchestrators)
- **Base URL:** `http://127.0.0.1:7935`

#### Tags

- Node Operations
- Orchestrator
- Gateway
- Staking
- Ethereum
- CLI

#### Properties

- [Documentation](https://docs.livepeer.org/orchestrators/guides/install-go-livepeer)
- [API Reference](https://docs.livepeer.org/references/livepeer-cli)
- [OpenAPI](openapi/livepeer-cli-http-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/livepeer-cli-http.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/livepeer-cli-http.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Spectral Ruleset](rules/livepeer-studio-rules.yml)

## Common Properties

- [Arazzo Workflows](arazzo/) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [Website](https://livepeer.org)
- [Studio Portal](https://livepeer.studio)
- [Documentation](https://docs.livepeer.org)
- [API Reference](https://docs.livepeer.org/api-reference)
- [Pricing](https://livepeer.studio/pricing)
- [Blog](https://livepeer.org/blog)
- [Changelog](https://docs.livepeer.org/changelog)
- [Explorer](https://explorer.livepeer.org)
- [Forum](https://forum.livepeer.org)
- [Roadmap](https://roadmap.livepeer.org/roadmap)
- [Status Page](https://status.livepeer.studio)
- [Sign Up](https://livepeer.studio/register)
- [Login](https://livepeer.studio/login)
- [Terms of Service](https://www.livepeer.org/legal/terms-of-service)
- [Privacy Policy](https://www.livepeer.org/legal/privacy-policy)
- [GitHub Organization](https://github.com/livepeer)
- [GitHub Repository](https://github.com/livepeer/go-livepeer)
- [GitHub Repository](https://github.com/livepeer/studio)
- [GitHub Repository](https://github.com/livepeer/docs)
- [S D Ks](https://docs.livepeer.org/sdks)
- [Type Script S D K](https://github.com/livepeer/livepeer-js)
- [Python S D K](https://github.com/livepeer/livepeer-python)
- [Python S D K](https://github.com/livepeer/livepeer-ai-python)
- [Python S D K](https://github.com/livepeer/livepeer-python-gateway)
- [Go S D K](https://github.com/livepeer/livepeer-go)
- [U I Kit](https://github.com/livepeer/ui-kit)
- [Reference Implementation](https://github.com/livepeer/go-livepeer)
- [A I Worker](https://github.com/livepeer/ai-worker)
- [Plugin](https://github.com/livepeer/naap)
- [Smart Contracts](https://github.com/livepeer/protocol)
- [Network Explorer](https://explorer.livepeer.org)
- [Token Contract Ethereum](https://etherscan.io/token/0x58b6a8a3302369daec383334672404ee733ab239)
- [Token Contract Arbitrum](https://arbiscan.io/token/0x289ba1701c2f088cf0faf8b3705246331cb8a839)
- [Discord](https://discord.gg/livepeer)
- [Twitter](https://twitter.com/Livepeer)
- [YouTube](https://www.youtube.com/@LivepeerNetwork)
- [LinkedIn](https://www.linkedin.com/company/livepeer)
- [L L Ms Txt](https://docs.livepeer.org/llms.txt)
- [L L Ms Full Txt](https://docs.livepeer.org/llms-full.txt)
- [Spectral Ruleset](rules/livepeer-studio-rules.yml)
- [Spectral Ruleset](rules/livepeer-ai-rules.yml)
- [Vocabulary](vocabulary/livepeer-com-vocabulary.yml)
- [J S O N- L D](json-ld/livepeer-com-context.jsonld)
- [JSON Structure](json-structure/livepeer-platform-structure.json)
- [Plans](plans/livepeer-com-plans-pricing.yml)
- [Rate Limits](rate-limits/livepeer-com-rate-limits.yml)
- [Fin Ops](finops/livepeer-com-finops.yml)
- [Features](undefined)
- [Use Cases](undefined)
- [Integrations](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
