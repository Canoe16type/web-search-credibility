# Web Search Credibility · Agent Skill

A platform-agnostic skill for high-credibility web research.

It defines a repeatable workflow: when to search, how to choose authoritative sources, how to cross-check claims, how to read the original page instead of snippets, how to handle conflicting sources, and how to cite what was actually used.

It does not depend on a specific search vendor, chat platform, or Markdown dialect. Any agent runtime with web search and/or page-fetch capabilities can use it.

## When to use

- Product/API docs, versions, pricing, parameters
- Policies, standards, regulations, announcements
- Company and financial information
- Official settings for games, anime, and fictional works
- Fact-checking a link or a claim
- When an agent is about to answer a verifiable fact from memory

## Principles

- **Official and primary sources first**
- **Cross-check consequential claims**; label single-source claims
- **Read the page, not just the snippet**
- **Separate fact, opinion, and inference**
- **Surface conflicts instead of smoothing them over**
- **Cite what was used**
- **Do not search just to look thorough**

## Files

```text
SKILL.md                                 Chinese skill
SKILL.en.md                              English skill
README.md                                Chinese README
README.en.md                             English README
references/authoritative-sources.md      Chinese reference
references/authoritative-sources.en.md   English reference
examples/citation-styles.md              Chinese examples
examples/citation-styles.en.md           English examples
LICENSE                                  MIT
```

## Install

Download one of the release packages; each contains a standard `SKILL.md` at its root:

- `web-search-credibility-zh-v1.0.0.zip`: Chinese
- `web-search-credibility-en-v1.0.0.zip`: English

Or copy `SKILL.en.md` and `references/authoritative-sources.en.md` into your agent's skill directory.

If your runtime uses different tool names, map the capability names in the skill to the available tools. No code changes are required.

## License

MIT. See [LICENSE](LICENSE).

Copyright (c) 2026 Canoe16type
