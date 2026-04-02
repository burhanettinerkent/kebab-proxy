# Kebab AI Proxy Management Center

Kebab Proxy is a self-hosted, privacy-first AI gateway built for routing and managing multiple coding/model providers behind a single local endpoint.

It is designed for teams and solo builders who want one stable OpenAI-compatible entry point for tools like Claude Code, Codex, Gemini, and similar AI clients—without exposing private local credentials or publishing personal configuration.

## Project Purpose

The goal of this project is to provide a **secure, practical, and brandable AI proxy layer** that can:

- unify multiple providers behind one endpoint
- simplify local credential and account orchestration
- provide a built-in management panel for operations
- support self-hosted deployments with no external telemetry
- serve as infrastructure for larger products such as Kebab SaaS tools

In short: **Kebab Proxy is the operational gateway layer for Kebab-branded AI products.**

## Core Features

- **Multi-Provider Routing:** Route requests across Anthropic (Claude), OpenAI/Codex, Gemini, and other supported providers.
- **OpenAI-Compatible Endpoint:** Use a single local API surface for compatible tools and integrations.
- **Built-in Management UI:** Manage auth files, config, usage, and operational settings from the browser.
- **Security-First Design:** Credentials, tokens, auth files, and logs stay local unless you explicitly export them.
- **Model Mapping & Control:** Redirect, normalize, and control upstream model behavior from one place.
- **Self-Hosted by Default:** No required third-party telemetry, analytics, or cloud control plane.

## Security & Privacy

This public repository is intentionally sanitized.

The following are **not** included in the repo:

- personal `config.yaml`
- local `auths/` contents
- private tokens / OAuth account data
- local binaries and machine-specific secrets

If you deploy this project yourself, create your own local config from the example file and keep secrets private.

## Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/burhanettinerkent/kebab-proxy.git
cd kebab-proxy
```

### 2. Install dependencies

```bash
go mod tidy
```

### 3. Create your local config

```bash
cp config.example.yaml config.yaml
```

Then edit `config.yaml` with your own local settings and credentials.

### 4. Run the server

```bash
go run ./cmd/server
```

## Accessing the Dashboard

After startup, open:

- `http://localhost:8317/management.html`

## Typical Use Cases

- Running multiple AI coding tools behind one local endpoint
- Managing OAuth/API-backed accounts without exposing secrets publicly
- Operating a branded AI proxy layer for internal tools or SaaS products
- Standardizing local AI infrastructure across projects

## Notes

- Keep `config.yaml` private.
- Keep `auths/` private.
- Do not commit personal machine credentials to GitHub.
- Use `config.example.yaml` as the public-safe starting point.

## License

MIT
