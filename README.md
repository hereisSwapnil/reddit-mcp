# Reddit MCP

A Model Context Protocol (MCP) server for browsing Reddit directly from Claude Desktop.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
![Python](https://img.shields.io/badge/python-3.12+-green.svg)

## ✨ Features

- 🔍 **Browse Subreddits** - View posts from any subreddit with flexible sorting
- 🔎 **Search Reddit** - Search across Reddit or within specific communities
- 📄 **Post Details** - Get full post content with threaded comments
- 👤 **User Analysis** - Analyze Reddit user activity and statistics
- 🔓 **No Auth Required** - Works immediately in anonymous mode
- ⚡ **Optional OAuth** - Add credentials for higher rate limits

## 🚀 Installation

### One-Click Install (Recommended)

1. **Install `uv`** (if not already installed):
   
   **macOS/Linux:**
   ```bash
   curl -LsSf https://astral.sh/uv/install.sh | sh
   sudo ln -sf ~/.local/bin/uv /usr/local/bin/uv
   ```
   
   **Windows:**
   ```powershell
   powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
   ```

2. **[⬇️ Download reddit-mcp.mcpb](https://github.com/hereisSwapnil/reddit-mcp/releases/download/v1.0.0/reddit-mcp.mcpb)**

3. **Double-click** the downloaded file to install in Claude Desktop

4. **Done!** Start using Reddit tools in Claude

### Manual Installation

Add to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "reddit-mcp": {
      "command": "/usr/local/bin/uv",
      "args": ["run", "main.py"],
      "cwd": "/path/to/reddit-mcp"
    }
  }
}
```

## ⚙️ Configuration (Optional)

For higher rate limits (60 req/min vs 10 req/min), add your Reddit API credentials:

1. Go to [reddit.com/prefs/apps](https://www.reddit.com/prefs/apps)
2. Click **"create another app..."**
3. Select **"script"** type
4. Note your **Client ID** and **Client Secret**
5. Enter them when prompted during MCP installation

## 🛠️ Available Tools

| Tool | Description |
|------|-------------|
| `browse_subreddit` | Browse posts from any subreddit with sorting (hot, new, top, rising) |
| `search_reddit` | Search Reddit for posts matching a query |
| `get_post_details` | Get full post details including threaded comments |
| `user_analysis` | Analyze a Reddit user's activity, karma, and top subreddits |

## 💬 Example Usage

Ask Claude things like:

- *"Browse the top posts from r/programming this week"*
- *"Search Reddit for 'machine learning tutorials'"*
- *"Get details and comments for post ID abc123"*
- *"Analyze the Reddit user spez"*

## 📁 Project Structure

```
reddit-mcp/
├── main.py           # MCP server entry point and tool definitions
├── reddit/
│   └── api.py        # Reddit API client (supports OAuth and anonymous)
├── manifest.json     # MCP bundle manifest for one-click install
├── pyproject.toml    # Python dependencies
└── README.md
```

## 🔒 Rate Limits

| Mode | Rate Limit | Requirements |
|------|------------|--------------|
| Anonymous | 10 req/min | None |
| OAuth | 60 req/min | Client ID + Secret |

## 📄 License

This project is licensed under the [MIT License](LICENSE).

## 🤝 Contributing

Contributions welcome! Please feel free to submit a Pull Request.
