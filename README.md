# AgentFoundry Workspace

An experimental JavaScript developer workspace with a React/Vite frontend, Node/Express services, code-analysis helpers and an Electron wrapper. Repository slug: `AgentFoundry-instantly`; older app/package labels include Copilot Pro and ChatGPT 2.0.

**Stage: alpha.** It is an application workspace, not a Linux distribution. Electron packaging configuration is present; working installers for every platform have not been qualified. This is an independently maintained project, not an official GitHub Copilot or ChatGPT product.

## Current scope

- Editor and developer-workspace UI under `src/`.
- Local code-analysis and assistance services under `server/ai-engine/`.
- Express HTTP/Socket.IO services in `server/index.js`.
- Guarded public-web fetching and document-analysis helpers in `server/chat-tools.js`.
- Electron entry points in `electron.js` and `preload.js`.
- Additional older experiments in separate subdirectories.

Code and UI presence do not establish that every advertised feature works. Offline helpers include deterministic/rule-based behavior; they are not proof of neural model inference. Optional provider and web-access code exists, so “100% offline,” “nothing leaves your machine,” and “unlimited professional suite” are not verified descriptions of the entire repository.

## Development setup

Use Node.js 22, as in the repository CI. Dependency installation requires network access unless dependencies are already cached.

```bash
git clone https://github.com/HenricHuntsman/AgentFoundry-instantly.git
cd AgentFoundry-instantly
npm ci
npm start
```

Vite is configured on port 3000 and proxies `/api` to port 3001. The backend calls `server.listen(PORT)` without an explicit loopback host; do not assume it is restricted to localhost. Network binding and optional online integrations still need deployment review.

## Checks and builds

```bash
npm test
npm run build
```

The existing CI checks runtime-script syntax, guarded chat tools, the Vite build, and readiness-helper success/timeout paths. Passing those checks does not qualify every historical module.

`npm run electron:build:linux` is a configured packaging command, not evidence that its output has been installed and tested. Linux/macOS/Windows package smoke tests and native dependency compatibility remain separate work.

## What remains

- Test a complete editor → local assistant → saved project workflow.
- Document which routes are live, deterministic demos, optional network features, or unfinished.
- Qualify loopback binding, authentication, storage and offline failure behavior.
- Verify actual local-model inference separately from static analysis and canned output.
- Build, install and test Electron packages on each claimed platform.
- Reconcile older completion reports, tool counts and provider claims against the active code.

## Repository guide

| Path | Purpose |
| --- | --- |
| `src/`, `public/` | Main browser UI and assets |
| `server/` | API routes, services, AI helpers and guarded tools |
| `test/`, `scripts/` | Automated checks and startup helpers |
| `electron.js`, `preload.js` | Desktop wrapper |
| `genspark-2.0/`, `genspark-ai-developer/`, `forge-spark-mvp/` | Separate historical experiments; maturity must be assessed individually |
| `README.legacy.md` | Preserved earlier promotional README |
| Root status/completion reports | Historical reports, not current acceptance evidence |

Internal package identifiers and build-resource paths remain unchanged to preserve compatibility. See [AGENTS.md](AGENTS.md) for development constraints.

*Status reviewed 18 October 2026. No RC/RTM qualification or universal installer claim is made.*
