# mana-bar-status

Community-driven status tracker for AI coding services. Used by [mana.bar](https://github.com/binhonglee/mana-bar) to show outage reports directly in VS Code.

## How it works

1. A [mana.bar](https://github.com/binhonglee/mana-bar) user experiences an AI service outage
2. They click "Report Outage" in the extension, which runs local diagnostics and opens a pre-filled GitHub Issue here
3. Other mana.bar users see the report in their editor with a count of affected users
4. A GitHub Actions cron job probes the affected model every 15 minutes and auto-closes the issue once the model responds

## Tracked Services

| Service | Probe Method |
|---------|-------------|
| **Claude Code** | Anthropic API (minimal "Reply YES" prompt) |
| **Codex** | OpenAI API (minimal "Reply YES" prompt) |

More services may be added in the future.

## Labels

| Label | Purpose |
|-------|---------|
| `outage` | Applied automatically to all outage reports |
| `verified` | Added by maintainers to enable CI probing (anti-spam) |
| `claude-code` | Service label |
| `codex` | Service label |
| `auto-resolved` | Added when CI confirms the model is operational |

## Contributing

If you're experiencing an AI service outage, the easiest way to report it is through the [mana.bar](https://github.com/binhonglee/mana-bar) VS Code extension. You can also manually create an issue using the issue template.

## License

MIT
