---
name: web-search-credibility
description: A platform-agnostic workflow for credible web research. Use when a task depends on external or real-time information, when fact-checking a link or claim, or when the user explicitly asks to search. Emphasizes primary sources, cross-checking, reading the original page, conflict handling, and citations.
---

# High-Credibility Web Search

Goal: make every research result traceable and verifiable. Better to say less than to say something wrong.

## When to use

- The user asks to search, look something up, or find recent information
- The user provides a link and asks for a summary, fact-check, or extraction
- The answer depends on external or real-time facts: versions, prices, schedules, announcements, parameters, policies, company data, fictional settings
- You are unsure about a fact that can be verified externally

Do not search for common knowledge, pure reasoning, local operations, or calculations just to appear thorough.

## Tool-agnostic

Do not hard-code a vendor or tool name. Runtimes may expose `web_search`, `fetch_page`, `extract`, domain filters, or date filters. Use the equivalent capability available in the current runtime.

If only search snippets are available and the page cannot be fetched:

- State: "Based on search snippets; the original page was not verified."
- Do not treat a snippet as full context.
- Try to verify key claims with another fetchable source.

## Workflow

1. **Identify the domain**: technology, product, policy, academia, company, fiction, etc.
2. **Build the query**:
   - Natural language + official site name
   - Use domain filters if supported instead of putting `site:` inside the query
   - Official sources often look like `docs.<domain>`, `<domain>/support`, `<domain>/news`, official repositories and releases
   - Multilingual: locate the name in the user's language, then verify details in the official language or English
3. **Search**
4. **Classify the source**: primary official, reliable secondary, community, or unreliable
5. **Cross-check**: use two independent sources for consequential claims; label single-source claims
6. **Fetch the original page**: verify context; do not decide from a snippet
7. **Deliver**: conclusion, evidence, uncertainty, sources

## Source tiers

### Tier A: authoritative primary

Official sites, docs, help centers, announcements; standards, laws, regulations, policy texts; official repositories, releases, changelogs; official databases, company filings, regulator disclosures; papers, DOI, PubMed, arXiv (by field).

### Tier B: reliable secondary

Authoritative encyclopedias; official developer communities, Stack Overflow, GitHub Discussions; official or professional media; signed industry reports.

### Tier C: community sources (usable with a label)

Fan wikis, Fandom, community reference sites; personal blogs, columns, aggregators; e-commerce or merchant pages.

- Label them "community-maintained / unofficial"
- Use them for names, settings, and mechanics
- Numbers, versions, prices, and drop rates must be verified against official sources or actual testing
- If they conflict with official sources, follow the official source and explain the discrepancy

### Not acceptable as evidence

Content farms, unsigned aggregators, clickbait, pure SEO pages, truncated snippets without context.

## Conflicting sources

When sources disagree:

- State that there is a disagreement
- List the sources and dates
- Judge which is newer or closer to a primary source
- Recommend which to trust, with priority:

**official text / standard / first-party announcement / official repository > reliable secondary > community**

Do not split the difference, and do not present low-quality sources as equal to official ones.

## Output

1. **Conclusion**: answer directly
2. **Evidence**: source type and whether it was cross-checked
3. **Uncertainty**: distinguish fact, opinion, and inference; if evidence is insufficient, say "current evidence suggests" or "uncertain"
4. **Sources**: external information must include links; never say "there is information online" without a source
5. **No authoritative source**: say so explicitly; do not fill the gap with low-quality sources

### Citation styles

Default `compact`:

```markdown
Conclusion...

Sources:
- [Title](https://example.com/page)
```

For platforms that support horizontal rules, `section`:

```markdown
Body...

***

Sources
- [Title](https://example.com/page)

***
```

For plain text, `plain`:

```text
Sources:
Title - https://example.com/page
```

Rules: put citations after the body; list only sources actually used; label single-source claims; stay consistent within one response.

## Pre-delivery self-check

1. Did this answer use search, page fetching, or external information?
2. If yes, are the sources included?
3. Were key claims checked against the original page?
4. Are conflicting sources explained?
5. Did I present inference as fact?
6. Did I cite a content farm?

External information without citations is an incomplete answer.

## Boundaries

- Do not search just to pad an answer
- Refuse searches for illegal, infringing, or harmful purposes
- Search snippets can be stale or distorted; verify key claims against the original page
- Explain conflicts and your judgment
- If you cited something wrong, acknowledge it, thank the correction, and provide a corrected source

## References

- `references/authoritative-sources.en.md`
- `examples/citation-styles.en.md`
