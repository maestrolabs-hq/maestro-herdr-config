# Integrations

## Pi

Herdr recognizes Pi as a first-class agent through a managed extension Herdr
installs into a Pi installation's extensions directory
(`~/.pi/agent/extensions/herdr-agent-state.ts`). The extension reports
lifecycle state (`idle`, `working`, `blocked`) and a native session reference
directly to Herdr's socket API, so Herdr does not fall back to screen-scraping
to classify a Pi pane, and a Pi conversation can resume after a Herdr server
restart.

| Field | Value |
| --- | --- |
| Integration id | `pi` (`HERDR_INTEGRATION_ID=pi`) |
| Integration version | `8` (`HERDR_INTEGRATION_VERSION=8`, read from the managed file's own header) |
| Managed file | `~/.pi/agent/extensions/herdr-agent-state.ts` — reinstalling or updating the integration overwrites this file; it is not hand-edited |

## Pi-side extensions are out of scope here

The managed integration file itself, and any custom Pi extension placed
beside it (for example a task-label reporter that uses Herdr's metadata API
for sidebar presentation), are Pi runtime state. They are captured by
[maestro-pi-config](https://github.com/maestrolabs-hq/maestro-pi-config)
under its `extensions/` directory, not by this repository. This repository
records only that the integration exists and which version is active, so a
restore can verify the two repositories agree.
