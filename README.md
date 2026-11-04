# OpenAccountants for Hermes

The OpenAccountants tax library as a portable Agent Plugin (agent-plugins.org
v1), which Hermes loads natively: 2,100+ jurisdiction tax skills (countries,
US states, cross-border, verticals) register as plugin skills, and the hosted
OpenAccountants connector ships as the package's MCP server.

This repository mirrors [`openaccountants/openaccountants`](https://github.com/openaccountants/openaccountants)
in real time. The `skills/` tree is generated content built from that repo's
`agent-skills/` by its sync; never edit it here.

## What installs

- `skills/` — the full library, one folder per skill with a `SKILL.md`.
- `mcp.json` — the connector at https://www.openaccountants.com/api/mcp
  (streamable-http). Hermes registers it as `openaccountants` when the plugin
  is enabled.

Skills register read-only as `openaccountants:<slug>`: listed by `skills_list`
and readable by `skill_view()`, not copied into `~/.hermes/skills/`.

## Disclosure

- Network calls: the OpenAccountants connector (hosted at
  https://www.openaccountants.com/api/mcp) when the plugin is enabled.
- Shell commands: none. Writes: none at runtime. Credentials: none required.

## Install (Hermes)

```bash
hermes plugins install lEWFkRAD/openaccountants-hermes-plugin
hermes plugins enable openaccountants
```

Or by hand: copy this folder to `~/.hermes/plugins/openaccountants/` (into your
active profile's `plugins/` dir if you use profiles), then
`hermes plugins enable openaccountants`.
