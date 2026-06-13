---
name: social-signal-intelligence
description: >-
  Use when a product manager needs X/Twitter market signals, launch feedback,
  competitor chatter, creator research, support triage, trend analysis, or an
  approved social action through Hermes Tweet.
argument-hint: "<product, competitor, launch, trend, or social workflow>"
---

# Social Signal Intelligence

## Purpose

Turn X/Twitter evidence into product strategy inputs. Use Hermes Tweet to research public posts, profiles, trends, and product conversations, then summarize the signal in a format PMs can feed into strategy, competitive analysis, prioritization, pre-mortems, or decision logs.

## Setup Checks

1. Inspect the tools available in the current session. Never infer availability from this Skill.
2. Require `tweet_explore` before starting any live workflow.
3. Require `tweet_read` before live research.
4. Require `tweet_action` and explicit approval before account-changing work.
5. Keep `HERMES_TWEET_ENABLE_ACTIONS` unset or false for read-only strategy work.

## Runtime Boundary

This Skill provides instructions only. It does not install or expose Hermes tools in Claude Code.

If a required tool is unavailable, stop before live work. Explain that the user must run the workflow in Hermes Agent with the native Hermes Tweet plugin enabled. Do not invent results, silently substitute another tool, or imply that setup succeeded. You may still organize evidence the user already supplied.

## Instructions

1. Classify the request:
   - Discovery: the user asks what X/Twitter data or actions are available.
   - Research: the user needs public posts, trends, accounts, or market signal evidence.
   - Action: the user asks to post, reply, like, follow, DM, create monitors, run webhooks, start extraction jobs, upload media, or run giveaway actions.
2. Apply the runtime boundary. Stop if the tool required for this request is unavailable.
3. Use `tweet_explore` first to find the endpoint, capability, or route.
4. Use `tweet_read` only for catalog-listed public read-only endpoints.
5. Use `tweet_action` only after the user approves the exact endpoint, method, payload, and reason.
6. Cite returned public URLs and timestamps. Mark missing links as "URL not verified".
7. Connect findings to the relevant PM workflow:
   - `competitive-landscape` for competitor positioning.
   - `strategy` for market and user context.
   - `pre-mortem` for launch risks.
   - `decision-log` for evidence behind a product call.
   - `prioritization` for demand and urgency signals.

## Output Format

```text
## Social Signal Brief
- Product or question:
- Query and window:
- Top signals:
- Evidence:
- PM implication:
- Risk or caveat:
- Recommended next step:
```

## Safety Rules

- Never ask for or reveal API keys, passwords, cookies, or TOTP secrets.
- Never place credentials in tool arguments or PM artifacts.
- Never invent handles, post URLs, metrics, account state, or trend strength.
- Never claim live research ran when a required Hermes tool is unavailable.
- Do not guess endpoint paths. Use the catalog returned by `tweet_explore`.
- Do not retry writes through alternate routes after policy, auth, or account-state errors.
- Summarize any account-changing action before calling `tweet_action`.

## Install Reference

```bash
hermes plugins install Xquik-dev/hermes-tweet --enable
uv pip install --python ~/.hermes/hermes-agent/venv/bin/python hermes-tweet
```
