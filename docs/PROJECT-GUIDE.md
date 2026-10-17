# Project and folder guide

Stage: alpha application, not an operating system.

| Folder | Role |
| --- | --- |
| src/, public/ | Active browser application |
| server/ | Active services; verify each route before claiming support |
| test/, scripts/ | Checks and launch helpers |
| docs/history/ | Preserved old reports and plans; not acceptance evidence |
| genspark-2.0/, genspark-ai-developer/, forge-spark-mvp/, github-2.0/, ai-suite-pro-mobile/, tv-radio-streaming/, unrestricted-suite/ | Separate experiments; not merged into the active root application by this cleanup |

Electron entry points remain at the root to preserve configured paths. Dependency manifests, launchers and source folders retain their existing locations.

Previously executed: 22 tests and Vite build passed. Linux installers and a complete editor → local model → saved project workflow still need qualification. Next: reproduce the root build, test that workflow, then package and install the Linux application.

[Historical document index](history/README.md) · [Current README](../README.md)
