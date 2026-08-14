---
name: nwd-validate
description: Validate News Digest concepts: required fields, types, and in-bundle links.
---

# nwd-validate

```bash
python3 "${CLAUDE_PLUGIN_ROOT}/scripts/nwd_common.py" validate --bundle knowledge
```

Fail on missing `type`/`title` or broken absolute links.
