# MCP Server Obsidian Omnisearch

A FastMCP-based server that provides Obsidian vault search functionality through a REST API interface.

## Overview

This project implements a search service that allows you to search through Obsidian vault notes programmatically. It uses FastMCP to expose the search functionality as a tool that can be integrated with other services.

## Features

- Search through Obsidian vault notes
- REST API integration
- Returns absolute paths to matching notes
- Easy integration with FastMCP tools

## Prerequisites

- Python 3.x
- Obsidian with Omnisearch plugin installed and running
- FastMCP library
- Active Obsidian vault

## Installation

1. Clone the repository:
```bash
git clone https://github.com/anpigon/mcp-server-obsidian-omnisearch.git
cd mcp-server-obsidian-omnisearch
```

2. Install dependencies:
```bash
uv install
```

## Configuration

Update the `OBSIDIAN_VAULT_PATH` in `server.py` to point to your Obsidian vault location:

```python
OBSIDIAN_VAULT_PATH = "/path/to/your/obsidian/vault"
```

## Usage

### Obsidian Omnisearch API

You need the Obsidian Omnisearch community plugin running: https://publish.obsidian.md/omnisearch/Inject+Omnisearch+results+into+your+search+engine

### Claude Desktop

On MacOS: `~/Library/Application\ Support/Claude/claude_desktop_config.json`

On Windows: `%APPDATA%/Claude/claude_desktop_config.json`

<details>
  <summary>Development/Unpublished Servers Configuration</summary>

```json
{
  "mcpServers": {
    "obsidian-omnisearch": {
      "command": "uv",
      "args": [
        "--directory",
        "<dir_to>/mcp-server-obsidian-omnisearch",
        "run",
        "--with",
        "fastmcp",
        "fastmcp",
        "run",
        "<dir_to>/mcp-server-omnisearch/server.py"
      ]
    }
  }
}
```
</details>

<details>
  <summary>Published Servers Configuration</summary>

```json
{
  "mcpServers": {
    "obsidian-omnisearch": {
      "command": "uvx",
      "args": [
        "mcp-server-obsidian-omnisearch",
        "/path/to/your/obsidian/vault"
      ]
    }
  }
}
```
</details>

## API Reference

### Search Notes
- Function: `obsidian_notes_search(query: str)`
- Description: Searches Obsidian notes and returns absolute paths to matching notes
- Parameters:
  - `query`: Search query string
- Returns: List of absolute paths to matching notes

## Dependencies

- FastMCP
- requests
- urllib

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
