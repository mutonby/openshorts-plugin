# Installing the OpenShorts MCP server

OpenShorts is a hosted remote MCP server. There is nothing to clone, build or
run locally: you only add the server URL to the MCP client.

- URL: `https://mcp.openshorts.app/mcp`
- Transport: Streamable HTTP
- Auth: OAuth 2.1 with dynamic client registration (no key to copy)

## Cline

Add this entry to `cline_mcp_settings.json` (Cline → MCP Servers → Configure):

```json
{
  "mcpServers": {
    "openshorts": {
      "type": "streamableHttp",
      "url": "https://mcp.openshorts.app/mcp",
      "disabled": false
    }
  }
}
```

On the first tool call Cline opens a browser tab: the user signs in at
openshorts.app (or creates a free account) and approves the access.

If the client cannot complete OAuth, use an API key instead. The user creates
one at https://www.openshorts.app/#/account (API keys card) and it goes in a
header:

```json
{
  "mcpServers": {
    "openshorts": {
      "type": "streamableHttp",
      "url": "https://mcp.openshorts.app/mcp",
      "headers": { "Authorization": "Bearer <OPENSHORTS_API_KEY>" },
      "disabled": false
    }
  }
}
```

Never invent a key: ask the user to paste theirs.

## Check that it works

Call `get_quota`. It returns the user's plan and remaining minutes. New
accounts get free minutes.

## Tools

`process_video`, `get_job_status`, `list_clips`, `add_subtitles`,
`recut_clip`, `publish_clip`, `create_upload`, `get_quota`.

Typical flow: `process_video` with a YouTube URL, poll `get_job_status` until
it is completed, then `list_clips`. Processing uses minutes from the user's
plan, and the user must own the video or hold the rights to it.
`publish_clip` only posts to the social accounts the user connected at
openshorts.app, and only when the user asks for it.
