---
name: nwd-init
description: Scaffold the News Digest catalogs in a shared second-brain bundle.
---

# nwd-init

Create the catalogs this plugin owns inside a shared knowledge root.

## Process

1. Confirm target (default `knowledge/`).
2. Run:

```bash
python3 "${CLAUDE_PLUGIN_ROOT}/scripts/nwd_common.py" init-bundle \
  --bundle knowledge \
  --title "News Digest" \
  --catalogs "news-items,sources,digests,topics,trends"
```

3. Point the user at `sample-knowledge/` for a fictional demo.

## Done when

- `knowledge/index.md` exists
- Each owned catalog has `index.md`
