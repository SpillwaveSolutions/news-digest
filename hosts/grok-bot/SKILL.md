---
name: grok-bot-news-digest
description: Bind a Grok Bot agent to the news-digest ContentPack. Isolation, identity, deterministic writes.
---

# Grok Bot / AI News Journalist

Read `docs/ONBOARDING.md` first, then follow `docs/GROK_BOT.md`.

1. Identity: `grok-bot/news-digest`
2. Open an isolation session before writes (`scripts/brain_session.py open`) unless the human already pointed `SECOND_BRAIN_ROOT` at a session worktree.
3. Pack 2 hops, then write owned types only via `scripts/nwd_common.py write --author`.
4. Close the session to PR. Report path + SHA.
5. Never document a private remote. Never write raw Markdown into the tree.
