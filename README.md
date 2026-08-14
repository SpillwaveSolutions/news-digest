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

## License

MIT. Copyright 2026 Rick Hightower / contributors.
