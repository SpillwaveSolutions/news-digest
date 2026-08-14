# Typed edges — News Digest

Direction matters. Packs follow outbound edges by default.

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

Unknown `rel` values are treated as `info` by validation. Do not invent new names in this plugin.
