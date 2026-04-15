# web-access

Full internet access for AI agents — CDP browser automation + web search + direct HTTP.

> OpenClaw Skill — works with [OpenClaw](https://github.com/openclaw/openclaw) AI agents

## What It Does

Provides comprehensive web access capabilities for AI agents through CDP browser automation (Chrome DevTools Protocol) for dynamic pages and login-required sites, web search for information discovery, and direct HTTP fetching for static content. The appropriate tool is selected per scenario based on task requirements. Supports page navigation, form filling, content extraction, and authenticated browsing sessions.

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
- **Tool selection per scenario**: CDP (dynamic/login-required pages), web search (information discovery), direct HTTP (static content) — chosen based on task needs
- **Login-aware sessions**: Preserves authentication state across page navigations
- **Site pattern matching**: Configurable per-site strategies for optimal extraction
- **Dependency auto-check**: `check-deps.mjs` validates environment before operations
- **Parallel page processing**: Divide-and-conquer for multi-page tasks

## Usage

**触发词：**
- `打开网页` — 打开并浏览网页
- `网页自动化` — 自动化网页操作
- `登录某网站` — 需要登录态的网站访问
- `填写表单` — 自动填写网页表单
- `操作页面` — 页面交互操作
- `读取动态渲染` — 读取 JavaScript 动态渲染的页面内容
- `CDP` — Chrome DevTools Protocol 相关操作
- `浏览器自动化` — 通用浏览器自动化任务

**不适用：** 社交媒体平台内容搜索提取（公众号/小红书/推特/B站等请用 all-net-search-read）；简单网页内容读取（用 web_fetch）。

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
