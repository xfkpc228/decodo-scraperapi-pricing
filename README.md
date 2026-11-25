# Decodo Web Scraping API: What Does It Cost, What Do the $0.15/1K Rates Leave Out, and When Is ScraperAPI the Better Buy? (Full Plan Table)

Decodo's web scraping API (sold as the Web Data API) starts at $0.15 per 1,000 requests and gives new accounts $5 in free credit, capped at 10,000 requests spread across all four endpoints. That entry rate covers the simplest configuration only: plain pages, standard proxy pool, no JavaScript rendering. The AI templates on `/scrape` bill at $1 per 1,000 requests on every plan, and every crawl runs through the premium proxy pool whether or not the target needs it.

What follows is what each Decodo tier includes, what the published prices work out to per 1,000 pages once you divide price by allowance, and where ScraperAPI's credit model lands on the same jobs.

> ScraperAPI's free plan carries 1,000 credits a month (5,000 in the first seven days) and 5 concurrent threads, enough to price a real job with the Domain Cost Estimator before spending anything. Paid plans start at $49/month for 100,000 credits.
>
> 👉 [See ScraperAPI's plans and free-tier limits](https://www.scraperapi.com/pricing?fp_ref=coupons)

## What Decodo's web scraping API covers

Four endpoints share one API key and one base URL, with proxy rotation, JS rendering and anti-bot handling done on the vendor side.

| Endpoint | Returns | Request mode | Ceiling |
| --- | --- | --- | --- |
| `/scrape` | HTML, Markdown, JSON, CSV, PNG screenshots | sync, async or batch | one page per call |
| `/search` | parsed Google organic results and top stories | sync | vendor quotes sub-second responses |
| `/map` | URLs on the page plus the site's top-level sitemap | sync | 147,000 URLs per call |
| `/crawl` | Markdown or HTML per page | async only | 10,000 pages per job |

Authentication is a Bearer token in the `Authorization` header. The vendor's own advice is to run `/map` first to see a site's structure, then `/crawl` with `select_paths` so you collect only the sections you need.

## Decodo's four plans, as published

| Rate limit | Price per month | Crawls included | Pages scraped |
| --- | --- | --- | --- |
| 10 req/s | $19 | up to 19,000 | up to 38,000 |
| 25 req/s | $49 | up to 65,000 | up to 122,000 |
| 50 req/s | $99 | up to 141,000 | up to 330,000 |
| 100 req/s | $249 | up to 383,000 | up to 1.2M |

Every tier lists JS rendering, the 100+ pre-built templates, one key for all four endpoints, 24/7 support and a 14-day money-back window. No annual pricing appears anywhere on the plan table, so there is no discount to weigh against monthly billing.

## The $0.15 rate is a floor, not a budget line

Divide each tier by its page allowance and the effective cost per 1,000 scraped pages comes out near $0.50 on the $19 plan, $0.40 on $49, $0.30 on $99 and $0.21 on $249. The advertised $0.15/1K sits below every one of those figures, which means it applies at volumes above the largest published tier. Plan a monthly budget from the tier you'll actually buy.

Four other details shape the bill more than the headline rate:

- **Rates move with the proxy pool and with rendering.** The product page says pricing "stays flat" with no hidden multipliers, while the help center states plainly that the per-1K rate depends on the proxy pool and whether JavaScript is rendered. The help center is the document that governs billing, so budget from it.
- **Crawls always use the premium pool.** `/scrape` lets you choose Standard or Premium; `/crawl` does not.
- **AI templates cost $1 per 1,000 requests.** Perplexity, ChatGPT, Gemini and Google AI Mode templates on `/scrape` carry that single rate on every plan, roughly 6.6 times the $0.15 entry price.
- **Only successful requests are billed.** Failures retry across the proxy pool at no charge, which matters on heavily protected sites.

The usage policy is the other hard boundary. The API is for publicly accessible data only. Post-login content, private user information and restricted or non-public data are out of scope, so anything behind a paywall or an account is not a job this tool will do.

Free credit is quoted as $5, up to 10,000 requests across all four endpoints, with no card required. The official CLI repository says 2,000 free requests instead. Go with the 10,000 figure from the site and FAQ, then confirm the balance in the dashboard before building a plan around it.

## ScraperAPI's plans and what one credit buys

ScraperAPI bills in credits. A standard page request costs 1 credit, and the multiplier rises with the domain: Amazon is 5 credits, Google and Bing 25, LinkedIn 30, and sites behind Cloudflare, DataDome or PerimeterX add 10 credits whenever bypass logic activates. The Domain Cost Estimator in the dashboard returns the exact credit cost for any URL, and `max_cost` caps what a single request is allowed to consume.

| Plan | Monthly | Annual (per month, 10% off) | Credits/mo | Threads | Sign up |
| --- | --- | --- | --- | --- | --- |
| Free | $0 | n/a | 1,000 (5,000 in first 7 days) | 5 | [See plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Hobby | $49 | $44.10 | 100,000 | 20 | [See plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Startup | $149 | $134.10 | 1,000,000 | 50 | [See plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Business | $299 | $269.10 | 3,000,000 | 100 | [See plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Scaling | $475 | $427.50 | 5,000,000 | 200 | [See plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Professional | $975 | $877.50 | 10,500,000 | 300 | [See plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Advanced | $1,975 | $1,777.50 | 21,500,000 | 500 | [See plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Enterprise | Custom | Custom | 22,000,000+ | 500+ | [See plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |

Every plan includes JS rendering, premium residential and mobile IPs, anti-bot bypass, JSON autoparse, rotating proxy pools, custom headers, CAPTCHA handling, automatic retries, unlimited bandwidth and a 99.9% uptime guarantee. Country-level geotargeting starts at Business; Hobby and Startup are limited to US and EU. Credits reset at each renewal date and unused credits are lost rather than carried forward. Hobby, Startup and Business can enable auto-upgrade so an account steps up a tier when credits run out; pay-as-you-go with a monthly spending cap is available from Scaling upward. Cancellation is self-serve, and the refund window is 7 days with no questions asked.

The per-credit price swings hard with volume. Hobby works out to about $0.49 per 1,000 credits, Scaling to roughly $0.095. On a standard page where 1 credit equals 1 request, that's the whole story. On Amazon's 5-credit multiplier, 1,000 pages consume 5,000 credits, or $2.45 on Hobby against $0.48 on Scaling. Google's 25-credit multiplier turns 1,000 searches into 25,000 credits, about $12.25 on Hobby and $2.38 on Scaling.

That divergence is why the tier you pick should come from a measured sample of your own URLs rather than from the sticker price.

👉 [Compare ScraperAPI's credit cost across plans](https://www.scraperapi.com/pricing?fp_ref=coupons)

## Choosing by workload, not by feature list

**A few thousand plain pages a month, nothing exotic.** Decodo's $19 tier covers up to 38,000 pages at a lower line item than ScraperAPI's $49 Hobby plan. If your targets are ordinary HTML pages with no bot protection, the cheaper invoice is Decodo's.

**Any meaningful share of Amazon, retail or SERP targets.** Decodo doesn't publish per-target rates next to its plan table, so the comparison has to be measured rather than read. ScraperAPI publishes every multiplier and exposes them through the estimator, which makes budgeting a mixed workload possible before purchase. Run the same ten URLs through both cost calculators and compare the totals for a month of real traffic.

**Site-wide crawls.** Decodo caps a single job at 10,000 pages and always uses the premium pool. ScraperAPI charges per page like any other request, so a 10,000-page crawl of standard pages consumes 10,000 credits and fits inside Hobby's 100,000. Both handle the job; the difference shows up in what the crawl costs at your page count and how many concurrent crawls you need to run.

**Google results at volume.** ScraperAPI bills Google and Bing at 25 credits per request, which is $2.38 per 1,000 searches at the Scaling tier and $12.25 at Hobby. Decodo quotes a single rate for `/search` without publishing the number beside the plan table. Price both before committing to either.

**High concurrency on a small budget.** ScraperAPI's Hobby plan allows 20 concurrent threads for $49; Decodo's $19 tier runs at 10 requests per second and its $49 tier at 25. If your bottleneck is parallelism rather than page count, compare those two figures directly.

**A long trial window.** Decodo refunds within 14 days; ScraperAPI's window is 7. If you need more than a week to validate a migration, that gap is worth weighing.

👉 [Start on ScraperAPI's free plan and test your own targets](https://www.scraperapi.com/pricing?fp_ref=coupons)

## Questions that decide the purchase

**How many free requests do I get on Decodo?**
$5 in credit, up to 10,000 requests across `/scrape`, `/search`, `/map` and `/crawl`, with no card required. The CLI repository's 2,000-request figure conflicts with the site and should be treated as outdated.

**Does JavaScript rendering cost extra?**
On Decodo, the help center says the rate depends on the proxy pool and on whether JS is rendered, even though the product page claims no multipliers. Assume it can cost more and check the billing page for your endpoint. ScraperAPI lists JS rendering as included on every plan, and its published multipliers are tied to domains and anti-bot bypass rather than rendering.

**Can I scrape pages behind a login?**
Not with Decodo's Web Data API. The usage policy excludes post-login and authenticated content, private user information and restricted data. Users are responsible for staying within each target site's terms.

**Will my old Decodo token still work?**
The help center, updated in October 2026, states that legacy tokens from the Web Scraping API and Fast Search API do not work with the Web Data API, and points to a migration guide for the new endpoints and authentication. The official CLI README says older basic-auth tokens still work in the CLI, while also noting that `search`, `map` and `crawl` reject them. Confirm with support before swapping credentials on a production integration.

**What happens when ScraperAPI credits run out?**
On Hobby, Startup and Business, scraping pauses at renewal unless auto-upgrade is enabled. From Scaling upward you can turn on pay-as-you-go at a fixed per-credit rate with a monthly cap you set, and the account won't exceed that cap unless you change it.

**Which one refunds me if the data quality disappoints?**
Decodo offers 14 days. ScraperAPI offers 7 days, no questions asked, and you can cancel from the dashboard at any time without a charge.

## The decision, in one pass

Testing an idea this week with no commitment: start on ScraperAPI's free plan, which gives 1,000 credits a month plus 5,000 in the first seven days, and price your real URLs in the dashboard before choosing a tier. Under 30,000 plain pages a month with no protected targets: Decodo's $19 tier is the cheaper invoice, and there is no reason to pay more. Mixed domains that include marketplaces, search engines or bot-protected retail: measure ten representative URLs first, because a 5-credit or 25-credit multiplier can flip the ranking between a $49 plan and a $249 one. Crawling one site end to end: check whether your page count fits inside a single Decodo job cap of 10,000 pages, and compare what those pages cost in credits on ScraperAPI.

Three things to confirm before you enter card details. Your actual monthly page count, taken from a week of logs rather than a guess. Whether you need country-level geotargeting, since ScraperAPI restricts Hobby and Startup to US and EU. And whether annual billing makes sense at all, because ScraperAPI's 10% discount only pays off if you'll burn the credits, and unused credits don't roll over.

👉 [Check ScraperAPI's current plans and pick the smallest tier that covers your workload](https://www.scraperapi.com/pricing?fp_ref=coupons)
