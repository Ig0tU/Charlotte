<p align="center">
  <img src="assets/bannerGif10.gif" alt="CLI Anything Web" width="100%">
</p>

<h1 align="center">CLI-Anything-WEB: Making the Web Agent-Native</h1>

<p align="center">
  <strong>Today's Web Serves Humans👨‍💻. Tomorrow's Users will be Agents🤖.<br>
CLI-Anything-WEB: Bridging the Gap Between AI Agents and the World's Web Apps</strong><br>
</p>

<p align="center">
  <a href="#-quick-start">Quick Start</a> &nbsp;&bull;&nbsp;
  <a href="#-examples">Examples</a> &nbsp;&bull;&nbsp;
  <a href="#%EF%B8%8F-how-it-works">How It Works</a> &nbsp;&bull;&nbsp;
  <a href="#-supported-protocols">Protocols</a> &nbsp;&bull;&nbsp;
  <a href="https://itamarzand88.github.io/CLI-Anything-WEB/registry/">Registry</a> &nbsp;&bull;&nbsp;
  <a href="#-whats-next">Roadmap</a> &nbsp;&bull;&nbsp;
  <a href="#-contributing">Contributing</a>
</p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License: MIT"></a>
  <a href="https://github.com/ItamarZand88/CLI-Anything-WEB/stargazers"><img src="https://img.shields.io/github/stars/ItamarZand88/CLI-Anything-WEB?style=social" alt="GitHub Stars"></a>
  <a href="https://github.com/ItamarZand88/CLI-Anything-WEB/issues"><img src="https://img.shields.io/github/issues/ItamarZand88/CLI-Anything-WEB" alt="Issues"></a>
  <img src="https://img.shields.io/badge/python-3.10%2B-blue" alt="Python 3.10+">
  <img src="https://img.shields.io/badge/CLIs_generated-19-brightgreen" alt="19 CLIs">
  <img src="https://img.shields.io/badge/claude%20code-plugin-blueviolet" alt="Claude Code Plugin">
  <a href="https://itamarzand88.github.io/CLI-Anything-WEB/registry/"><img src="https://img.shields.io/badge/registry-live-orange" alt="CLI Registry"></a>
</p>

**🌐 [CLI-Hub](https://itamarzand88.github.io/CLI-Anything-WEB/)**: `pip install cli-anything-hub` then `cli-hub install <name>` — browse, install, and manage all community-built web CLIs. Want to add your own? [Open a PR](https://github.com/ItamarZand88/CLI-Anything-WEB/blob/main/CONTRIBUTING.md) — the hub updates instantly.

**🎬 [See Demos](#-examples)**: Watch AI agents use generated CLIs to produce real artifacts.

**🙋 [Become a Contributor, or Request a CLI]**: [Join us](https://github.com/ItamarZand88/CLI-Anything-WEB/issues/new)! Sign up to build a new CLI harness. Wish CLI-Anything-WEB supported a specific website? Submit a [request](https://github.com/ItamarZand88/CLI-Anything-WEB/issues/new)!

---

**CLI-Anything-Web** is a [Claude Code](https://docs.anthropic.com/en/docs/claude-code) plugin that generates production-grade Python CLIs for **any** web application by capturing its live HTTP traffic. Point it at a URL, and get a fully working CLI on your PATH — with auth, REPL mode, `--json` output, and tests.

> [!WARNING]
> **Experimental Project — Use Responsibly**
>
> This project uses **undocumented web APIs** reverse-engineered from live HTTP traffic. These APIs can change without notice.
>
> - **Not affiliated with any website** — This is an independent open-source project
> - **APIs may break** — Websites can change their internal endpoints, HTML structure, or add protections at any time
> - **Respect rate limits** — Generated CLIs include exponential backoff, but heavy usage may be throttled
> - **For personal use** — Best suited for prototyping, automation, research, and personal productivity
>
> Generated CLIs interact with real production services. Use them responsibly and in accordance with each website's terms of service.

## 🤔 Why CLI?

CLI is the universal interface for both humans and AI agents:

- **Structured & Composable** - Text commands match LLM format and chain for complex workflows
- **Lightweight & Universal** - Minimal overhead, works across all systems without dependencies
- **Self-Describing** - `--help` flags provide automatic documentation agents can discover
- **Agent-First Design** - Structured JSON output eliminates parsing complexity
- **Deterministic & Reliable** - Consistent results enable predictable agent behavior

## 🚀 Quick Start

CLI-Anything-WEB has two equally useful starting points:

| Goal | Start Here |
|------|------------|
| **Use existing web CLIs now** | Install `cli-anything-hub`, browse the registry, and install ready-made CLIs. |
| **Build a new web CLI** | Install the CLI-Anything-WEB plugin for Claude Code, then run the generation pipeline. |

### Phase 1: Empower yourself — your CLI toolkit

Install the **CLI-Hub** package manager first. It lets you browse, search, inspect, install, update, uninstall, and launch CLI-Anything-WEB harnesses plus public third-party CLIs from one command.

```bash
pip install cli-anything-hub

# Browse what is available
cli-hub list
cli-hub search hotel

# Install and try a CLI immediately
cli-hub install cli-web-booking
cli-hub info cli-web-booking
cli-hub launch cli-web-booking
```

### Phase 1.5: Empower your agents — install in one command

Give SKILL-compatible agents the **CLI-Hub meta-skill** so they can discover and install the right CLI for a task.

```bash
npx skills add ItamarZand88/CLI-Anything-WEB --skill cli-hub-meta-skill -g -y
```

Works with: OpenClaw, Nanobot, Claude Code, Codex, and other SKILL-compatible agents.

### Phase 2: Build a new CLI when the registry does not have one yet

#### Prerequisites

| Requirement | Version | Why |
|------------|---------|-----|
| [Claude Code](https://docs.anthropic.com/en/docs/claude-code) | With plugin support | Runs the generation pipeline |
| [Node.js](https://nodejs.org/) | 18+ | For playwright traffic capture |
| [Python](https://python.org/) | 3.10+ | Generated CLIs are Python |

#### Install the Plugin

```bash
# Inside Claude Code
/plugin marketplace add ItamarZand88/CLI-Anything-WEB
/plugin install cli-anything-web
/reload-plugins
```

#### Generate Your First CLI

```bash
/cli-anything-web https://your-favorite-website.com
```

The agent opens a browser, asks you to log in if needed, captures traffic, and generates a complete CLI. That's it.

<br>

## 📦 Examples

19 real CLIs generated by the plugin — shipped as reference implementations:

| CLI | Website | Protocol | Auth | Skill | Description |
|-----|---------|----------|------|-------|-------------|
| [`cli-web-stitch`](stitch/) | Google Stitch | batchexecute RPC | Google SSO | [📖 Skill](skills/cli-web-stitch/SKILL.md) | AI UI design — generate mobile/web app mockups from text prompts |
| [`cli-web-reddit`](reddit/) | Reddit | REST JSON API (curl_cffi) | Optional (OAuth) | [📖 Skill](skills/cli-web-reddit/SKILL.md) | Feeds, subreddits, search, vote, comment, submit, save, inbox |
| [`cli-web-booking`](booking/) | Booking.com | GraphQL + HTML (curl_cffi) | WAF cookies | [📖 Skill](skills/cli-web-booking/SKILL.md) | Hotel search, property details, destination resolution |
| [`cli-web-gai`](gai/) | Google AI Mode | Browser-rendered (Playwright) | None | [📖 Skill](skills/cli-web-gai/SKILL.md) | AI-powered search with source references |
| [`cli-web-notebooklm`](notebooklm/) | Google NotebookLM | batchexecute RPC | Google SSO | [📖 Skill](skills/cli-web-notebooklm/SKILL.md) | Notebooks, sources, chat, 9 artifact types (audio, video, slides, quiz, mindmap) |
| [`cli-web-pexels`](pexels/) | Pexels | SSR + __NEXT_DATA__ (curl_cffi) | None | [📖 Skill](skills/cli-web-pexels/SKILL.md) | Free stock photos & videos — search, download, collections, profiles |
| [`cli-web-unsplash`](unsplash/) | Unsplash | REST API (curl_cffi) | None | [📖 Skill](skills/cli-web-unsplash/SKILL.md) | Photo search, download, topics, collections, profiles |
| [`cli-web-producthunt`](producthunt/) | Product Hunt | HTML scraping (curl_cffi) | None | [📖 Skill](skills/cli-web-producthunt/SKILL.md) | Today's launches, leaderboards, product details |
| [`cli-web-futbin`](futbin/) | FUTBIN | HTML + JSON API | None | [📖 Skill](skills/cli-web-futbin/SKILL.md) | EA FC player database — search, compare, prices, market analysis, arbitrage, trading signals |
| [`cli-web-gh-trending`](gh-trending/) | GitHub Trending | HTML scraping | None | [📖 Skill](skills/cli-web-gh-trending/SKILL.md) | Trending repos & developers with language/time filters |
| [`cli-web-youtube`](youtube/) | YouTube | InnerTube REST API | None | [📖 Skill](skills/cli-web-youtube/SKILL.md) | Search videos, video details, trending, channel info |
| [`cli-web-hackernews`](hackernews/) | Hacker News | REST API (Firebase + Algolia) | Cookie (optional) | [📖 Skill](skills/cli-web-hackernews/SKILL.md) | Stories, search, comments, users, upvote, submit, comment, favorite |
| [`cli-web-codewiki`](codewiki/) | Google Code Wiki | batchexecute RPC | None | [📖 Skill](skills/cli-web-codewiki/SKILL.md) | AI-generated repo docs, wiki sections, Gemini chat, download as .md |
| [`cli-web-chatgpt`](chatgpt/) | ChatGPT | REST API + Camoufox | Browser (OpenAI SSO) | [📖 Skill](skills/cli-web-chatgpt/SKILL.md) | Ask questions, generate/download images, conversations, models |
| [`cli-web-airbnb`](airbnb/) | Airbnb | SSR HTML + niobeClientData | None | [📖 Skill](skills/cli-web-airbnb/SKILL.md) | Search stays, listing details, amenities, host info, autocomplete locations |
| [`cli-web-amazon`](amazon/) | amazon.com | SSR HTML + REST JSON | None | [📖 Skill](skills/cli-web-amazon/SKILL.md) | Search products, view details, browse bestsellers |
| [`cli-web-tripadvisor`](tripadvisor/) | TripAdvisor | SSR HTML + JSON-LD (curl_cffi) | None | [📖 Skill](skills/cli-web-tripadvisor/SKILL.md) | Search locations, hotels, restaurants, and attractions |
| [`cli-web-linkedin`](linkedin/) | LinkedIn | GraphQL + Voyager REST (curl_cffi) | Cookie (li_at) | [📖 Skill](skills/cli-web-linkedin/SKILL.md) | Search, feed, profiles, jobs, posts, reactions, comments, network, messaging (26 cmds) |
| [`cli-web-capitoltrades`](capitoltrades/) | Capitol Trades | SSR HTML + BFF JSON (curl_cffi) | None | [📖 Skill](skills/cli-web-capitoltrades/SKILL.md) | US congressional stock trades (STOCK Act) — trades, politicians, issuers, price history |

<br>

## ⚙️ How It Works

The plugin runs a 4-phase pipeline, fully automated by Claude:

<p align="center">
  <img src="assets/pipeline.png" alt="CLI-Anything-Web Pipeline" width="100%">
</p>

| Phase | What Happens |
|-------|-------------|
| **1. Capture** | Opens browser via Playwright, records all HTTP traffic while you use the site |
| **2. Analyze & Generate** | Identifies protocol (REST/GraphQL/RPC/HTML), maps endpoints, generates full Python CLI |
| **3. Test** | Writes unit tests (mocked) + E2E tests (live API) + subprocess tests |
| **4. Publish** | `pip install -e .` → on your PATH → smoke tested → Claude skill generated |

<br>

## 🔧 What Every Generated CLI Includes

| Feature | Details |
|---------|---------|
| **Click commands** | `cli-web-<app> <group> <command> [options]` |
| **Interactive REPL** | Run with no args — history, autocomplete, branded prompt |
| **`--json` output** | Machine-readable on every command — pipe into `jq`, scripts, or agents |
| **Auth management** | Python Playwright browser login → cookie extraction → `auth.json` |
| **Error handling** | Typed exceptions → structured JSON errors: `{"error": true, "code": "AUTH_EXPIRED"}` |
| **Tests** | Unit (mocked HTTP) + E2E (live API) + subprocess (`_resolve_cli`) |
| **Installable** | `pip install -e .` puts it on your PATH immediately |

## 📋 Commands

| Command | Description |
|---------|-------------|
| `/cli-anything-web <url>` | Full pipeline — capture, analyze, generate, publish |
| `/cli-anything-web:record <url>` | Capture traffic only (for exploration) |
| `/cli-anything-web:refine <path>` | Add more commands to an existing CLI |
| `/cli-anything-web:test <path>` | Run tests and update TEST.md |
| `/cli-anything-web:validate <path>` | Validate against 75-check quality standards |
| `/cli-anything-web:list` | List all generated CLIs |

<br>

## 🌐 Supported Protocols

The plugin auto-detects and handles multiple web architectures:

| Protocol | Example Sites | How It's Handled |
|----------|--------------|-----------------|
| **REST / JSON API** | Monday.com, Dev.to | `httpx` client, JSON response parsing |
| **Server-rendered HTML** | GitHub, FUTBIN, Hacker News | `BeautifulSoup4` + CSS selectors |
| **Cloudflare-protected** | Product Hunt, Unsplash | `curl_cffi` with Chrome TLS impersonation |
| **GraphQL** | Shopify, GitHub API v4 | Query abstraction into CLI commands |
| **GraphQL + AWS WAF** | Booking.com | `curl_cffi` + WAF cookie bypass |
| **Google batchexecute** | NotebookLM, Google Docs, Keep | Custom RPC encoder/decoder |
| **Browser-rendered (Playwright)** | Google AI Mode | Headless browser rendering + content extraction |

<br>

## 🏗️ Repository Structure

```
CLI-Anything-WEB/
├── cli-anything-web-plugin/     # 🔌 The installable Claude Code plugin
│   ├── commands/                #    Slash command definitions
│   ├── skills/                  #    4-phase pipeline skills
│   └── HARNESS.md               #    Complete methodology SOP
├── cli-hub/                     # 📦 CLI-Hub package manager
├── cli-hub-meta-skill/          # 🤖 Meta-skill for agent discovery
├── skills/                      # 📖 Canonical SKILL.md repository
├── stitch/                      # 🎨 Google Stitch
├── reddit/                      # 💬 Reddit
├── booking/                     # 🏨 Booking.com
├── gai/                         # 🤖 Google AI Mode
├── notebooklm/                  # 📓 NotebookLM
├── pexels/                      # 📸 Pexels
├── unsplash/                    # 📷 Unsplash
├── producthunt/                 # 🚀 Product Hunt
├── futbin/                      # 🎮 FUTBIN
├── gh-trending/                 # 📈 GitHub Trending
├── youtube/                     # 🎬 YouTube
├── hackernews/                  # 📰 Hacker News
├── codewiki/                    # 📚 Google Code Wiki
├── chatgpt/                     # 🤖 ChatGPT
├── airbnb/                      # 🏠 Airbnb
├── amazon/                      # 🛒 Amazon
├── tripadvisor/                 # 🌍 TripAdvisor
├── linkedin/                    # 💼 LinkedIn
└── capitoltrades/               # 🏛️ Capitol Trades
```

<br>

## 🔗 Inspiration

This project is directly inspired by [**CLI-Anything**](https://github.com/HKUDS/CLI-Anything) by HKUDS — a Claude Code plugin that makes **desktop software** (GIMP, Blender, LibreOffice, OBS Studio) agent-native by analyzing source code and generating CLI wrappers.

**CLI-Anything-Web** extends the same vision to the **web** — where there's no source code to analyze, only live HTTP traffic to capture.

| | [**CLI-Anything**](https://github.com/HKUDS/CLI-Anything) | **CLI-Anything-Web** |
|---|---|---|
| **Target** | Desktop apps (GIMP, Blender, OBS) | Web apps (NotebookLM, Booking.com, any website) |
| **Input** | Source code, GUI APIs, plugin systems | Live HTTP traffic from browser |
| **Analysis** | Static code analysis + API mapping | Network traffic capture + protocol detection |
| **Auth** | N/A (local software) | Browser login, cookies, WAF bypass, API keys |
| **Output** | Click CLI + REPL + `--json` + tests | Click CLI + REPL + `--json` + tests |

Together they cover the full spectrum: **CLI-Anything** for desktop, **CLI-Anything-Web** for the web.

<br>

## 🗺️ What's Next

We're actively building more CLIs and improving the plugin:

- 🎯 **More CLIs** — Jira, Notion, Monday.com, Spotify
- 🎵 **Content generation** — Suno, ElevenLabs, Midjourney
- 🧠 **Smarter analysis** — Auto-detect auth flows, pagination, WebSocket streams
- 🔄 **CI/CD integration** — Run CLIs in GitHub Actions with env-var auth
- 📦 **Community registry** — Share and install CLIs built by other users

**Want a specific website?** [Open an issue](https://github.com/ItamarZand88/CLI-Anything-WEB/issues/new) with the URL — we'll prioritize the most requested ones.

<br>

## 🤝 Contributing

We'd love your help! See **[CONTRIBUTING.md](CONTRIBUTING.md)** for the full guide.

The quickest ways to contribute:

| What | How |
|------|-----|
| **Build a new CLI** | Run `/cli-anything-web <url>` on any website, submit a PR |
| **Improve the plugin** | Add patterns to `cli-anything-web-plugin/skills/` |
| **Report bugs** | [Open an issue](https://github.com/ItamarZand88/CLI-Anything-WEB/issues) with `--json` output |
| **Fix a broken CLI** | Website changed? Update the scraper/client |

<br>

<br>

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

<p align="center">
  Built with <a href="https://docs.anthropic.com/en/docs/claude-code">Claude Code</a> &nbsp;·&nbsp;
  Inspired by <a href="https://github.com/HKUDS/CLI-Anything">CLI-Anything</a> &nbsp;·&nbsp;
  <a href="https://github.com/ItamarZand88/CLI-Anything-WEB/issues/new">Request a CLI</a>
</p>
