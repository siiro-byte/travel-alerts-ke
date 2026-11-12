# Pippit Bridge — Travel Alerts.ke Integration

**Status:** Integration documented; runtime not yet installed or connected.

## Purpose

Pippit Bridge is an open-source adapter for using a Pippit account to generate images and videos through supported agent interfaces. Travel Alerts.ke records this integration so it can be deployed and evaluated without mixing media-generation code into the editorial research system.

- Upstream project: https://github.com/superche/pippit-bridge
- Upstream documentation: https://github.com/superche/pippit-bridge/blob/main/README.md
- Integration guide: https://github.com/superche/pippit-bridge/blob/main/docs/integrations.md

## What it supports

- Text-to-image and reference-image generation.
- Text-to-video and video generation using reference media, including first/last frames.
- Asynchronous video-job polling and supported video-segment regeneration.
- MCP, Codex plugin, OpenCode plugin and a ChatGPT developer-mode App integration.

## Important limitations

Pippit Bridge is **not** a complete video-production suite. Its documented scope is image and video generation. It does not provide general-purpose script writing, AI presenter generation, speech/voice generation, transcription or a full timeline editor. Those stages require separate tools.

Generated scenes must be labelled and treated as illustrative. Do not present AI-generated airport, airline or incident footage as documentary evidence of a real event.

## Recommended Travel Alerts.ke workflow

1. Research and verify the alert using the Travel Alerts.ke master guide and research entry point in the Chatgpt.-Md repository.
2. Finalise the factual script, source attribution and traveller action before generating media.
3. Use Pippit Bridge for supporting images or video scenes only where they add value.
4. Complete presenter, voiceover, subtitles, source line, branding and final edit in a separate production tool.
5. Review every factual statement and visual for accuracy before publication.

## Installation routes

Choose one supported route in the upstream documentation:

- **Codex plugin:** install the public pippit-bridge marketplace and its pippit-video plugin. Requires a supported Node.js version (22.22.2+, 24.15.0+, or 26+) with npm/npx.
- **Generic MCP:** run the upstream stdio MCP server on a trusted computer with Node.js.
- **ChatGPT App:** deploy the upstream ChatGPT App server, expose it through a trusted HTTPS tunnel, then register its /mcp endpoint in ChatGPT developer mode. The upstream local app defaults to loopback and is not a public hosted service.

See the upstream README and integration guide for current commands and compatibility requirements. Do not copy commands from this document without checking the upstream version.

## Account and security requirements

- A Pippit account and Pippit access key are required for generation.
- Add the access key only through the upstream short-lived local enrollment flow. Never paste it into ChatGPT conversation text, GitHub files, source code, ordinary tool arguments or public configuration.
- Do not commit .env files, API keys, access keys, tokens, generated private media or credentials to this repository.
- Generation may incur charges under the connected Pippit account. Check the model, credit cost and account balance before each paid test.
- The upstream ChatGPT App currently documents a no-auth, single-user/controlled-tunnel development boundary. Do not expose it as a public multi-user service. Production multi-user use requires a properly implemented OAuth 2.1 and per-user credential-isolation layer.

## Deployment state and next step

This repository contains this integration record only. It does not vendor, fork, install or execute the upstream Pippit Bridge source, and it does not create a server, tunnel, ChatGPT App registration or Pippit credential.

Before runtime installation, confirm access to a trusted computer or server with the required Node.js/npm environment. An Android phone alone is not the documented default host for the local stdio/Codex installation. Do not purchase hosting or upgrade a plan solely on the basis of this documentation.
