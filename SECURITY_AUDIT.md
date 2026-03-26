# Security Audit — multi-search-engine (gpyangyoujun)

Date: 2026-03-27
Audited package: `multi-search-engine@2.0.1` (ClawHub)

## Scope Reviewed

- `SKILL.md`
- `config.json`
- `metadata.json`
- `references/international-search.md`
- package metadata files (`_meta.json`, `.clawhub/origin.json`)

## Findings

### 1) High-risk operator examples without safeguards (Medium)
Reference content includes search patterns that can be abused (e.g., `intext:password`, `intitle:"index of"`, cache scraping examples) without clear ethical/legal limits.

**Risk:** unsafe or policy-violating search behavior by less-constrained agents.

### 2) Missing consent/trust-boundary checks (Medium)
The skill does not enforce a preflight check before running broad/sensitive searches.

**Risk:** accidental reconnaissance-style queries or privacy-invasive collection.

### 3) Overly broad extraction guidance (Low)
Examples encourage direct fetch of result pages with no minimization strategy.

**Risk:** excessive data capture and unnecessary processing of unrelated content.

### 4) Packaging hygiene issues (Low)
Includes extra non-essential files (`CHANGELOG.md`, `CHANNELLOG.md`) and references a missing file (`references/advanced-search.md`) in SKILL docs.

**Risk:** maintenance confusion and lower reliability.

## Verdict

No executable malicious code observed. Primary risk is **unsafe guidance design**. A hardened rewrite should keep functionality while adding strict usage boundaries and minimization.

## Hardened Rewrite Requirements

1. Keep all feature categories (multi-engine URLs, operators, time filters, privacy engines, WolframAlpha).
2. Add explicit allowed-use and disallowed-use policy.
3. Add preflight checklist and minimal-extraction rules.
4. Remove/replace exploit-prone examples.
5. Keep examples focused on legitimate research and troubleshooting tasks.
