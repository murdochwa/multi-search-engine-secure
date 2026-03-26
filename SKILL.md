---
name: "multi-search-engine-secure"
description: "Security-hardened multi-engine search workflow (CN + global) with safe query construction, time filters, privacy-first options, and WolframAlpha queries. Use for legitimate research, verification, and discovery tasks with bounded extraction."
---

# Multi Search Engine (Security-Hardened)

Use this skill to build and run search-engine URLs safely across Chinese and global engines.

## Safety Policy (Required)

### Allowed
- Research and fact-finding
- Documentation lookup
- Public market/news/technical discovery
- Cross-engine verification

### Disallowed
- Credential harvesting or account compromise queries
- Reconnaissance intended to target systems/people
- Privacy-invasive collection of personal data
- Any illegal or unethical use

If a request appears unsafe, refuse or narrow scope.

## Preflight Checklist

Before searching:
1. Confirm purpose is legitimate.
2. Confirm minimal needed output.
3. Prefer privacy-first engine when user intent permits.
4. Use time/site filters to reduce noise.

## Engine Catalog

### CN-focused
- Baidu: `https://www.baidu.com/s?wd={keyword}`
- Bing CN: `https://cn.bing.com/search?q={keyword}&ensearch=0`
- Bing INT: `https://cn.bing.com/search?q={keyword}&ensearch=1`
- 360: `https://www.so.com/s?q={keyword}`
- Sogou: `https://sogou.com/web?query={keyword}`
- WeChat: `https://wx.sogou.com/weixin?type=2&query={keyword}`
- Toutiao: `https://so.toutiao.com/search?keyword={keyword}`
- Jisilu: `https://www.jisilu.cn/explore/?keyword={keyword}`

### Global
- Google: `https://www.google.com/search?q={keyword}`
- Google HK: `https://www.google.com.hk/search?q={keyword}`
- DuckDuckGo: `https://duckduckgo.com/html/?q={keyword}`
- Yahoo: `https://search.yahoo.com/search?p={keyword}`
- Startpage: `https://www.startpage.com/sp/search?query={keyword}`
- Brave: `https://search.brave.com/search?q={keyword}`
- Ecosia: `https://www.ecosia.org/search?q={keyword}`
- Qwant: `https://www.qwant.com/?q={keyword}`
- WolframAlpha: `https://www.wolframalpha.com/input?i={keyword}`

## Safe Query Operators

- `site:` restrict to known sources
- `filetype:` target specific doc formats
- `"phrase"` exact matching
- `-term` exclude noisy terms
- `OR` alternative terms

Example:
```javascript
web_fetch({"url":"https://www.google.com/search?q=site:github.com+openclaw+filetype:md"})
```

## Time Filters

- `tbs=qdr:h` hour
- `tbs=qdr:d` day
- `tbs=qdr:w` week
- `tbs=qdr:m` month
- `tbs=qdr:y` year

Example:
```javascript
web_fetch({"url":"https://www.google.com/search?q=openclaw+release+notes&tbs=qdr:m"})
```

## Privacy-First Engines

Prefer when appropriate:
- DuckDuckGo
- Startpage
- Brave
- Qwant

## WolframAlpha Knowledge Queries

Legitimate use examples:
- unit conversion: `100 USD to AUD`
- math: `integrate x^2`
- weather math/lookup summaries

```javascript
web_fetch({"url":"https://www.wolframalpha.com/input?i=100+USD+to+AUD"})
```

## Execution Pattern (Bounded)

1. Build query URL with encoded keyword.
2. Fetch only needed result page.
3. Extract only requested answer snippets.
4. Avoid broad harvesting or repeated uncontrolled crawling.

## Output Standard

Report:
- engines used
- exact query string
- top findings only
- confidence/limitations

## Notes

- No API keys required.
- Respect target ToS and legal requirements.
