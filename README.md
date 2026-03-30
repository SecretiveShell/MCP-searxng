# MCP-searxng

An MCP server for connecting agentic systems to search systems via [searXNG](https://docs.searxng.org/).

<p align="center">
  <a href="https://glama.ai/mcp/servers/sl2zl8vaz8">
    <img width="380" height="200" src="https://glama.ai/mcp/servers/sl2zl8vaz8/badge" alt="MCP SearxNG Badge"/>
  </a>
</p>

## Tools

Search the web with SearXNG

## Prompts

```python
search(query: str) -> f"Searching for {query} using searXNG"
```

## Hosted deployment

A hosted deployment is available on [Fronteir AI](https://fronteir.ai/mcp/secretiveshell-mcp-searxng).

## Usage

### via uvx

1) configure your client JSON like

```json
{
  "mcpServers": {
    "searxng": {
      "command": "uvx", 
      "args": [
        "mcp-searxng"
      ]
    }
  }
}
```

### via git clone

1) Add the server to claude desktop (the entrypoint is main.py)

Clone the repo and add this JSON to claude desktop

you can run this server with `uvx mcp-searxng`, or use a local copy of the repo

```json
{
  "mcpServers": {
    "searxng": {
      "command": "uv", 
      "args": [
        "--project",
        "/absoloute/path/to/MCP-searxng/",
        "run",
        "/absoloute/path/to/MCP-searxng/mcp-searxng/main.py"
      ]
    }
  }
}
```

you will need to change the paths to match your environment

### Custom SearXNG URL

2) set the environment variable `SEARXNG_URL` to the URL of the searxng server (default is `http://localhost:8080`)

3) run your MCP client and you should be able to search the web with searxng

Note: if you are using claude desktop make sure to kill the process (task manager or equivalent) before running the server again
