# soax pricing: how the credit plans really price out per GB, and a cheaper route when your volume is small

Type "soax pricing" into Google and you land on a page that opens with the words "Predictable pricing for web access at scale" and "No sales theatre. No pricing games." A few centimetres below that, there's a headline rate of $0.35 per GB.

Here's the thing about that number: to reach it you need the $3,000-a-month plan *and* traffic routed through the cheapest country band. If you need US or UK IPs — which is what most people reading a pricing page actually need — the best published rate you can ever get is around $0.85/GB, and it's still locked behind that $3,000 plan. The rate a brand-new customer with no commitment pays is $5/GB.

All of those numbers are real and published on the same page. Working out which one applies to you is the entire job of understanding SOAX pricing. So let's do it properly.

## What you're actually buying: plans plus credits

SOAX doesn't sell you a bucket of gigabytes for a flat monthly fee. It sells a subscription that sets your *rate*, and credits you spend against that rate. One credit is roughly $1 of usage — a reference value, not cash.

That single design decision causes most of the confusion. Paying $200 doesn't get you $200 worth of data bundled in on top of your subscription; the fee *is* the credits. Moving up the ladder doesn't get you more data per dollar — it gets you a cheaper rate to spend those dollars at.

Here's the current ladder as it appears on SOAX's own pricing page:

| Plan | Monthly price | Cost per GB, tier 1 | Notes |
| --- | --- | --- | --- |
| Sandbox | $0 | $5.00/GB | Free to join, no time limit, but pay-as-you-go at the highest rate on the card |
| Builder | $200 | $3.00/GB | The first real subscription |
| Team | $500 | $2.20/GB |  |
| Scale | $1,500 | $1.50/GB | ZIP-code targeting unlocks here |
| Enterprise | From $3,000 | From $0.85/GB | Custom quotes, the only place the sub-$1 rates live |

Read the sandbox row again, because it's the part people get wrong. Sandbox is free — no monthly fee, no expiry on the account itself. You top up a minimum of $25 and pay for traffic as you go, at the most expensive rate SOAX publishes. It's also capped at one package and one seat, which is fine for testing an integration and useless as a working setup.

The usual advice to "start small and scale up" works against you here, because small is exactly when the rate is worst.

## The second dial: geography

SOAX sorts countries into three bands, and the band matters as much as the plan.

**Tier 1** covers 32 countries — the US, UK, Germany, Japan, Australia and the rest of the developed-market list. These are the most expensive IPs to source, so they cost the most per GB. **Tier 2** covers roughly 60 markets including Brazil, India, Mexico and Turkey. **Tier 3** is everything else — around 150-odd remaining countries.

Routing through tier 1 instead of tier 3 can cost you up to eight times more per GB *on the same plan*. That's SOAX's own wording in its billing FAQ, and it's the single most useful sentence on the whole site.

Then it compounds. Within each geo tier there are three volume bands, and the rate drops as you burn through the bands during a billing period. SOAX's billing FAQ walks through an example: 20 TB through Germany and the US is charged at 0.85 credits/GB for the first 5 TB, 0.75 for the next 10, and 0.50 for the remainder. Tier-3 traffic is billed separately, at bands running down to 0.25 credits/GB. Every tier resets to its first band when the next billing period starts, and usage in one tier doesn't help the others.

So no single number describes what SOAX costs. Two dials multiply, and both of them have to be turned to reach the rate advertised at the top of the page.

## What that works out to at volumes people actually buy

This is where SOAX pricing gets uncomfortable for small and mid-sized users.

At 5 GB a month, a $200 floor means an effective cost of $40 per GB, whatever the rate card says. The per-GB figure improves almost tenfold — to about $4 — once you're buying 50 GB a month, and that's purely because the fixed part of the bill stops dominating it.

Third-party benchmarks that model real monthly volumes put it in concrete terms:

- **100 GB/month** — about $300, using the Builder rate of $3.00/GB plus credits beyond the plan allowance. Effective rate: $3/GB.
- **500 GB/month** — roughly $1,100 at the Team rate of $2.20/GB.
- **1+ TB/month** — this is where the ladder starts to look competitive, and where the headline numbers finally become reachable.

If your monthly consumption is under about 20 GB, SOAX is structurally the wrong shape for you, regardless of how good the network is. You're not buying bandwidth at that point, you're subsidising a subscription you don't need.

## What's bundled in, and what isn't

The plan price isn't only about gigabytes. A few things genuinely sit inside the same credit balance:

- **Residential and mobile are priced identically.** SOAX doesn't charge a premium for carrier IPs — one set of per-GB rates covers both networks, on every plan down to Sandbox. Most competitors charge a large multiple for mobile traffic, so if you need both, this matters more than the rate card suggests.
- **One shared balance across residential, mobile, US ISP and datacenter.** You're not juggling separate accounts or invoices.
- **155M+ residential IPs across 195+ countries**, plus a 33M+ mobile pool, per SOAX's published figures.
- **Carrier/ASN targeting on every paid plan**, not gated to Enterprise, and no annual contract requirement.

And the constraints worth knowing before you pay:

ZIP-code targeting is only on Scale and Enterprise — lower plans go down to country, region, city and ISP. KYC identity verification applies to most plans, which is a direct consequence of SOAX's anti-abuse stance and does add friction to sign-up. Unused credits roll over for 60 days on monthly billing, and longer on annual or Enterprise arrangements; on monthly billing, a project you pause for a quarter burns prepaid credit you already paid for. There's no genuinely free trial either — SOAX's position is that free traffic invites misuse, so testing costs $1.99 for 400 MB across three days, with full dashboard access across proxy types.

> The practical upshot: SOAX pricing rewards teams who know their monthly traffic mix in advance and can commit to a tier-1-heavy workload at scale. It punishes anyone whose usage is spiky, seasonal, or exploratory.

## Where SOAX pricing is genuinely worth the money

Two situations, mostly.

The first is geo-precision. Country, region, city and ASN or carrier-level targeting applied cleanly is the actual product here, and it's more surgical than most networks expose without a sales call. If your job depends on appearing in one specific metro, or testing a carrier-gated signup flow, paying a premium per GB is defensible because the alternative isn't a cheaper gigabyte — it's a wrong answer.

The second is at genuine enterprise volume with a predictable target mix. Once you're through several terabytes a month, and your traffic is concentrated in tier-1 countries, the Enterprise bands get you into a rate range that the low-end pay-as-you-go providers can't match on headline price.

For everyone else — a small team pulling 10 or 30 GB a month, or a scraper whose target countries shift month to month — the credit subscription is a poor fit, and the fix isn't a discount. It's a different billing model.

## The cheaper route when you don't need enterprise volume

If the problem you're solving is "I want residential IPs without a $200 monthly floor and without credits that expire in 60 days," the alternative worth looking at is 9Proxy, which bills by bandwidth with no subscription attached.

The model is straightforward: you buy a data package, you get 180 days to use it, and you generate as many proxy endpoints as you like from the dashboard. No activation fees per IP, no counting IPs. Sessions can be sticky or rotating with a custom duration, authentication works by sub-user credentials or IP whitelisting, and targeting goes down to country, state, city, ZIP and ISP — which, notably, is deeper than SOAX offers below its $1,500 tier.

Coverage is smaller: 20M+ residential IPs across 90+ countries, against SOAX's 155M+ across 195+. That's the real trade-off, and it matters if your targets are in thin markets.

Here's the full published price list:

| Plan | Data / unit | Price | Validity | Get it |
| --- | --- | --- | --- | --- |
| Starter GB pack | 5 GB | $3.00/GB ($15) | 180 days | [ Grab the 5 GB pack](https://bit.ly/9-Proxy) |
| Small bundle | 50 GB + 5 GB bonus | $2.10/GB ($105) | 180 days | [ Take the 50+5 GB bundle](https://bit.ly/9-Proxy) |
| Mid pack | 100 GB | $1.50/GB ($150) | 180 days | [ Pick up 100 GB](https://bit.ly/9-Proxy) |
| Volume pack | 200 GB | $1.00/GB ($200) | 180 days | [ Buy the 200 GB pack](https://bit.ly/9-Proxy) |
| Bulk pack | 1,000 GB | $0.80/GB ($800) | 180 days | [ Go for 1,000 GB](https://bit.ly/9-Proxy) |
| Bulk pack | 2,000 GB | $0.75/GB ($1,500) | 180 days | [ Stock up on 2,000 GB](https://bit.ly/9-Proxy) |
| Pay-per-IP | Per IP, unlimited bandwidth | From about $0.015/IP | Per the IP plan | [ See the per-IP option](https://bit.ly/9-Proxy) |
| Enterprise | Custom volume, team seats | VIP pricing, quoted | No expiry | [ Ask about Enterprise](https://bit.ly/9-Proxy) |

Two things worth flagging on that list. First, the IP-based plans bill per IP with unlimited bandwidth attached, which is a completely different shape of cost from per-GB billing — if your workload is many small requests rather than sustained throughput, it can undercut per-GB pricing substantially. Second, the Enterprise tier removes the 180-day clock entirely and adds team functionality: one owner plus up to five members, per-member traffic controls, activity logs, and shared bandwidth that doesn't expire inside the team.

Published prices on a ladder like this get adjusted, so confirm the current numbers on the sign-up page before you commit.

## The same workloads, side by side

Comparing the two models at the volumes where most people actually operate:

| Monthly volume | SOAX (credits model) | 9Proxy (pack model) | Notes |
| --- | --- | --- | --- |
| 5 GB | ~$40/GB effective — a $200 floor spreads across very little data | $15 for a 5 GB pack | SOAX's minimum subscription makes low volume expensive |
| 100 GB | ~$300 (Builder rate, $3.00/GB) | $150, valid 180 days | Same order of magnitude, half the cost, no monthly renewal |
| 200 GB | ~$600 at the Builder rate | $200 | The gap widens as SOAX's rate stays plan-bound |
| 1,000 GB | ~$1,500 (Scale, $1.50/GB) | $800 | SOAX's advantage only appears above this with tier-3 traffic |
| Unused balance | Lapses after 60 days on monthly billing | 180 days to spend | A quiet or seasonal month costs you differently on each |

The honest read: 9Proxy wins on billing flexibility and on the low-to-mid volume bands. SOAX wins on pool size, country coverage, and extreme-volume tier-1 rates. If your traffic is concentrated in the US or Western Europe and you're pulling single-digit gigabytes a month, the SOAX subscription is an expensive way to buy a small amount of data — not because the rate is bad, but because of the floor underneath it.

Ready to compare on your own numbers? [👉 Start with a 5 GB pack and test your targets](https://bit.ly/9-Proxy) — a pack that doesn't expire in 60 days is a much easier experiment to run than a $200 subscription.

## Questions that decide the purchase

**What's the cheapest way into SOAX?**
Sandbox, the free plan — but it's billed at $5.00/GB with a $25 minimum top-up and limited to a single package and seat. For anything beyond integration testing, the effective entry point is Builder at $200/month.

**Do SOAX credits expire?**
Yes. Sixty days on monthly billing, with longer windows on annual and Enterprise terms. That's the least forgiving part of the model and SOAX states it plainly rather than hiding it.

**Is there a free trial?**
No. Testing costs $1.99 for 400 MB over three days, with access across proxy types.

**Can I pay per gigabyte without a subscription?**
Not at SOAX — the minimum paid commitment is $200/month. If avoiding a monthly floor is the priority, a prepaid data pack is the better shape: [👉 check the bandwidth plans](https://bit.ly/9-Proxy) and see whether your target mix works on a 20M+ IP pool before scaling up.

**Is mobile traffic more expensive?**
Not at SOAX — residential and mobile share the same per-GB rates, which is unusual and genuinely useful if you need both.

## Bottom line

SOAX pricing is honest but layered. Every number is published, and nothing is hidden — you just have to read the plan column and the geography column together, because either one alone will give you a wrong answer. That $0.35 headline describes a purchase most readers can't make.

If you're a team pushing multiple terabytes through tier-1 countries and you value city- and carrier-level precision, the credit model is a reasonable buy and the Enterprise bands are where it earns its keep. If you're buying tens of gigabytes a month, or your targeting shifts between markets, you're paying a subscription fee to access a rate you'll never reach — and a prepaid pack with a 180-day window is the more sensible place to spend the money.
