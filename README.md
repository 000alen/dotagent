# dotagent

My public, portable Codex setup, managed with
[chezmoi](https://chezmoi.io/).

It installs native Codex conventions rather than a custom framework:

- `~/.codex/AGENTS.md` for global preferences;
- `~/.codex/config.toml` for portable settings and tool declarations;
- `~/.codex/skills/` for reusable Agent Skills.

Credentials, OAuth state, sessions, caches, generated catalogs, private data,
and machine-specific provider configuration do not belong here.

## Install

Install `chezmoi`, then preview the changes:

```bash
chezmoi init 000alen/dotagent
chezmoi diff
```

Apply when the diff looks right:

```bash
chezmoi apply
```

For a new machine where `~/.codex` has no configuration to preserve:

```bash
chezmoi init --apply 000alen/dotagent
```

This repository intentionally manages the complete portable `config.toml`.
Review the diff first on a machine that already has custom providers, profiles,
or machine-local paths, and keep those settings outside this public repository.

## Tool setup

The config declares the Linear MCP endpoint. Authenticate separately on each
machine:

```bash
codex mcp login linear
```

Install and connect the curated Slack plugin separately so its account state
remains local:

```bash
codex plugin add slack@openai-curated-remote
```

## Updating

Edit through chezmoi so the source repository remains authoritative:

```bash
chezmoi edit ~/.codex/AGENTS.md
chezmoi diff
chezmoi apply
```
