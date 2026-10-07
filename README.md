# codex-setup

Personal Codex instructions, specialist agents, quality guides, and focused skills. The main session coordinates substantial tasks. Small tasks stay in one session.

## Contents

| Path | Purpose |
| --- | --- |
| `AGENTS.md` | Communication, authorization, task routing, and context rules |
| `agents/` | Backend, frontend, mobile, researcher, QA, reviewer, and security reviewer roles |
| `guides/` | Workflow, delegation, writing, memory, and language quality guidance |
| `skills/` | Planning, frontend design, browser checks, and test-driven development |
| `config.example.toml` | Portable model, status line, and memory settings |
| `setup/` | Optional RTK hook and command exclusions |

Guides and skills are loaded when relevant. They do not require every agent to run on every task. Python 3.12 or later is the personal default; project requirements take precedence.

## First setup on a new device

These commands target macOS or Linux with Bash, Git, and the default Codex directory, `~/.codex`. Use that directory for this setup: the instructions refer to `~/.codex/guides`. If you use a different `CODEX_HOME`, adapt the paths before installation.

### 1. Install Codex

Follow the [official OpenAI Codex CLI instructions](https://learn.chatgpt.com/docs/codex/cli). With Node.js and npm installed, you can use:

```bash
npm install -g @openai/codex
codex --version
```

### 2. Install this configuration

If `~/.codex` does not exist, clone directly into it:

```bash
git clone https://github.com/NovelioPI/codex-setup.git "$HOME/.codex"
cd "$HOME/.codex"
```

If `~/.codex` already exists, preserve its local state. Clone into a separate directory and use `rsync` to copy only the reusable instructions. Install `rsync` first if it is unavailable. Review the dry-run before the copy:

```bash
git clone https://github.com/NovelioPI/codex-setup.git "$HOME/codex-setup"
cd "$HOME/codex-setup"
rsync -avn AGENTS.md agents guides skills "$HOME/.codex/"
rsync -av --backup --suffix=.before-codex-setup AGENTS.md agents guides skills "$HOME/.codex/"
```

The copy replaces matching instructions and saves their previous content with the `.before-codex-setup` suffix. It does not delete other files or copy authentication, local settings, or Git metadata. Keep the separate checkout for future updates. Remove or archive saved instruction copies after you inspect the changes.

Create local settings only if they do not exist:

```bash
if [ ! -e "$HOME/.codex/config.toml" ]; then
  cp config.example.toml "$HOME/.codex/config.toml"
fi
```

For existing settings, merge the example manually. Choose a model available to your account. The example does not configure approval policy, sandbox permissions, plugins, or hook trust.

### 3. Sign in and verify

Start Codex from a project directory and follow the sign-in prompt:

```bash
cd /path/to/your/project
codex
```

Ask Codex to explain the loaded working agreements before you request edits. Restart existing sessions after installing these files. Available custom agents and skills depend on the installed Codex version and harness; configuration files alone do not prove that a role was loaded.

The Playwright skill requires Node.js and `npx`. Its wrapper uses `@playwright/cli` on demand. Browser checks also require the browsers supported by that CLI. Follow its setup output when you first use it.

## Optional RTK output compression

RTK reduces the output of supported development commands. Install it with the [official RTK instructions](https://github.com/rtk-ai/rtk#installation), then check:

```bash
command -v rtk
rtk --version
```

Copy the hook only if no local hook file exists:

```bash
if [ ! -e "$HOME/.codex/hooks.json" ]; then
  cp setup/hooks.example.json "$HOME/.codex/hooks.json"
fi
mkdir -p "$HOME/.config/rtk"
if [ ! -e "$HOME/.config/rtk/config.toml" ]; then
  cp setup/rtk.config.toml "$HOME/.config/rtk/config.toml"
fi
```

If either file exists, merge the relevant entries manually. If `XDG_CONFIG_HOME` is set, use its `rtk/config.toml` path instead. The exclusions preserve raw source reads, searches, and review diffs.

The hook command requires `rtk` on the PATH inherited by Codex. If that PATH differs from your terminal PATH, set the absolute executable path in your local `hooks.json`.

In Codex, open `/hooks`, inspect the RTK entry, and trust its current definition. Repeat this review after hook changes. Trust is device-local and is not included in this repository. See the [official OpenAI hook documentation](https://learn.chatgpt.com/docs/hooks).

Confirm interception with a supported command and inspect `rtk gain`. A valid hook file does not prove that a command passed through the hook. To disable this integration, disable the RTK entry in `/hooks`.

## Plugins and private state

Install and authenticate plugins separately when a project needs them. This repository does not include plugin downloads, account connections, or system skills supplied by Codex. Graft and gh-axi are not part of this setup.

The `.gitignore` permits selected public paths and ignores new root paths by default. It excludes local settings and hooks, credentials, sessions, history, memory, databases, caches, logs, backups, and generated output. Add a new public path only after you inspect its content. Do not force-add private files.

Before a commit, inspect the exact files and changes:

```bash
git status --short
git diff --cached --stat
git diff --cached
```

## Updates

Run `git pull --ff-only` from the configuration checkout after you resolve local changes. For a separate checkout, repeat the instruction copy from step 2. Merge changes to configuration and hook examples into local settings manually. Recheck hook trust after local hook changes.

## Sources and licenses

The frontend design skill was adapted from [Anthropic skills](https://github.com/anthropics/skills/tree/main/skills/frontend-design). The Playwright skill comes from the [OpenAI skill collection](https://github.com/openai/skills/tree/main/skills/.curated/playwright) and includes material from Microsoft Playwright CLI. Their bundled license and notice files are retained. The frontend skill records its local adaptation in `SKILL.md`.

The planning and TDD skills contain local guidance inspired by [Matt Pocock's skills](https://github.com/mattpocock/skills). This repository does not install that full collection.
