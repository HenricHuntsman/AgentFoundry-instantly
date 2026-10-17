# AgentFoundry Workspace — development setup

Status: alpha. This is a JavaScript application workspace, not a Linux distribution or a universally qualified desktop installer.

## Prerequisites

Use Node.js 22 and npm, matching the existing CI. Dependency installation requires network access unless dependencies are cached. Platform-native dependencies and Electron packaging may need additional prerequisites.

```bash
git clone https://github.com/HenricHuntsman/AgentFoundry-instantly.git
cd AgentFoundry-instantly
npm ci
npm test
npm run build
npm start
```

Vite uses port 3000 and proxies `/api` to backend port 3001. Full startup and native-package installation remain to be qualified on each target platform. The backend does not explicitly bind to loopback, so localhost-only exposure is not guaranteed.

## Verification from this review

On 18 October 2026, `npm ci --ignore-scripts --no-audit --no-fund`, `npm test` (22 passing tests), and `npm run build` succeeded in the review environment. Skipping install scripts matches CI's dependency-install path; it does not validate native dependency installation or Electron installers. The web build reported a large-bundle warning.

`npm run electron:build:linux` is configured but was not executed in this review. No AppImage/deb/macOS/Windows installer is claimed to be qualified.

## Network and optional features

Local deterministic code analysis differs from model inference. Provider, crawling and other network code exists in the repository. No API key is required for basic offline helpers; verify each feature's actual behavior before relying on a fully offline deployment.

The former installation guide is preserved in [INSTALL.legacy.md](INSTALL.legacy.md). Its old Node/platform requirements and one-line install recommendations are historical, not current compatibility evidence.

See [README.md](README.md) for current scope and remaining work.
