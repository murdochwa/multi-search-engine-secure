# International Search Guide (Security-Hardened)

Use this reference to construct precise, lawful, and privacy-aware queries.

## Core Engines
- Google / Google HK
- DuckDuckGo
- Brave
- Startpage
- Yahoo
- Qwant
- Ecosia
- WolframAlpha

## Safe Advanced Operators
- `site:` (scope to trusted domains)
- `filetype:` (target docs)
- `"..."` (exact phrase)
- `-term` (exclude noise)
- `OR` (alternatives)

Example:
```text
site:docs.python.org "asyncio" filetype:html
```

## Time & Freshness (Google)
- `tbs=qdr:h` hour
- `tbs=qdr:d` day
- `tbs=qdr:w` week
- `tbs=qdr:m` month
- `tbs=qdr:y` year

## Region/Language Filters
- `hl=` interface language
- `lr=` result language
- `gl=` geo hint

## Privacy Recommendations
- Prefer DuckDuckGo/Startpage/Brave for sensitive-topic research.
- Avoid account logins unless required.
- Minimize data saved from results.

## WolframAlpha Best Uses
- Calculations, conversions, quick quantitative facts.

## Disallowed Patterns
Do not use search patterns intended for:
- credential discovery
- unauthorized system access
- personal data targeting

## Practical Workflow
1. Start with one engine and narrow query.
2. Add site/time constraints.
3. Cross-check with a second engine.
4. Return concise findings + limitations.
