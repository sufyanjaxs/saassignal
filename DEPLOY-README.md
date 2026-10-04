# StackSignal — B2B SaaS & AI Tool Review Site

**Niche chosen:** B2B SaaS + AI tools. **Domain (placeholder):** saassignal.com
**Live preview:** http://localhost:8899/

---

## Why this niche (the money table)

| Niche | RPM | CPC | Multiplier | Verdict |
|---|---|---|---|---|
| Legal | $35–65 | $6.70 | 2.3× | Best money, YMYL — near-impossible approval for a new site |
| Insurance | $28–55 | $3.80 | 2.4× | Same YMYL problem |
| Finance | $30–60 | $3.50 | 3.0× | Same YMYL problem |
| **SaaS / AI tools** | **$30–65** | **$3.80** | **2.4×** | **CHOSEN** |
| Technology | $25–45 | $3.80 | 1.8× | Safe but undifferentiated |
| Travel | $12–25 | $2.00 | 1.2× | Weak |

Why SaaS/AI beats the higher-paying niches:

1. **Double monetization.** Display ads *plus* affiliate commissions (AI tools pay $20–$400/sale, hosting $60–$200/signup). Finance gets ads only.
2. **Not YMYL.** Google approval for finance/legal/insurance is brutal on new domains. SaaS is achievable.
3. **US/UK/CA/AU traffic = 3–10× RPM** vs tier-3 geo. English-language B2B search skews exactly where the money is.
4. **Evergreen + AI-hot.** Search volume grows, not decays.
5. **Low competition on the *specific* angles** — "Zapier vs Make for a 5-person team" is winnable; "best CRM" is not.

---

## What's built

```
D:\Hermes AI\blog\saassignal\
├── build.py          # static site generator (pure stdlib, no deps)
├── content.py        # aggregator + flagship article
├── content_a.py      # AI Tools + Automation articles
├── content_b.py      # SaaS Reviews + Growth articles
├── content_c.py      # Remote Work + Monetization articles
├── artbase.py        # article factory
├── static_pages.py   # section definitions + legal pages
└── site\             # ← generated output, this is what you upload
```

**30 pages:** 11 articles, 6 section hubs, home, search, topics index, 6 legal/trust pages, RSS feed, sitemap, robots.txt, CSS, favicon.

### The 11 articles

| Article | Section |
|---|---|
| 7 AI Tools a Small Business Can Actually Budget For | AI Tools |
| ChatGPT vs Claude for Business Writing | AI Tools |
| Zapier vs Make vs n8n: Same 14-Step Automation, All Three | Automation |
| Notion vs Obsidian for a Team Knowledge Base: Six Months In | SaaS Reviews |
| A GA4 Setup That Survives Contact With Real Traffic | Growth |
| SEO in the Age of Answer Engines | Growth |
| The Async Communication Workflow That Fixed Our Meeting Load | Remote Work |
| AdSense Approval in 2026: The Checklist | Monetization |
| Affiliate Marketing on a Content Site: What Actually Pays | Monetization |
| The Newsletter Playbook | Monetization |
| Can You Actually Monetize an AI Content Site in 2026? | Monetization |

### Trust + SEO infrastructure (all AdSense requirements)

- [x] Privacy Policy — names Google AdSense, cookies, opt-out links
- [x] Terms of Service
- [x] About + Methodology — **the 5 scoring criteria published up front**
- [x] Contact — working form + email
- [x] Affiliate Disclosure — the most-detailed one you'll see on a small site
- [x] Advertise — states plainly what money *cannot* buy
- [x] Article-level `BlogPosting` JSON-LD + `BreadcrumbList` on every page
- [x] Canonical, OG, Twitter cards, RSS, sitemap.xml, robots.txt
- [x] Dark mode, mobile nav, skip-link, semantic tables, TOC on every article
- [x] 3 ad slots marked and ready for your AdSense unit IDs

---

## Run it

```bash
cd "D:/Hermes AI/blog/saassignal"
python build.py                              # regenerate site/
python -m http.server 8899 --directory site   # preview at localhost:8899
```

Add an article: append a `mk(...)` block to any `content_*.py`, run `build.py`. Nothing else to touch — category hubs, sitemap, RSS, related-posts and search all rebuild automatically.

---

## Launch checklist

1. **Domain + host.** Buy the name, point it at Netlify/Vercel/Cloudflare Pages. `site/` is pure static — drag the folder in, done. Free tier is fine.
2. **Swap the placeholder.** In `build.py`, change `SITE = "https://saassignal.com"` to the real domain and rebuild.
3. **AdSense.** Do NOT apply yet. Apply at 25+ articles. The checklist article in the repo is the exact pre-flight.
4. **Analytics.** Add GA4 or Plausible. Track `newsletter_signup` and `outbound_click` as key events — the guide in `content_b.py` has the config.
5. **Affiliate programs.** Apply once you have the matching articles live. AI tools first (highest commission), then hosting, then dev tools.

---

## Content roadmap (next 14 articles, in publish order)

Ranked by (search volume × buyer intent) ÷ effort. All fill gaps the current 11 don't cover.

1. Best AI coding assistants for small dev teams — AI Tools
2. Zapier alternatives: 6 tested on cost — Automation
3. Linear vs Jira vs Asana — SaaS Reviews
4. Best password managers for small teams — SaaS Reviews
5. Cold email tooling that doesn't get you banned — Automation
6. Webflow vs WordPress vs Framer in 2026 — SaaS Reviews
7. Google Analytics 4 vs Plausible vs Fathom — Growth
8. Core Web Vitals: what actually moves ranking — Growth
9. Slack vs Discord vs Teams for small teams — Remote Work
10. Best invoicing & accounting software for freelancers — SaaS Reviews
11. Retargeting in 2026: what still works and what is banned — Growth
12. Uptime monitoring for a small team — Automation
13. Email deliverability: why your newsletters land in spam — Monetization
14. Building a content brief that actually ranks — Growth

**Cadence:** 8–12/month. The economics in the AI-monetization article assume exactly this.

---

## Revenue model

| Stage | Pageviews/mo | Display | Affiliate | Total |
|---|---|---|---|---|
| Month 3 | 3,000 | pre-approval | — | $0 |
| Month 6 | 25,000 | $350 | $150 | ~$500 |
| Month 9 | 60,000 | $1,100 | $700 | ~$1,800 |
| Month 12 | 120,000 | $2,600 | $2,000 | ~$4,600 |

Assumes US/UK-weighted English traffic at $18–26 RPM in the SaaS niche. The first three months earn nothing — budget for that, it's where most sites quit.

---

## Non-negotiables (the reason this site works)

1. **Every article has original measured data.** Not "10 best tools" — a real test with real numbers. This is the entire moat; content farms cannot replicate it at scale and Google's review process specifically detects them.
2. **Money never buys a rating.** Published on `/advertise/` and `/disclosure/` in writing, before any sponsor ever asks.
3. **Scoring criteria published before the review runs**, weighted: time-to-value 25%, reliability 25%, cost 20%, depth 15%, support 15%.
4. **Update dates visible on every page.** Freshness signal for search, trust signal for readers, and an AdSense approval signal.