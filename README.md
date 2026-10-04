> **Personal fork of [BMAD-METHOD](https://github.com/bmad-code-org/BMAD-METHOD).** Upstream's README follows below the line.
>
> What this fork changes:
>
> - **Taskwarrior as the source of truth** across the BMAD lifecycle — stories, sprint status and dev-story progress are mirrored into `task`, with Timewarrior tracking time per story.
> - **User preference overlays** injected into every routing and agent skill, so coding standards (TDD, docstrings, error propagation, language choice) apply without restating them per session.
> - **1Password CLI (`op`) as the secrets standard** across all skills — no plaintext `.env` files.
> - An [installation runbook](docs/) for replicating the setup on a new machine.

---

![BMad Method](banner-bmad-method.png)

[![Version](https://img.shields.io/npm/v/bmad-method?color=blue&label=version)](https://www.npmjs.com/package/bmad-method)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Node.js Version](https://img.shields.io/badge/node-%3E%3D20.12.0-brightgreen)](https://nodejs.org)
[![Python Version](https://img.shields.io/badge/python-%3E%3D3.10-blue?logo=python&logoColor=white)](https://www.python.org)
[![uv](https://img.shields.io/badge/uv-package%20manager-blueviolet?logo=uv)](https://docs.astral.sh/uv/)
[![Discord](https://img.shields.io/badge/Discord-Join%20Community-7289da?logo=discord&logoColor=white)](https://discord.gg/gk8jAdXWmj)

**Build More Architect Dreams** — An AI-driven agile development module for the BMad Method Module Ecosystem, the best and most comprehensive Agile AI Driven Development framework that has true scale-adaptive intelligence that adjusts from bug fixes to enterprise systems.

**100% free and open source.** No paywalls. No gated content. No gated Discord. We believe in empowering everyone, not just those who can pay for a gated community or courses.

## Why the BMad Method?

Traditional AI tools do the thinking for you, producing average results. BMad agents and facilitated workflows act as expert collaborators who guide you through a structured process to bring out your best thinking in partnership with the AI.

- **AI Intelligent Help** — Invoke the `bmad-help` skill anytime for guidance on what's next
- **Scale-Domain-Adaptive** — Automatically adjusts planning depth based on project complexity
- **Structured Workflows** — Grounded in agile best practices across analysis, planning, architecture, and implementation
- **Specialized Agents** — 12+ domain experts (PM, Architect, Developer, UX, and more)
- **Party Mode** — Bring multiple agent personas into one session to collaborate and discuss
- **Complete Lifecycle** — From brainstorming to deployment

[Learn more at **docs.bmad-method.org**](https://docs.bmad-method.org)

---

## 🚀 What's Next for BMad?

**V6 is here and we're just getting started!** The BMad Method is evolving rapidly with optimizations including Cross Platform Agent Team and Sub Agent inclusion, Skills Architecture, BMad Builder v1, Dev Loop Automation, and so much more in the works.

**[📍 Check out the complete Roadmap →](https://docs.bmad-method.org/roadmap/)**

---

## Quick Start

**Prerequisites**: [Node.js](https://nodejs.org) v20.12+ · [Python](https://www.python.org) 3.10+ · [uv](https://docs.astral.sh/uv/)

```bash
npx bmad-method install
```

> Want the newest prerelease build? Use `npx bmad-method@next install`. Expect higher churn than the default install.

Follow the installer prompts, then open your AI IDE (Claude Code, Cursor, etc.) in your project folder.

**Non-Interactive Installation** (for CI/CD):

```bash
npx bmad-method install --directory /path/to/project --modules bmm --tools claude-code --yes
```

Override any module config option with `--set <module>.<key>=<value>` (repeatable). Run `--list-options [module]` to see locally-known official keys (built-in modules plus any external officials cached on this machine):

```bash
npx bmad-method install --yes \
  --modules bmm --tools claude-code \
  --set bmm.project_knowledge=research \
  --set bmm.user_skill_level=expert
```

[See all installation options](https://docs.bmad-method.org/how-to/non-interactive-installation/)

> **Not sure what to do?** Ask `bmad-help` — it tells you exactly what's next and what's optional. You can also ask questions like `bmad-help I just finished the architecture, what do I do next?`

## Modules

BMad Method extends with official modules for specialized domains. Available during installation or anytime after.

| Module                                                                                                            | Purpose                                           |
| ----------------------------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| **[BMad Method (BMM)](https://github.com/bmad-code-org/BMAD-METHOD)**                                             | Core framework with 34+ workflows                 |
| **[BMad Builder (BMB)](https://github.com/bmad-code-org/bmad-builder)**                                           | Create custom BMad agents and workflows           |
| **[Test Architect (TEA)](https://github.com/bmad-code-org/bmad-method-test-architecture-enterprise)**             | Risk-based test strategy and automation           |
| **[Game Dev Studio (BMGD)](https://github.com/bmad-code-org/bmad-module-game-dev-studio)**                        | Game development workflows (Unity, Unreal, Godot) |
| **[Creative Intelligence Suite (CIS)](https://github.com/bmad-code-org/bmad-module-creative-intelligence-suite)** | Innovation, brainstorming, design thinking        |

## Web Bundles

V4 shipped web bundles. V6 brings them back, new and improved.

Web bundles package selected BMad skills for installation as **Google Gemini Gems** and **ChatGPT Custom GPTs**. Use them to do the upfront planning work (brainstorming, product briefs, PRDs, PRFAQs, UX specs, market and industry research) in your web LLM subscription, then bring the polished artifacts into your IDE for implementation. Planning runs on a flat-rate subscription instead of metered IDE tokens, which is a meaningful cost saver on longer engagements. Choose the best model available to you in Gemini or ChatGPT.

Current shelf: brainstorming, product brief, PRFAQ, PRD, UX, market & industry research.

**Browse and install at [bmadcode.com/web-bundles](https://bmadcode.com/web-bundles/)**. One card per bundle, inline install steps for Gemini and ChatGPT, one-click ZIP download. See [the web bundles guide](https://docs.bmad-method.org/explanation/web-bundles/) for the concept.

## Documentation

[BMad Method Docs Site](https://docs.bmad-method.org) — Tutorials, guides, concepts, and reference

**Quick links:**

- [Getting Started Tutorial](https://docs.bmad-method.org/tutorials/getting-started/)
- [Upgrading from Previous Versions](https://docs.bmad-method.org/how-to/upgrade-to-v6/)
- [Test Architect Documentation](https://bmad-code-org.github.io/bmad-method-test-architecture-enterprise/)

## Personal Fork — Installation Runbook

This fork adds Taskwarrior/Timewarrior integration, 1Password secrets patterns, and opinionated developer preferences to the upstream BMad Method. The changes live in `customize.toml` files inside `src/bmm-skills/`. To replicate the full environment on a new machine, apply all steps below.

### 1. Install this fork

Clone and install in place of the upstream npm package. When installing BMad into a project, reference the local clone instead of `npx bmad-method`:

```bash
git clone https://github.com/nickvdyck/bmad-method.git ~/code/bmad-method
cd ~/code/bmad-method && npm install
# Then in any project:
node ~/code/bmad-method/tools/installer/bmad-cli.js install
```

### 2. `~/.claude/CLAUDE.md`

Create `~/.claude/CLAUDE.md` with your global development preferences (TDD, devcontainer-only workflow, commit hygiene, language stack, Taskwarrior integration, communication style). See [CLAUDE.md](CLAUDE.md) in this repo for the full template — copy and adapt it.

### 3. `~/.claude.json` — MCP server registrations

Add the following top-level `mcpServers` block to `~/.claude.json` (create the file if it does not exist):

```json
{
  "mcpServers": {
    "searxng": {
      "type": "http",
      "url": "http://127.0.0.1:11236/mcp"
    },
    "crawl4ai": {
      "type": "sse",
      "url": "http://127.0.0.1:11235/mcp/sse"
    },
    "search_bookmarks": {
      "command": "npx",
      "args": ["@karakeep/mcp"],
      "env": {
        "KARAKEEP_API_ADDR": "https://<your-karakeep-host>",
        "KARAKEEP_API_KEY": "<your-karakeep-api-key>"
      }
    },
    "1password": {
      "command": "/usr/lib/opt/1Password/onepassword-mcp"
    }
  }
}
```

The `search_bookmarks` entry requires a running [Karakeep](https://karakeep.app) instance and an API key generated from its settings.

### 4. `~/.claude/settings.json` — hooks, Taskwarrior MCP, plugins

Merge these keys into `~/.claude/settings.json`:

```json
{
  "hooks": {
    "PreCompact": [
      {
        "matcher": "manual",
        "hooks": [
          {
            "type": "command",
            "command": "echo '{\"systemMessage\": \"Before compacting: are there memories or skills from this session worth saving? Review the session and save any important learnings to the memory system before the context is compacted.\"}'",
            "statusMessage": "Memory check reminder..."
          }
        ]
      }
    ]
  },
  "mcpServers": {
    "taskwarrior": {
      "command": "podman",
      "args": [
        "run", "--rm", "-i",
        "-v", "$HOME/.task:$HOME/.task:z",
        "-v", "$HOME/.taskrc:$HOME/.taskrc:ro,z",
        "-e", "TASKRC=$HOME/.taskrc",
        "localhost/mcp-taskwarrior"
      ]
    }
  },
  "enabledPlugins": {
    "clangd-lsp@claude-plugins-official": true,
    "fullstack-dev-skills@fullstack-dev-skills": true,
    "skill-creator@claude-plugins-official": true
  },
  "extraKnownMarketplaces": {
    "fullstack-dev-skills": {
      "source": { "source": "github", "repo": "jeffallan/claude-skills" }
    }
  },
  "permissions": {
    "allow": ["Bash(task *)"]
  }
}
```

Then install the three plugins from within Claude Code:

```
/plugins install clangd-lsp@claude-plugins-official
/plugins install fullstack-dev-skills@fullstack-dev-skills
/plugins install skill-creator@claude-plugins-official
```

### 5. `~/.claude/settings.local.json` — MCP tool permissions

```json
{
  "permissions": {
    "allow": [
      "mcp__searxng__searxng_web_search",
      "mcp__searxng__web_url_read",
      "mcp__crawl4ai__md",
      "mcp__crawl4ai__screenshot",
      "mcp__search_bookmarks__create-bookmark",
      "Bash(podman run *)",
      "Bash(podman build *)",
      "Bash(gh run *)",
      "Bash(npx bmad-method *)"
    ]
  }
}
```

### 6. Build the MCP container images

**Taskwarrior MCP** (`~/.config/mcp-taskwarrior/Containerfile`):

```dockerfile
FROM fedora:latest
RUN dnf install -y nodejs npm task && dnf clean all
RUN npm install -g mcp-server-taskwarrior
ENTRYPOINT ["npx", "mcp-server-taskwarrior"]
```

```bash
mkdir -p ~/.config/mcp-taskwarrior
# write Containerfile above, then:
podman build -t localhost/mcp-taskwarrior ~/.config/mcp-taskwarrior/
```

**SearXNG MCP** (`~/.claude/mcp/searxng/Containerfile`):

```dockerfile
FROM node:lts-alpine
RUN apk update && apk upgrade --no-cache && \
    npm install -g mcp-searxng@1.0.3 && \
    npm cache clean --force
USER node
ENTRYPOINT ["mcp-searxng"]
```

```bash
podman build -t localhost/mcp-searxng:local ~/.claude/mcp/searxng/
```

**crawl4ai MCP** (`~/.claude/mcp/crawl4ai/Containerfile`):

```dockerfile
FROM unclecode/crawl4ai:0.8.6
EXPOSE 11235
```

```bash
podman build -t localhost/crawl4ai-mcp:local ~/.claude/mcp/crawl4ai/
```

### 7. Enable persistent MCP services (systemd user units)

Create `~/.config/systemd/user/searxng-mcp.service`:

```ini
[Unit]
Description=SearXNG MCP server
Wants=network-online.target
After=network-online.target

[Service]
Restart=always
ExecStart=/usr/bin/podman run --rm --sdnotify=conmon --replace -d \
  --name searxng-mcp \
  -p 127.0.0.1:11236:11236 \
  -e SEARXNG_URL=https://<your-searxng-host> \
  -e MCP_HTTP_PORT=11236 \
  localhost/mcp-searxng:local
ExecStop=/usr/bin/podman stop -t 10 searxng-mcp
Type=notify
NotifyAccess=all

[Install]
WantedBy=default.target
```

Create `~/.config/systemd/user/crawl4ai-mcp.service`:

```ini
[Unit]
Description=crawl4ai MCP server
Wants=network-online.target
After=network-online.target

[Service]
Restart=always
ExecStart=/usr/bin/podman run --rm --sdnotify=conmon --replace -d \
  --name crawl4ai-mcp \
  -p 127.0.0.1:11235:11235 \
  localhost/crawl4ai-mcp:local
ExecStop=/usr/bin/podman stop -t 10 crawl4ai-mcp
Type=notify
NotifyAccess=all

[Install]
WantedBy=default.target
```

```bash
systemctl --user daemon-reload
systemctl --user enable --now searxng-mcp crawl4ai-mcp
```

The Taskwarrior MCP container is launched on-demand by Claude Code (step 4) and needs no persistent service.

---

## Community

- [Discord](https://discord.gg/gk8jAdXWmj) — Get help, share ideas, collaborate
- [YouTube](https://youtube.com/@BMadCode) — Tutorials, master class, and more
- [X / Twitter](https://x.com/BMadCode)
- [Website](https://bmadcode.com)
- [GitHub Issues](https://github.com/bmad-code-org/BMAD-METHOD/issues) — Bug reports and feature requests
- [Discussions](https://github.com/bmad-code-org/BMAD-METHOD/discussions) — Community conversations

## Support BMad

BMad is free for everyone and always will be. Star this repo, [buy me a coffee](https://buymeacoffee.com/bmad), or email <contact@bmadcode.com> for corporate sponsorship.

## Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

MIT License — see [LICENSE](LICENSE) for details.

---

**BMad** and **BMAD-METHOD** are trademarks of BMad Code, LLC. See [TRADEMARK.md](TRADEMARK.md) for details.

[![Contributors](https://contrib.rocks/image?repo=bmad-code-org/BMAD-METHOD)](https://github.com/bmad-code-org/BMAD-METHOD/graphs/contributors)

See [CONTRIBUTORS.md](CONTRIBUTORS.md) for contributor information.
