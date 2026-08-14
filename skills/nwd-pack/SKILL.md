---
name: nwd-pack
description: Build a bounded ContextPack from a News Digest root concept (default 2 hops, 20 nodes).
---

# nwd-pack

## Process

```bash
python3 "${CLAUDE_PLUGIN_ROOT}/scripts/nwd_common.py" pack \
  --bundle knowledge \
  --root "/news-items/example.md" \
  --hops 2 \
  --max-nodes 20
```

Use `--hops 1` for a tiny pack. Outbound edges only. Do not dump the whole tree.
