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
| `bdd` | Behaviour-Driven Development toolkit — Gherkin authoring, spec reports, UI wireframe sketching, cucumber + Playwright/Appium scaffolding, outside-in TDD planning, run coverage, flow maps, DDL generation | [h2nology/bdd](https://github.com/h2nology/bdd) (subdir `plugin/`) |

## Adding a plugin

Add an entry to `.claude-plugin/marketplace.json`. Each plugin lives in its own
repository and is referenced by source.

Whole repository is the plugin:

```json
{
  "name": "my-plugin",
  "source": { "source": "github", "repo": "owner/repo", "ref": "v1.0.0" },
  "description": "...",
  "version": "1.0.0"
}
```

Plugin lives in a subdirectory (keeps dev-only files out of the user's plugin
cache — there is no exclude/ignore mechanism, the whole source tree is copied):

```json
{
  "name": "my-plugin",
  "source": {
    "source": "git-subdir",
    "url": "https://github.com/owner/repo.git",
    "path": "plugin"
  }
}
```

Omit `ref` to track the repository's default branch (every push publishes).
Set `ref` to a tag to pin users to a released version.

## Verify before pushing

```
/plugin marketplace add ./h2nology-marketplace
```

Plugin repos must already be pushed — `git-subdir` and `github` sources are
fetched from the remote, not from the local working copy.
