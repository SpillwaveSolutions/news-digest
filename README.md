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

### ContentPack suite

- [second-brain-core](https://github.com/SpillwaveSolutions/second-brain-core)
- [executive-coordination](https://github.com/SpillwaveSolutions/executive-coordination)
- [account-management](https://github.com/SpillwaveSolutions/account-management)
- [sales-pipeline](https://github.com/SpillwaveSolutions/sales-pipeline)
- [executive-job-search](https://github.com/SpillwaveSolutions/executive-job-search)
- [consulting-leads](https://github.com/SpillwaveSolutions/consulting-leads)
- [content-media](https://github.com/SpillwaveSolutions/content-media)
- [news-digest](https://github.com/SpillwaveSolutions/news-digest)
- [gtm-positioning](https://github.com/SpillwaveSolutions/gtm-positioning)
- [second-brain-marketplace](https://github.com/SpillwaveSolutions/second-brain-marketplace)
- [second-brain-starter](https://github.com/SpillwaveSolutions/second-brain-starter)

### Foundation

- [okf-plugin](https://github.com/SpillwaveSolutions/okf-plugin) — Open Knowledge Format graph engine
- [project-knowledge-capture](https://github.com/SpillwaveSolutions/project-knowledge-capture) — Project Knowledge Capture. The why second brain.
- [system-architecture-capture](https://github.com/SpillwaveSolutions/system-architecture-capture) — System Architecture Capture. The what-is-running second brain.
- [data-engineering-knowledge-capture](https://github.com/SpillwaveSolutions/data-engineering-knowledge-capture) — Data Engineering Knowledge Capture. The data-plane second brain.
- [wiki_ticket_sdd](https://github.com/SpillwaveSolutions/wiki_ticket_sdd) — WikiTicket SDD. Visible work log. Append-only ULID JSONL plus fold.
- [okf-agent-graph](https://github.com/SpillwaveSolutions/okf-agent-graph) — AGER. Orchestrator / Doer / Judge / Synthesizer.


## Onboarding

Grok Bot and other host agents should start at [docs/ONBOARDING.md](docs/ONBOARDING.md). That file is the history of the LLM-wiki effort, the destination state (Grok Bots and local agents sharing one git-native second brain), and the canonical public repo list.

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
