# web-access

Full internet access for AI agents — CDP browser automation + web search + direct HTTP.

> OpenClaw Skill — works with [OpenClaw](https://github.com/openclaw/openclaw) AI agents

## What It Does

Provides comprehensive web access capabilities for AI agents through a 3-layer architecture: CDP browser automation (Chrome DevTools Protocol) for dynamic pages and login-required sites, web search integration for information discovery, and direct HTTP fetching for static content. Supports page navigation, form filling, content extraction, and authenticated browsing sessions.

## Quick Start

```bash
# Install via ClawHub (recommended)
openclaw skill install web-access

# Or clone this repo
git clone https://github.com/rrrrrredy/web-access.git ~/.openclaw/skills/web-access
```

### Prerequisites

- Node.js 22+ (uses native WebSocket)
- Chrome with remote debugging enabled:
  Open `chrome://inspect/#remote-debugging` → check "Allow remote debugging"

## Features

- **CDP browser automation**: Full Chrome DevTools Protocol integration for dynamic page interaction
- **3-layer channel selection**: CDP (dynamic pages) / web search (discovery) / direct HTTP (static) — selected per scenario
- **Login-aware sessions**: Preserves authentication state across page navigations
- **Site pattern matching**: Configurable per-site strategies for optimal extraction
- **Dependency auto-check**: `check-deps.mjs` validates environment before operations
- **Parallel page processing**: Divide-and-conquer for multi-page tasks

## Usage

Trigger phrases:
- "搜索信息"、"查看网页内容"、"访问需要登录的网站"
- "操作网页界面"、"读取动态渲染页面"
- "抓取社交媒体内容（小红书、微博、推特等）"
- "任何需要真实浏览器环境的网络任务"

## Project Structure

```
web-access/
├── SKILL.md              # Main skill definition
├── .claude-plugin/       # Claude plugin config
│   ├── plugin.json
│   └── marketplace.json
├── scripts/
│   ├── cdp-proxy.mjs     # CDP proxy server
│   ├── check-deps.mjs    # Dependency checker
│   └── match-site.mjs    # Site pattern matcher
├── references/
│   ├── cdp-api.md        # CDP API reference
│   └── site-patterns/    # Per-site extraction configs
│       └── .gitkeep
└── .gitignore
```

## Requirements

- [OpenClaw](https://github.com/openclaw/openclaw) agent runtime
- Node.js 22+
- Chrome/Chromium with remote debugging enabled

## License

[MIT](LICENSE)
