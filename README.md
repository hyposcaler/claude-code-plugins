# Hyposcaler Plugins

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) plugin marketplace.

## Installation

Add the marketplace from within Claude Code:

```
/plugin marketplace add hyposcaler/claude-code-plugins
```

Then install any plugin by name:

```
/plugin install <plugin-name>@hyposcaler
```

## Available plugins

| Plugin | Description |
|--------|-------------|
| [clab](plugins/clab/) | Deploy, inspect, and manage containerlab SR Linux network labs |

## Local development

To develop or test a plugin locally, point Claude Code at its directory:

```
claude --plugin-dir /path/to/claude-code-plugins/plugins/<plugin-name>
```

## Repository structure

```
claude-code-plugins/
  .claude-plugin/
    marketplace.json           # Marketplace catalog
  plugins/
    clab/                      # Containerlab plugin
      ...
  README.md
```

Each plugin under `plugins/` is self-contained with its own manifest, agents, and skills. See individual plugin READMEs for details.
