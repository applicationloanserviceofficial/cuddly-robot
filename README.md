# cuddly-robot

## Claude Code plugins

This repository enables the [`commit-commands`](https://github.com/anthropics/claude-plugins-official)
plugin from Anthropic's official marketplace at **project scope**, via the committed
[`.claude/settings.json`](.claude/settings.json):

```json
{
  "extraKnownMarketplaces": {
    "claude-plugins-official": {
      "source": { "source": "github", "repo": "anthropics/claude-plugins-official" }
    }
  },
  "enabledPlugins": {
    "commit-commands@claude-plugins-official": true
  }
}
```

### What this gives you

The `commit-commands` plugin adds slash commands for creating well-formed git
commits from within a Claude Code session.

### Activating it on your machine

Project settings **enable** the plugin for everyone who clones this repo, but each
collaborator still needs it fetched locally the first time:

- **Terminal / desktop / VS Code:** open this repo in Claude Code and accept the
  workspace trust prompt. If the `/plugin` **Errors** tab shows
  *"enabled in project settings but isn't installed here"*, install it once with:

  ```bash
  claude plugin install commit-commands@claude-plugins-official
  ```

  (Claude Code adds the `claude-plugins-official` marketplace automatically on first
  interactive start; the `extraKnownMarketplaces` entry above declares the source
  explicitly as a fallback.)

- **Cloud sessions (claude.ai/code):** plugins come from your synced claude.ai
  account rather than from this file, so enable `commit-commands` in your account's
  plugin settings there.

For details, see the Claude Code docs:
<https://code.claude.com/docs/en/plugins>.
