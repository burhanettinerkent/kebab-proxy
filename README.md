# Kebab Proxy

**Kebab Proxy** is a self-hosted, privacy-first AI gateway that exposes a unified local API for multiple AI providers and coding assistants.

It is built for developers, operators, and SaaS builders who want to run tools like **Claude Code**, **Codex/OpenAI-compatible clients**, **Gemini-based flows**, and other supported providers behind **one stable endpoint**, with **local control over credentials, routing, usage, and operational policy**.

## Why Kebab Proxy?

Modern AI workflows are fragmented.
Different tools expect different auth flows, different model APIs, and different operational assumptions. That gets messy fast.

Kebab Proxy solves that by acting as a **local orchestration layer** between your clients and upstream model providers.

With Kebab Proxy, you can:

- expose **one consistent endpoint** to your tools
- route requests across multiple upstream providers
- keep private credentials and auth files **on your own machine/server**
- manage local operations through a built-in **management dashboard**
- use the proxy as the backend layer for **Kebab-branded products and SaaS systems**

In short: **Kebab Proxy is the infrastructure layer that turns scattered AI access into one manageable system.**

---

## Core Value Proposition

Kebab Proxy is designed around four practical goals:

### 1. Unified Access
Run multiple providers and integrations behind a single local/API-compatible surface.

### 2. Operational Control
Control auth files, config, routing, model mapping, and usage from one place.

### 3. Privacy by Default
Keep secrets, OAuth files, and machine-specific credentials local.

### 4. Product Readiness
Use the proxy not only as a personal tool, but as a reusable backend layer for larger systems such as appointment assistants, internal tooling, and Kebab SaaS products.

---

## Features

### Multi-provider routing
Kebab Proxy can act as a unified request layer across supported upstream AI providers and auth-backed integrations.

### OpenAI-compatible endpoint surface
Many clients and tools expect OpenAI-style APIs. Kebab Proxy makes local integration easier by providing a compatible access layer where applicable.

### Built-in management dashboard
The included management UI helps you operate the system from the browser, including:

- auth file handling
- config inspection and editing
- operational visibility
- usage and system management

### Local-first credential handling
Instead of publishing sensitive values to a public repo or scattering them across tools, Kebab Proxy keeps operational auth material under your own control.

### Model mapping and provider control
You can use the proxy as a translation and routing layer between client expectations and upstream model availability.

### Self-hosted deployment model
Kebab Proxy is intended to run under your control on your own machine, workstation, server, or product infrastructure.

---

## Typical Use Cases

Kebab Proxy works especially well for scenarios like these:

### AI coding workflow hub
Use one endpoint for multiple coding assistants and development tools without manually reconfiguring each provider flow every time.

### Local AI operations layer
Run a private gateway on your machine or server to centralize provider access, auth files, quotas, and request routing.

### SaaS backend building block
Use Kebab Proxy as the infrastructure foundation for higher-level products that need stable AI connectivity, operational controls, and branded management.

### Team/internal tooling
Standardize how internal tools talk to upstream AI systems while keeping operational behavior centralized.

---

## Project Goal

The long-term goal of Kebab Proxy is simple:

> Build a secure, manageable, brandable proxy layer for real-world AI operations.

That means the project is not just about forwarding requests.
It is about making AI infrastructure:

- easier to operate
- safer to self-host
- easier to integrate into products
- more practical for day-to-day development workflows

---

## Security & Privacy

Kebab Proxy is intended to be used as a **self-hosted local/control-plane component**.

This public repository is sanitized and does **not** include private operational data.

### Not included in this public repo

- personal `config.yaml`
- real `auths/` contents
- OAuth account exports
- machine-specific secrets
- local binaries
- private credentials or tokens

### Recommended usage

- keep `config.yaml` private
- keep `auths/` private
- do not commit live credentials
- treat public GitHub as code-only, not secret storage

If you want to deploy the project, use the example configuration as a starting point and provide your own local values.

---

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

### 3. Create a local config

```bash
cp config.example.yaml config.yaml
```

Then edit `config.yaml` with your own local settings.

### 4. Start the server

```bash
go run ./cmd/server
```

### 5. Open the dashboard

After startup, open:

- `http://localhost:8317/management.html`

---

## Where Kebab Proxy Fits in the Stack

You can think of the system like this:

**Clients / Tools**
→ Claude Code, Codex-compatible clients, Gemini-oriented flows, custom apps

**Kebab Proxy**
→ routing, auth handling, config, management UI, operational control

**Upstream Providers**
→ the actual model providers and external AI services

That makes Kebab Proxy the **control layer** between usage and providers.

---

## Public Repository Notes

This repository is meant to present the project cleanly and safely in public.

That means:

- branding is public
- architecture and code are public
- private deployment details stay private

If you fork or reuse it, keep the same discipline: **ship code publicly, keep secrets local.**

---

## License

MIT
