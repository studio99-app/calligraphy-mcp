# Calligraphy Maker by Studio99 (MCP server)

A hosted [Model Context Protocol](https://modelcontextprotocol.io) server that turns exact Hindi, Marathi, Gujarati and English text into calligraphy artwork. Ask your AI assistant for a word, name or phrase, such as a wedding title like शुभ विवाह, a festival greeting or a logo word, and get PNG previews plus editable SVG.

Text is rendered from real calligraphy fonts, so conjuncts and matras come out exactly as typed.

- **Server URL:** `https://mcp.studio99.app/api/mcp`
- **Transport:** Streamable HTTP
- **Sign-in:** OAuth 2.1 with dynamic client registration. Your client opens the Studio99 sign-in page; a free account is created during sign-in if you don't have one.
- **Registry name:** `app.studio99/calligraphy`

This repository holds documentation only. The server is hosted and run by Studio99; there is nothing to install or run locally.

## Tools

| Tool | What it does |
|---|---|
| `list_styles` | Lists calligraphy styles by language, mood or use case (read-only) |
| `generate_calligraphy` | Renders text as calligraphy; returns PNG previews and SVG |
| `create_studio99_project` | Opens a result as an editable project in the Prishora editor on studio99.app |

## Configure

### VS Code (GitHub Copilot)

Add the server to `.vscode/mcp.json` in your workspace, or to your user `mcp.json` (Command Palette → **MCP: Open User Configuration**):

```json
{
  "servers": {
    "studio99": {
      "type": "http",
      "url": "https://mcp.studio99.app/api/mcp"
    }
  }
}
```

Start the server from the `mcp.json` editor or the Extensions view. VS Code asks you to sign in with your Studio99 account the first time. Then use Copilot Chat in **Agent** mode.

### Claude

Settings → Connectors → **Add custom connector**, then paste the server URL. In Claude Code:

```bash
claude mcp add --transport http studio99 https://mcp.studio99.app/api/mcp
```

### ChatGPT

Settings → Connectors → Developer mode, then add the server URL.

### Cursor

Add the server URL as a remote MCP server in `mcp.json`:

```json
{
  "mcpServers": {
    "studio99": {
      "url": "https://mcp.studio99.app/api/mcp"
    }
  }
}
```

### Gemini CLI

```bash
gemini extensions install https://github.com/studio99-app/gemini-extension
```

Then run `/mcp auth studio99` once inside Gemini CLI.

Step-by-step guides for each assistant: https://studio99.app/calligraphymaker/mcp

## Use

Ask in plain language, for example:

- "Create calligraphy of शुभ विवाह in Hindi"
- "Make a Gujarati calligraphy for શુભ લગ્ન in an elegant style"
- "Show me Marathi calligraphy styles for a festival greeting"
- "Write 'Happy Diwali' in English calligraphy, then open it in the editor"

Free-font results include the full PNG and SVG; PRO-font results show a preview on the free plan.

## Plans

Free plan: 20 generations a month. More generations and all PRO fonts come with Studio99 One. Plans and pricing: https://studio99.app/calligraphymaker/mcp

## Links

- Documentation: https://studio99.app/calligraphymaker/mcp
- AI integration guide: https://studio99.app/developers/ai
- Service status: https://studio99.betteruptime.com
- Privacy: https://studio99.app/privacy · Terms: https://studio99.app/terms
- Support: reach@studio99.app

## Licence

The files in this repository are MIT licensed. The server is closed source. The calligraphy fonts and the rendered artwork are covered by the [Studio99 terms](https://studio99.app/terms), not by the MIT licence.

Studio99 is a product of ArtoMania Studio Pvt Ltd, Pune, India.
