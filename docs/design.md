# Design — News Digest

## Problem

Session memory evaporates. This plugin gives one job function a typed, git-native vocabulary so agents and local jobs share a second brain.

## Rules

1. Git-native Markdown + YAML
2. Deterministic write boundary
3. Progressive disclosure via ContextPacks
4. No hard-coded real-world client names in samples
5. Dual-host plugin packaging

## Nouns

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
