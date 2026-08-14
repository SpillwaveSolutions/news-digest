---
name: nwd-capture
description: Capture a News Digest noun into the shared second brain via the deterministic write helper.
---

# nwd-capture

## Process

1. Identify the noun type from the allowed list (see README).
2. Collect title, status, author identity, and optional typed links.
3. Write with the helper — do not hand-author frontmatter unless the user insists:

```bash
python3 "${CLAUDE_PLUGIN_ROOT}/scripts/nwd_common.py" write \
  --bundle knowledge \
  --type NewsItem \
  --folder news-items \
  --title "Example NewsItem" \
  --author "Grok Bot: News Digest" \
  --tags "nwd"
```

4. Add typed links in a follow-up edit if needed (`rel` values from `docs/typed-edges.md`).
5. Validate.

Allowed types: NewsItem, Source, Digest, SignalStrength, Topic, Trend, CompanyMention, ProductLaunch, ResearchPaper, OpinionPiece, FollowUpCandidate, SourceCredibility, TimestampedEvent.
