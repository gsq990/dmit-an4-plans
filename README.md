# DMIT AN4: What the LAX.AN4 Pro, EB and T1 Plans Really Cost, Which One Fits Your Use Case, and What Changes You Should Plan For

Searching "DMIT AN4" usually starts with the same question: is this still worth buying, or am I looking at a dead product line?

That's a fair question, because AN4 has been the most scrambled part of DMIT's catalog. It was launched, quietly promoted, raised in price, sold out, delisted, re-listed as a stopgap, and restocked in batches over the last year. Blog posts from different months quote prices that differ by 40 percent for the identical plan name, and a lot of them are still ranking.

So here's the practical version: what AN4 actually is, what the plans cost right now, how the three network profiles differ, and where the trap is if you buy based on an old price list.

## What "AN4" means in DMIT's naming scheme

DMIT codes its hardware generations with short platform tags, and those tags show up in front of every product name. On the Los Angeles side you'll see three:

| Platform code | CPU generation | Roughly |
| --- | --- | --- |
| AS3 | AMD EPYC 7003 (Milan, Zen 3) | The older, cheaper hardware; being expanded again as the value tier |
| AN4 | AMD EPYC 9004 (Genoa, Zen 4) | DDR5, PCIe 5.0, the generation this article covers |
| AN5 | AMD EPYC 9005 (Turin, Zen 5) | The newest generation; sales were suspended at one point, then reopened |

The three-digit code doesn't tell you anything about bandwidth or routing. It only tells you which CPU platform the host node runs on. A plan called LAX.AN4.Pro.MINI and one called LAX.AS3.Pro.MINI can look nearly identical on paper, since both are 4-core CN2 GIA boxes, even though the underlying silicon is a generation apart.

The letter in the middle matters far more than the platform tag. That's the network profile.

## The three AN4 profiles at Los Angeles: Pro, EB, T1

Every LAX.AN4 plan belongs to one of three routing profiles. This is the part worth understanding before you compare any price.

**Premium (Pro)** is the China-optimized tier. Outbound: China Telecom via AS4809 (CN2 GIA), China Unicom direct via AS4837, China Mobile via Hong Kong CMI (AS58453). Return traffic for all three carriers comes back over AS4809 CN2 GIA. That return path is what most buyers are actually paying for.

**Eyeball (EB)** swaps the return routing to CMIN2 (AS58807) with 9929 in the mix, and is generally the better fit if your users sit on China Unicom or China Mobile rather than Telecom. At matching specs EB usually comes with more traffic for the same money.

**Tier 1 (T1)** is plain international BGP transit with no China-specific optimization at all. It's the cheapest of the three, has the largest ports, and counts traffic in one direction (whichever of in/out is larger) rather than both.

A quick note on traffic accounting, because it changes what you're really buying: Pro and EB are billed bidirectionally, so 5TB means 2.5TB up plus 2.5TB down. T1 counts one direction. Same nominal number, different real allowance.

## LAX.AN4 Premium (Pro) plans and current prices

This is where the price confusion lives, so let's put the numbers side by side honestly.

Two price tiers circulate for the identical plan names. Older lists show LAX.AN4.Pro.MINI at **$58.88/month**. DMIT's own AN4 order page currently shows the same plan at **$72.90/month**. The reason is documented: when hardware costs climbed, DMIT re-listed the older AS3 platform and raised prices on the AN4 and AN5 generations rather than pushing those increases onto the cheap AS3 boxes. The $58.88 figure isn't a scam, it's just from before that revision.

Treat the order page number as the real one:

| Plan | vCPU | RAM | SSD | Port / Traffic (bi-directional) | After the cap | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.AN4.Pro.MINI | 4 | 4 GB | 80 GB | 10 Gbps / 5000 GB | 8 Mbps unmetered | $72.90/mo | [Current AN4 Pro price and stock](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |
| LAX.AN4.Pro.MICRO | 4 | 4 GB | 160 GB | 10 Gbps / 7000 GB | 8 Mbps unmetered | $102.90/mo | [Check LAX.AN4.Pro.MICRO availability](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |
| LAX.AN4.Pro.MEDIUM | 6 | 8 GB | 160 GB | 10 Gbps / 14000 GB | 10 Mbps unmetered | $239.90/mo | [Verify MEDIUM stock before ordering](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |
| LAX.AN4.Pro.LARGE | 8 | 16 GB | 320 GB | 10 Gbps / 25000 GB | 10 Mbps unmetered | $459.90/mo | [See LAX.AN4.Pro.LARGE details](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |
| LAX.AN4.Pro.GIANT | 12 | 24 GB | 640 GB | 10 Gbps / 50000 GB | 10 Mbps unmetered | $929.90/mo | [Check LAX.AN4.Pro.GIANT pricing](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |

Two things stand out. First, MEDIUM has been showing as sold out on the order page, so don't plan a purchase around it. Second, and more importantly: **the small AN4 Pro plans are gone.** The TINY, Pocket and STARTER rungs that used to start this line at $9.99/month no longer appear on the AN4 Pro listing. The cheapest way into AN4 Premium now is MINI at $72.90/month, which is a very different proposition from the $9.99 entry point that made AN4 famous in the first place.

For reference, that older pricing tier looked like this, and you should assume it's no longer orderable on AN4 Pro: TINY $9.99/mo, Pocket $14.90, STARTER $29.90, MINI $58.88, MICRO $74.99, MEDIUM $168.88, LARGE $338.88, GIANT $619.99. If you find a page quoting those numbers for AN4, it's stale.

Annual billing on AN4 Pro has been advertised at roughly a 10 percent discount versus monthly. Checkout will show which term is eligible.

## LAX.AN4 Eyeball (EB) plans

EB is the profile most people should look at first if their audience isn't Telecom-heavy, mainly because the traffic allowances are noticeably larger at the same spec level. The 4-core/4 GB EB plan carries 10TB against Pro's 5TB at the same core count.

| Plan | vCPU | RAM | SSD | Port / Traffic (bi-directional) | After the cap | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.AN4.EB.TINY | 1 | 2 GB | 20 GB | 2 Gbps / 1500 GB | 4 Mbps unmetered | $9.99/mo | [Order LAX.AN4.EB.TINY](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |
| LAX.AN4.EB.Pocket | 2 | 2 GB | 40 GB | 4 Gbps / 3000 GB | 4 Mbps unmetered | $14.90/mo | [Check LAX.AN4.EB.Pocket stock](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |
| LAX.AN4.EB.STARTER | 2 | 2 GB | 80 GB | 10 Gbps / 5000 GB | 4 Mbps unmetered | $29.90/mo | [See EB.STARTER plan details](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |
| LAX.AN4.EB.MINI | 4 | 4 GB | 80 GB | 10 Gbps / 10000 GB | 8 Mbps unmetered | $58.80/mo | [Order LAX.AN4.EB.MINI](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |
| LAX.AN4.EB.MICRO | 4 | 4 GB | 160 GB | 10 Gbps / 14000 GB | 8 Mbps unmetered | $74.99/mo | [Check EB.MICRO availability](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |
| LAX.AN4.EB.MEDIUM | 6 | 8 GB | 160 GB | 10 Gbps / 30000 GB | 10 Mbps unmetered | $168.88/mo | [See EB.MEDIUM configuration](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |
| LAX.AN4.EB.LARGE | 8 | 16 GB | 320 GB | 10 Gbps / 50000 GB | 10 Mbps unmetered | $338.88/mo | [Order LAX.AN4.EB.LARGE](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |
| LAX.AN4.EB.GIANT | 12 | 24 GB | 640 GB | 10 Gbps / 100000 GB | 10 Mbps unmetered | $620.00/mo | [Check EB.GIANT pricing](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |

Be aware that this EB table reflects the pre-revision price tier. The same across-the-board AN4 increase that pushed Pro.MINI to $72.90 has been rolling through the Pro and EB premium lines, and DMIT stated it would continue adjusting those prices. Confirm the figure on the order page before you commit to a term.

## LAX.AN4 Tier 1 plans: the cheap ones are still cheap

T1 is where AN4 still has genuinely low prices, precisely because there's no China-optimized routing to pay for. Traffic counts one direction, and the post-cap throttle is far more generous than on Pro or EB (100 to 500 Mbps instead of single-digit Mbps).

| Plan | vCPU | RAM | SSD | Port / Traffic (one direction) | After the cap | Price | Billing | Order |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.AN4.T1.WEE | 1 | 1 GB | 20 GB | 4 Gbps / 1000 GB | 100 Mbps unmetered | $36.90 | Annual | [Order LAX.AN4.T1.WEE](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |
| LAX.AN4.T1.TINY | 1 | 1 GB | 20 GB | 4 Gbps / 2000 GB | 200 Mbps unmetered | $6.90 | Monthly | [Check T1.TINY availability](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |
| LAX.AN4.T1.STARTER | 1 | 2 GB | 40 GB | 10 Gbps / 4000 GB | 200 Mbps unmetered | $12.90 | Monthly | [Order LAX.AN4.T1.STARTER](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |
| LAX.AN4.T1.MINI | 2 | 2 GB | 60 GB | 10 Gbps / 8000 GB | 200 Mbps unmetered | $21.90 | Monthly | [See T1.MINI plan details](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |
| LAX.AN4.T1.MICRO | 4 | 4 GB | 80 GB | 10 Gbps / 16000 GB | 500 Mbps unmetered | $32.90 | Monthly | [Order LAX.AN4.T1.MICRO](https://www.dmit.io/cart.php?region=los-angeles&generation=an4&aff=12046) |

The T1.WEE at $36.90/year is the single cheapest thing in the entire AN4 catalog, and it's the plan most commonly bought for relay boxes, CI runners, monitoring nodes and non-China-facing services. If your traffic is mostly European or North American, paying for Pro or EB is money spent on routing you won't use.

## The promo plans that appear and vanish: WEE, MALIBU, CORONA

Alongside the regular plans, DMIT periodically drops limited numbered promo boxes under names like Pro.WEE, Pro.MALIBU and EB.WEE. Reported configurations have included 1 vCPU / 1 GB / 20 GB with 1 TB of traffic on a 1 Gbps port, at prices around $39.90 to $49.90 per year. They are restocked in small batches, sell out quickly, require no coupon, and are gone for months at a time. Pro.WEE has been listed with 500 GB of traffic rather than 1 TB in at least one campaign, so the specs aren't consistent between drops.

Treat these as opportunism, not a plan. If you find one in stock, the price-to-spec ratio is excellent. If it's sold out, refreshing won't help.

## AN4 vs AS3 vs AN5: which platform to actually buy

This is the decision that matters more than the platform tag itself, and the situation has shifted repeatedly.

DMIT suspended AN5 sales when hardware costs spiked, re-listed the older AN4 as a transitional platform at AN5-level price points, then also brought the even older AS3 hardware back into production and raised AN4 and AN5 pricing. The stated direction is that AS3 will be the value tier that holds the low price points, while AN4 and AN5 move up-market.

So the honest summary:

- **If you want the lowest total cost** for a US box with decent ports and big traffic, AS3 is doing that job now, with entry points around $10.90/month on Premium and as little as $36.90/year on Tier 1.
- **If you specifically want AN4**, you're paying a premium for Zen 4 hardware that no longer has cheap small configurations on the Pro line. The value case is weakest at the low end and gets better as you go up, since the large AN4 plans still deliver 10 Gbps ports and heavy traffic allowances.
- **If you want the newest silicon**, that's AN5, and it comes with the highest price tag and its own availability gaps.

For most people searching "DMIT AN4" because they remember a $9.99 CN2 GIA box: that plan no longer exists in the AN4 Pro lineup. The equivalent budget slot today is an AS3 Premium or a Tier 1 plan.

## Coupons and recurring discounts worth trying

DMIT's coupon landscape is a mix of permanent recurring codes and short-lived campaign codes. The campaign codes carry names with expiry built in, so the 2025 Christmas set is almost certainly finished, though a few were set up as recurring discounts and may still validate. The ones with the best chance of working:

| Code | Applies to | Discount |
| --- | --- | --- |
| LAX-EB-LAUNCH-NON-MONTHLY-RECURRING-20OFF | LAX EB, quarterly or longer | 20% recurring |
| 2025-XMAS-LAX-PRO-EB-10-OFF-RECURRING | LAX Pro / EB, any regular plan | 10% off + 5% cashback, recurring |
| 2025-XMAS-LAX-PRO-EB-ANNUALLY-STARTER-AND-HIGHER-15OFF-RECURRING | LAX Pro / EB annual, STARTER and above | 15% off + 10% cashback |
| 2025-XMAS-LAX-T1-10-OFF-RECURRING | LAX Tier 1, excluding WEE | 10% off + 5% cashback |
| 2026-... check the order page | Varies | Varies |

Two practical notes. Month-to-month billing is usually excluded from these codes, so you need to select quarterly or annual for most of them to apply. And the discount validation happens at checkout, after you pick a billing cycle, so the code field will tell you the truth well before you pay.

DMIT also runs a standing structure where annual billing on some lines is discounted by around 10 percent without any code at all.

## Refund terms, payment methods, and the stock problem

A few operational details that don't show up in plan tables.

**Payment:** Alipay, PayPal and credit cards are all supported. That matters if you're buying from mainland China.

**Refunds:** DMIT's refund policy is on the strict side. Third-party writeups describe a full refund within 3 days as long as you've used under 30 GB of traffic, then a pro-rated refund within 30 days. Verify the current terms on the official policy page before you order, and if you're considering an annual AN4 plan, buy monthly first and confirm the routing actually performs the way you need.

**Stock:** This is the real risk. AN4 capacity has been described by DMIT as close to exhausted, with indications that it will eventually be discontinued without expansion. Restocks happen in batches and sell out within hours. MEDIUM has been unavailable. The old cheap Pro tiers aren't coming back. Whatever you see in the table above may be gone next week, and that cuts both ways: it argues for acting on a plan you actually want, and it argues against buying an annual term on a platform with an unclear runway.

**Testing:** Before committing, use DMIT's public Looking Glass endpoints for the LAX Pro, EB and T1 profiles to check latency and loss from your own location. It's a better use of ten minutes than reading another benchmark post.

## Which AN4 plan for which job

Concrete recommendations, based on the verified specs above rather than vague "it depends":

- **Non-China traffic, tight budget:** LAX.AN4.T1.WEE at $36.90/year, or T1.MINI at $21.90/month if you need more headroom and a bigger port. The 200 Mbps post-cap throttle means a traffic spike won't take you offline.
- **China-facing site, mixed carrier audience:** EB is the better value. EB.MINI gives 4 cores, 10TB and a 10 Gbps port for $58.80/month, against Pro's 5TB at the same core count for more money.
- **China Telecom-heavy audience:** Premium (Pro). The all-three-carrier CN2 GIA return path is the product. MINI at $72.90/month is the entry point now, so budget accordingly.
- **Sustained heavy transfer:** EB.MICRO at 14TB or EB.MEDIUM at 30TB will cost you less per TB than the equivalent Pro plans, and both are on 10 Gbps ports.
- **You wanted the $9.99 box:** buy AS3 instead. That plan doesn't exist on AN4 anymore.

One last thing worth saying plainly: the "AN4" tag describes a CPU platform, not a quality tier. A T1 plan on AN4 hardware is still an international-transit box with no China optimization, and no amount of Zen 4 silicon changes that. Pick the network profile first, then decide whether the AN4 specs justify the price over AS3 for your workload.
