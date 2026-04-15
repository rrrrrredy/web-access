# web-access

Full internet access for AI agents — 3-layer channel scheduling + browser CDP + parallel divide-and-conquer.

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
- **3-layer channel scheduling**: CDP → web search → direct HTTP, automatic fallback
- **Login-aware sessions**: Preserves authentication state across page navigations
- **Site pattern matching**: Configurable per-site strategies for optimal extraction
- **Dependency auto-check**: `check-deps.mjs` validates environment before operations
- **Parallel page processing**: Divide-and-conquer for multi-page tasks

## Usage

Trigger phrases:
- "打开网页"、"网页自动化"、"登录某网站"
- "填写表单"、"操作页面"、"读取动态渲染"
- "CDP"、"浏览器自动化"

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
└── .gitignore
```

## Requirements

- [OpenClaw](https://github.com/openclaw/openclaw) agent runtime
- Node.js 22+
- Chrome/Chromium with remote debugging enabled

## License

[MIT](LICENSE)
