---
name: deep-agents-news-digest
description: Bind LangChain Deep Agents to the news-digest ContentPack. Isolation, identity, deterministic writes.
---

# Deep Agents / AI News Journalist

Follow `docs/LANG_CHAIN_DEEP_AGENTS.md`.

1. Identity: `deep-agents/news-digest`
2. Load this pack with `skills=["./path/to/news-digest/skills/"]` or SkillsMiddleware.
3. Open an isolation session (`scripts/brain_session.py open --host deep-agents`) unless `SECOND_BRAIN_ROOT` already points at a session worktree.
4. Pack 2 hops, then write owned types only via `scripts/nwd_common.py write --author`.
5. Close the session to PR. Report path + SHA.
6. Never document a private remote. Never write raw Markdown into the tree.
