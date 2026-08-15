# News Digest

News digest ContentPack: news items, sources, scheduled digests, signal strength, trends, and follow-up candidates for long-form.

MIT. Dual-host: **Claude Code**, **Grok Build**, and **Codex** (Agent Skill Standard). Writes OKF Markdown + YAML into a shared second-brain bundle so other agents and local jobs can read the same graph.

## Install

```bash
# Claude Code
/plugin marketplace add SpillwaveSolutions/news-digest
/plugin install news-digest@SpillwaveSolutions

# Skilz CLI
skilz install SpillwaveSolutions/news-digest
```

Point the plugin at a shared knowledge root (default `knowledge/`). All sibling ContentPack plugins write into the same tree.

## Skills

| Skill | What it does |
|-------|----------------|
| `/nwd-init` | Scaffold the catalogs this plugin owns |
| `/nwd-capture` | Capture a noun into the shared second brain (deterministic write) |
| `/nwd-pack` | Build a bounded ContextPack from a root concept |
| `/nwd-validate` | Validate frontmatter, types, and links |
| `/nwd-session` | Open or close an isolated write session (worktree + PR) |
| `/nwd-doctor` | Health check of the bundle this plugin owns |

## Nouns this plugin may write

| Type | Meaning |
|------|---------|
| `NewsItem` | Single news item |
| `Source` | Publication or feed |
| `Digest` | Scheduled rollup (morning / afternoon) |
| `SignalStrength` | High / medium / low importance |
| `Topic` | Normalized topic tag |
| `Trend` | Multi-item pattern |
| `CompanyMention` | Company referenced in news |
| `ProductLaunch` | Launch event |
| `ResearchPaper` | Paper worth tracking |
| `OpinionPiece` | Commentary item |
| `FollowUpCandidate` | Item that should become an article |
| `SourceCredibility` | Trust note on a source |
| `TimestampedEvent` | Dated industry event |

## Relationships

| `rel` | Meaning |
|-------|---------|
| `sourced_from` | Item came from a source |
| `included_in` | Item is in a digest |
| `about_topic` | Tagged to a topic |
| `signals` | Supports a trend |
| `mentions` | Mentions a company or product |
| `follow_up_as` | Should become an article |
| `related_to` | Related items |
| `originates_from` | Provenance |

## Catalogs

- `news-items/`
- `sources/`
- `digests/`
- `topics/`
- `trends/`

## Deterministic write boundary

The model proposes. Schema-enforced scripts commit:

```bash
python3 scripts/nwd_common.py write \
  --bundle knowledge \
  --type NewsItem \
  --folder news-items \
  --title "Example" \
  --author "Grok Bot: News Digest"
```

Never invent `rel` values. Never write types owned by another plugin.



## Related plugins

- [second-brain-core](https://github.com/SpillwaveSolutions/second-brain-core) — shared pack engine and typed-edge conventions
- [project-knowledge-capture](https://github.com/SpillwaveSolutions/project-knowledge-capture) — the “why” second brain
- [system-architecture-capture](https://github.com/SpillwaveSolutions/system-architecture-capture) — the “what is running” second brain
- [wiki_ticket_sdd](https://github.com/SpillwaveSolutions/wiki_ticket_sdd) — visible work log

## Multi-host

Works with Claude Code, Grok Build, Codex, Agent Plugins 1.0 clients, Grok Bot, and LangChain Deep Agents.

| Host | How to load |
|------|-------------|
| Claude Code | marketplace + plugin install |
| Grok Build | zero-config Claude plugin |
| Codex | Agent Skills / `hooks/hooks.json` |
| Agent Plugins clients | root `plugin.json` + `skills/` |
| Grok Bot | [docs/GROK_BOT.md](docs/GROK_BOT.md) |
| LangChain Deep Agents | [docs/LANG_CHAIN_DEEP_AGENTS.md](docs/LANG_CHAIN_DEEP_AGENTS.md) |

Write isolation (worktree + PR) lives in second-brain-core: [docs/ISOLATION.md](https://github.com/SpillwaveSolutions/second-brain-core/blob/main/docs/ISOLATION.md). Point `SECOND_BRAIN_ROOT` at the session bundle. Never hard-code a private remote.

Eight job-function plugins plus core. Knowledge root is always a local path or env the human already owns.

## License

MIT. Copyright 2026 Rick Hightower / contributors.
