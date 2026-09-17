# h2nology marketplace

Claude Code plugin marketplace maintained by [hushukang](https://github.com/h2nology).

## Install

```
/plugin marketplace add h2nology/h2nology-marketplace
/plugin install bdd@h2nology
```

## Plugins

| Plugin | Description | Repo |
| --- | --- | --- |
| `bdd` | Behaviour-Driven Development toolkit — Gherkin authoring, spec reports, UI wireframe sketching, cucumber + Playwright/Appium scaffolding, outside-in TDD planning, run coverage, flow maps, DDL generation | [h2nology/bdd](https://github.com/h2nology/bdd) |

## Adding a plugin

Add an entry to `.claude-plugin/marketplace.json`. Each plugin lives in its own
repository and is referenced by source:

```json
{
  "name": "my-plugin",
  "source": { "source": "github", "repo": "owner/repo", "ref": "v1.0.0" },
  "description": "...",
  "version": "1.0.0"
}
```

Omit `ref` to track the repository's default branch (every push publishes).
Set `ref` to a tag to pin users to a released version.

## Verify before pushing

```
/plugin marketplace add ./h2nology-marketplace
```
