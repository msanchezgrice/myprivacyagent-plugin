# My Privacy Agent plugin for Grok Bot and Cursor

Get a home address, phone number or email off people-search and data-broker sites, from chat. The plugin connects your
agent to [My Privacy Agent](https://myprivacyagent.com)'s public MCP server and adds a skill that knows the rules.

- `@my-privacy-agent how do I remove my listing from Spokeo?`: verified step-by-step opt-out guide, with the link.
- `@my-privacy-agent what's the removal route for fastpeoplesearch.com, and which sister sites does one request cover?`
- `@my-privacy-agent do removed listings come back?`: answers from the published privacy library, cited.

The tools are read-only: they never look anyone up and hold no personal data. To check your own exposure, the agent
hands you to a free, private check at myprivacyagent.com. Nothing is filed without your approval there.

## Install

- **Grok Bot:** Plugins → search "My Privacy Agent" → Add. Or ask the bot: *Add a custom MCP server called
  my-privacy-agent at https://myprivacyagent.com/api/mcp*.
- **Cursor:** install from the Cursor Marketplace, or add `mcp.json` from this repo to your MCP settings.

## What's inside

| Path | What |
|---|---|
| `.cursor-plugin/plugin.json` | Plugin manifest |
| `mcp.json` | Remote MCP server: `https://myprivacyagent.com/api/mcp` (Streamable HTTP, public tools need no key) |
| `skills/my-privacy-agent/` | The skill: workflow and rules |
| `assets/logo.svg` | Logo |

Public tools: `get_opt_out_instructions`, `list_opt_out_guides`, `get_removal_route`, `search_privacy_library`,
`get_service_overview`. Account tools (OAuth) aren't open yet.
Docs: https://myprivacyagent.com/llms.txt · Grok guide: https://myprivacyagent.com/for/grok

Grok Bot is a product of xAI; My Privacy Agent is not affiliated with or endorsed by xAI.

MIT License.
