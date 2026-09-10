# hehrmann-agent-skills

Agent skills, an Agent Plugins manifest, and the MCP server declaration for [hehrmann.com](https://hehrmann.com/), the site of Erik Hehrmann, fractional COO for creative agencies of 10 to 75 people.

The site is the source of truth. It serves the same two skills at [hehrmann.com/.well-known/agent-skills/index.json](https://hehrmann.com/.well-known/agent-skills/index.json) with sha256 digests, and this repository mirrors them byte for byte for package managers and directories.

## Install

```bash
npx skills add ehehrmann/hehrmann-agent-skills
```

## What is in here

| Path | What |
|---|---|
| `skills/use-hehrmann-com/SKILL.md` | Read and cite the site: when to use it, Markdown for every page, the MCP server, how to cite |
| `skills/contact-erik-hehrmann/SKILL.md` | Contact Erik on a user's behalf through the screened form or email, without misusing the form |
| `plugin.json` | [Agent Plugins](https://agent-plugins.org/) 1.0.0 manifest |
| `mcp.json` | The remote MCP server at `https://hehrmann.com/mcp` (read-only, no authentication) |
| `AGENTS.md` | Instructions for coding agents working in this repository |

## The MCP server

Streamable HTTP at `https://hehrmann.com/mcp`. Four read-only tools: `list_pages`, `get_page`, `search_site`, `contact_instructions`. No authentication, 100 requests per minute per client, RFC 9457 errors. Everything about it, including the REST endpoints and the versioning policy, is on [hehrmann.com/developers/](https://hehrmann.com/developers/).

## License

MIT. The skills describe a public website; use them freely.
