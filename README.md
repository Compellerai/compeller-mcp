# Compeller MCP

Public documentation and metadata for the hosted **Compeller MCP** server.

Compeller turns music into performance-ready visuals. Agents can discover styles and pricing, search for music, create and track Compels, start renders, retrieve finished videos, and register signed webhooks for completion events.

> This repository contains public connector documentation and metadata only. The production Compeller application source code is not published here.

## Remote MCP endpoint

```text
https://compeller.ai/api/mcp
```

- **Namespace:** `ai.compeller/compel`
- **Server:** `compeller-mcp`
- **Version:** `0.5.0`
- **Transport:** Streamable HTTP JSON-RPC over HTTPS
- **Official MCP Registry:** <https://registry.modelcontextprotocol.io/v0.1/servers?search=ai.compeller%2Fcompel>
- **Smithery:** <https://smithery.ai/servers/info-nijd/compeller>

## Quick config

Most MCP clients that support remote Streamable HTTP servers can use:

```json
{
  "mcpServers": {
    "compeller": {
      "url": "https://compeller.ai/api/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_COMPELLER_API_TOKEN"
      }
    }
  }
}
```

If your MCP client stores raw token values without the `Bearer ` prefix, use the alternate header:

```json
{
  "mcpServers": {
    "compeller": {
      "url": "https://compeller.ai/api/mcp",
      "headers": {
        "X-API-Token": "YOUR_COMPELLER_API_TOKEN"
      }
    }
  }
}
```

Discovery works without authentication. Generation, account, media, rendering, and webhook tools require a Compeller API token.

## Public docs and discovery

- MCP docs: <https://compeller.ai/api/mcp/docs.md>
- Agent manifest: <https://compeller.ai/agents.json>
- LLM guide: <https://compeller.ai/llms.txt>
- OpenAPI: <https://compeller.ai/api/v1/openapi.yaml>
- Health: <https://compeller.ai/api/v1/health>

## Tool surface

Compeller currently exposes 20 MCP tools:

### Discovery

- `get_capabilities`
- `get_pricing`
- `list_styles`
- `search_music`

### Media and generation

- `upload_media`
- `search_media`
- `create_compel_from_music`
- `create_compel`
- `get_compel`
- `start_render`
- `list_compels`
- `search_compels`
- `list_renderings`
- `get_rendering`

### Webhooks

- `register_webhook`
- `list_webhooks`
- `update_webhook`
- `delete_webhook`
- `test_webhook_delivery`
- `rotate_webhook_secret`

Webhook deliveries are signed with `X-Compeller-Signature: sha256=<hex>` over the raw request body. Secrets are returned exactly once on registration or rotation.

## Example prompts

- “Search for Midnight City by M83 and create a cinematic Compeller visual.”
- “Show me available Compeller visual styles.”
- “Check the status of Compel 12345.”
- “Start the render for this READY Compel.”
- “Register a webhook for completed/failed Compeller events.”

## Directory listing copy

Short description:

```text
Create AI music videos and audio-reactive visuals from songs through MCP.
```

Longer description:

```text
Compeller is a creator media pipeline for music. The MCP server lets agents discover styles and pricing, search music, create and track Compels, upload media, start renders, retrieve renderings, and register signed webhooks for completion events. Completed renderings can also be loaded into REACT, Compeller's desktop app for live audio-reactive shows.
```

Suggested tags:

```text
AI, Music, Video Generation, Audio Reactive, Creative Tools, MCP, Remote MCP, Generative Art, Creator Tools, Entertainment
```

## License

The documentation and metadata in this repository are published under the MIT License.
