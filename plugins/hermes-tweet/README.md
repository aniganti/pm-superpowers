# Hermes Tweet

Hermes Tweet helps product managers use Hermes Agent for X/Twitter product signal research, launch monitoring, competitive listening, support triage, creator research, and approved social actions.

This Claude Code plugin contains workflow documentation only. It does not install or expose `tweet_explore`, `tweet_read`, or `tweet_action`. Live work requires a separate Hermes Agent session with the native Hermes Tweet plugin enabled. Stop before live research if the required tool is unavailable.

Use it alongside PM Superpowers workflows when strategy work needs live social evidence:

- Feed competitor chatter into `competitive-landscape`.
- Monitor launch feedback before a `pre-mortem`.
- Turn public trend and post analysis into `decision-log` evidence.
- Validate market demand signals before `prioritization`.

## Installation

After adding this marketplace, install the workflow guide:

```bash
claude plugin install hermes-tweet
```

This command installs guidance only. It does not add Hermes tools to Claude Code.

Install and enable the native Hermes Agent plugin in the Hermes runtime:

```bash
hermes plugins install Xquik-dev/hermes-tweet --enable
```

If the Hermes runtime does not install the Python package automatically, use the PyPI fallback:

```bash
uv pip install --python ~/.hermes/hermes-agent/venv/bin/python hermes-tweet
```

## Runtime Setup

| Variable | Required | Purpose |
|---|---:|---|
| `XQUIK_API_KEY` | Yes for live reads and actions | Enables configured Xquik API access where Hermes tools execute. |
| `HERMES_TWEET_ENABLE_ACTIONS=true` | Only for actions | Enables posting, replies, likes, follows, DMs, monitors, and other account-changing workflows. |

Keep secrets in the Hermes runtime environment or `~/.hermes/.env`. Do not paste keys into chat, prompts, logs, issue text, or repository files.

Xquik is a third-party paid API service. An account, API key, and sufficient plan or credits may be required. PM Superpowers does not provide or operate the runtime.

## Skill

| Skill | What it does |
|---|---|
| `social-signal-intelligence` | Guides X/Twitter product research through `tweet_explore`, `tweet_read`, and gated `tweet_action` workflows. |

## Safety Defaults

- Start with `tweet_explore` to find the endpoint or capability.
- Use `tweet_read` for public read-only data after the endpoint is known.
- Use `tweet_action` only after the exact endpoint, method, payload, and reason are approved.
- Do not invent handles, post URLs, metrics, trend strength, or account state.
- Never ask for or reveal API keys, passwords, cookies, or TOTP secrets.
- Stop rather than invent live results when a required Hermes tool is unavailable.

Xquik is an independent third-party service. Not affiliated with X Corp. "Twitter" and "X" are trademarks of X Corp.

## License

MIT. See [LICENSE](LICENSE).
