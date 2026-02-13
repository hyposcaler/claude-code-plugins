# clab

A Claude Code plugin for deploying and managing containerlab SR Linux network labs.

## Prerequisites

- [containerlab](https://containerlab.dev) installed
- Docker running in rootless mode
- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed

## Installation

```
/plugin marketplace add hyposcaler/claude-code-plugins
/plugin install clab@hyposcaler
```

## What it provides

**Agent: `containerlab`** -- A delegated agent that handles containerlab operations,
keeping verbose output out of your main conversation. Claude Code invokes it
automatically when your task involves containerlab or SR Linux.

**Skill: `containerlab`** -- Reference material for containerlab commands,
SR Linux CLI, operational procedures, and troubleshooting. Loaded automatically
into the agent's context.

Capabilities:

- Deploy topologies from `.clab.yml` files (or generate a default 2-node lab)
- Destroy labs with full cleanup
- Inspect running labs and report node status
- Execute SR Linux CLI or shell commands on lab nodes

## Basic usage

Once the plugin is active, give Claude Code natural-language instructions:

```
Deploy a 2-node SR Linux lab
```

```
Show me all running labs
```

```
Run "show version" on node srl1 in the srlinux-lab
```

```
Destroy the srlinux-lab
```

The containerlab agent runs preflight checks, deploys, waits for nodes to boot,
and returns a concise summary with node names, management IPs, and access
instructions.

## Plugin structure

```
clab/
  .claude-plugin/
    plugin.json            # Plugin manifest (name, version, description)
  agents/
    containerlab.md        # Delegated agent definition
  skills/
    containerlab/
      SKILL.md             # Skill reference (commands, procedures, troubleshooting)
```
