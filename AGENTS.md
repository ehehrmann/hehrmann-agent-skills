# AGENTS.md

Instructions for AI coding agents working in this repository.

## What this repository is

The public mirror of the agent-facing documents that hehrmann.com serves: two Agent Skills, an Agent Plugins manifest (`plugin.json`), and the declaration of the site's remote MCP server (`mcp.json`). The website is the source of truth. It publishes the same skills at https://hehrmann.com/.well-known/agent-skills/index.json with sha256 digests; this repository exists so package managers and directories (the `skills` CLI, agent-plugins.org clients, MCP registries) have something to point at.

## Layout

- `skills/use-hehrmann-com/SKILL.md`: how to read and cite the site.
- `skills/contact-erik-hehrmann/SKILL.md`: how to contact Erik on a user's behalf.
- `plugin.json`: Agent Plugins 1.0.0 manifest. Skills are discovered from `skills/`, the MCP server from `mcp.json`.
- `mcp.json`: the remote server, `streamable-http` at `https://hehrmann.com/mcp`.

## Rules

1. Do not edit the `SKILL.md` files here. They are byte-for-byte copies of the files served under https://hehrmann.com/.well-known/agent-skills/, and the digests in the served index must keep matching. If a copy differs from the served file, the served file wins; replace the copy.
2. Keep the skill names as they are. Directories and the `name` field in each frontmatter must stay identical to the served index.
3. Never add a tool, script, or instruction that writes to the site or submits its contact form. The MCP server is read-only and unauthenticated on purpose; the form is submitted by a person.
4. Never add credentials of any kind. Nothing on hehrmann.com takes a token, so there is nothing to store.
5. Prose in this repository follows the site's house style: no em dashes, plain sentences, lead with the point.

## Verify

```bash
# both skills are discoverable
npx skills add ehehrmann/hehrmann-agent-skills --list

# the MCP server answers with four tools
curl -s -X POST https://hehrmann.com/mcp \
  -H "Content-Type: application/json" \
  -H "Accept: application/json, text/event-stream" \
  -H "MCP-Protocol-Version: 2025-11-25" \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list"}'

# the copies match the served files
for s in use-hehrmann-com contact-erik-hehrmann; do
  curl -s "https://hehrmann.com/.well-known/agent-skills/$s/SKILL.md" | cmp - "skills/$s/SKILL.md" && echo "$s ok"
done
```

## Contact

erik@hehrmann.com. Developer documentation for the site: https://hehrmann.com/developers/
