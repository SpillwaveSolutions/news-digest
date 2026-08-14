# CLAUDE.md — News Digest

You are operating the **News Digest** ContentPack plugin.

## When to use

Use this plugin when the user is working on: NewsItem, Source, Digest, SignalStrength, Topic, Trend, CompanyMention, ProductLaunch.

## Write path

1. Identify the noun type.
2. Check `schemas/okf-concepts/` for required fields.
3. Call `python3 ${CLAUDE_PLUGIN_ROOT}/scripts/nwd_common.py write ...`
4. Link with typed `rel` values from `docs/typed-edges.md`.
5. Offer `/nwd-pack` if the user needs a session-sized subgraph.

## Do not

- Dump the whole knowledge tree into context. Use packs.
- Write types owned by another plugin.
- Publish, send email, or apply to jobs unless the user explicitly confirms.
