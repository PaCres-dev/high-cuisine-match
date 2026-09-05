# Claude Code configuration

This directory holds the **project-scoped** Claude Code configuration for
`high-cuisine-match`. It is committed so every collaborator gets the same setup.

## Enabled plugin: `mattpocock-skills`

[`mattpocock-skills`](https://github.com/mattpocock/skills) is Matt Pocock's set of
agent skills for real engineering work. It ships from Anthropic's official
marketplace (`claude-plugins-official`), which Claude Code registers automatically —
`settings.json` also declares it explicitly under `extraKnownMarketplaces` so the
setup still resolves in non-interactive and cloud sessions.

`settings.json` enables it for the project:

```json
{
  "enabledPlugins": {
    "mattpocock-skills@claude-plugins-official": true
  }
}
```

### One-time step per developer

Enabling a plugin in project settings declares the intent; because the plugin is
fetched from an external source, each developer still installs it once locally
(Claude Code will tell you if it isn't installed yet):

```bash
claude plugin install mattpocock-skills@claude-plugins-official
```

Or from inside a session:

```
/plugin install mattpocock-skills@claude-plugins-official
```

Then run `/reload-plugins` if the install summary asks you to.

Verify with:

```bash
claude plugin list
```

### What you get

Skills are namespaced under the plugin name, e.g. `/mattpocock-skills:tdd`.

**Engineering:** `ask-matt`, `codebase-design`, `code-review`, `diagnosing-bugs`,
`domain-modeling`, `grill-with-docs`, `implement`, `improve-codebase-architecture`,
`prototype`, `research`, `resolving-merge-conflicts`,
`setup-matt-pocock-skills`, `tdd`, `to-spec`, `to-tickets`, `triage`, `wayfinder`,
`wizard`

**Productivity:** `grill-me`, `grilling`, `handoff`, `teach`, `to-questionnaire`,
`wait-what`, `writing-for-agents`

Run `/mattpocock-skills:setup-matt-pocock-skills` once to let the skills tailor
themselves to this repository.

> Note: don't also run `npx skills@latest add mattpocock/skills` — that copies
> editable versions of the same skills into the repo and you'd end up with each
> skill twice. Pick the plugin (managed, auto-updating) or the copies, not both.

## Local overrides

Personal, uncommitted settings go in `.claude/settings.local.json`
(git-ignored). To opt out of the plugin for yourself only:

```json
{
  "enabledPlugins": {
    "mattpocock-skills@claude-plugins-official": false
  }
}
```

## References

- [Discover and install plugins](https://code.claude.com/docs/en/discover-plugins)
- [Settings reference](https://code.claude.com/docs/en/settings-reference)
