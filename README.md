# unmanaged linux vps hosting: what you actually run yourself, why the $5 headline rarely survives renewal, and when a $29 China-route box pays off

An unmanaged Linux VPS is a virtual machine with root access and nothing else bolted on. The provider keeps the power, the hypervisor and the network alive; you own the operating system, the packages, the firewall, the backups and whatever happens at 3 a.m. That's the entire product. The harder question is which one to buy, because the category now stretches from $4.99 boxes in a dozen generic datacenters to $29-and-up machines sold almost entirely on how fast they reach mainland China.

> **Quick take:** if your users sit in China, or you need low latency *from* China, the place to start is GoMami's Pulse line — Nano is $29/mo in Tokyo, Singapore and Los Angeles, $49/mo in Hong Kong, and every plan ships with root, VNC and rescue mode. If you just want a cheap Linux box in Frankfurt, its pricing runs roughly five times the category median and you should buy something else. [👉 Check GoMami's current plan pricing](https://bit.ly/Gomami)

## What does "unmanaged" actually leave you holding?

Everything above the hypervisor. The provider delivers power, network, RAID storage and a working VM; you deliver the operating system, the control panel, the patches, the monitoring and the recovery plan.

The split hosting.com publishes on its own product pages is the clearest version of this I've seen:

| Job | Unmanaged VPS | Managed VPS |
| --- | --- | --- |
| Root access / OS choice | You | Provider |
| OS and control panel updates | You | Provider |
| CPU, disk, uptime monitoring | You | Provider |
| Security patching | You | Provider |
| Proactive sysadmin support | Not included | Included |
| Backups | Optional add-on | Usually daily, included |
| SLA | 99.9% (power/network) | 99.95%+ |

Hostwinds states the support boundary even more bluntly in its FAQ: on an unmanaged plan it will "ensure your VPS can start up and is functional with the power, networking, and connection," and "will supply no other assistance or support." That's not a knock on Hostwinds — it's the definition of the product you're buying.

Two things follow from that. First, the price gap between managed and unmanaged is really a salary line: you're paying yourself, in hours, instead of a support team. Second, "unmanaged" doesn't mean "bare." Most large hosts still layer panel-level conveniences on top — Hostwinds includes snapshots, a real-time monitoring service that opens a ticket when something breaks, and nightly backups to its object storage. The label describes who fixes a broken nginx config, not how many buttons the dashboard has.

## What unmanaged Linux VPS hosting costs in 2026

The median is still in single digits. CloudsPress tracks 329 unmanaged hosts for its 2026 ranking and puts the median entry price at **$5.95/mo**, with a median renewal of **$7.99/mo** across the 41 hosts that publish renewal pricing; 16 of those hosts never raise the price at all.

The headline number is also the least reliable one. Hostinger's KVM 1 is listed at $6.49/mo during a promotional period and renews at $11.99/mo on a 24-month term — an 85% jump at renewal. Its KVM 4 goes from $12.99 to $28.99. Hostwinds starts its unmanaged Linux line at $4.99 with 1Gbps ports, SSD storage, snapshots and custom ISO support. Those are all real prices; they're just priced for a specific moment in the customer lifecycle.

So when you compare a $5 box to a $29 box, you're comparing two different purchases:

- **$5–8/mo** buys commodity compute in a generic location, with renewal risk and a wide feature set at the panel level.
- **$29+/mo** buys a specific network path. In GoMami's case, that path is China Telecom CN2 + China Unicom AS9929 + China Mobile CMIN2, with return routing chosen automatically based on your source IP.

If your application doesn't care about the route, the second purchase makes no sense. San Francisco to Frankfurt is a solved problem; Shenzhen to Los Angeles at 8 p.m. is not.

## Where GoMami fits, and the one word its documentation never uses

GoMami Networks is a China-route specialist, not a budget host. Its homepage leads with "RTT <50ms across mainland China," DDoS mitigation capacity up to 600 Gbps, and single-core benchmark claims. Its entry price is **$29/mo** for a Nano instance in Tokyo, Singapore or Los Angeles — roughly five times the category median — and $49/mo in Hong Kong.

Here's the honest wrinkle: **GoMami's own docs never call its product "unmanaged."** What they do describe is a KVM virtual machine with root, a VirtFusion control panel, VNC console, rescue mode, password reset, OS rebuild on demand, and no managed-service layer. That's functionally identical to an unmanaged Linux VPS. Treat "GoMami is unmanaged" as an accurate description of the service, not a quote from the company.

What you actually get for the premium, per the docs:

- **Triple-network direct routing** — CN2 for Telecom, AS9929 for Unicom, CMI for Mobile, with multi-upstream redundancy and automatic failover.
- **Published typical latency** — Hong Kong under 30ms, Tokyo under 50ms, Singapore under 70ms to mainland China. The docs are upfront that real numbers vary by ISP, time of day and local conditions.
- **Node guidance by audience** — South China users go to Hong Kong; North China users can use Japan or Hong Kong; all-China audiences go to Hong Kong; Southeast Asia goes to Singapore; game acceleration goes to Hong Kong.

Worth knowing before you commit: the official Locations & Network page lists only Hong Kong, Japan and Singapore. A full Los Angeles Pulse line exists on the store, and third-party trackers and reviewers have covered it since it launched in mid-2026, but it isn't in the network documentation. If LA is your target, verify the route yourself rather than trusting the docs page.

## GoMami's full plan list, line by line

The catalogue runs from a $29 Nano to an $899 dedicated box. The tables below cover every plan currently shown on GoMami's store pages, grouped by product line.

**Pulse** is the general-purpose line: EPYC 7763 for Hong Kong and Singapore, EPYC 7773X/7K83 in Japan. Same specs and same price in Tokyo and Singapore; Hong Kong costs more.

| Plan | Specs | Hong Kong | Japan | Singapore | Order |
| --- | --- | --- | --- | --- | --- |
| Nano | 2 vCPU / 2GB / 40GB NVMe · 500GB | $49 | $29 | $29 | [ Order](https://bit.ly/Gomami) |
| Mini | 2 vCPU / 4GB / 60GB NVMe · 1TB | $59 | $49 | $49 | [ Order](https://bit.ly/Gomami) |
| Air | 4 vCPU / 8GB / 80GB NVMe · 2TB | $119 | $89 | $89 | [ Order](https://bit.ly/Gomami) |
| Pro | 8 vCPU / 16GB / 100GB NVMe · 5TB | $269 | $169 | $169 | [ Order](https://bit.ly/Gomami) |
| Ultra | 12 vCPU / 32GB / 300GB NVMe · 10TB | $499 | $338 | $338 | [ Order](https://bit.ly/Gomami) |

Ports vary more than the specs table suggests: Pulse runs 1Gbps up to the Air tier, with 3Gbps on Pro and Ultra in Hong Kong, Japan and Singapore. Japan's Mini is the odd one at 1.5Gbps.

**LAX.Pulse** trades latency for bandwidth — the Titan plan carries 30TB and a 10Gbps port.

| Plan | Specs | Traffic | Port | Price | Order |
| --- | --- | --- | --- | --- | --- |
| Nano | 2 vCPU / 2GB / 40GB | 1TB | 1Gbps | $29 | [ Order](https://bit.ly/Gomami) |
| Mini | 2 vCPU / 4GB / 60GB | 2TB | 1Gbps | $59 | [ Order](https://bit.ly/Gomami) |
| Air | 4 vCPU / 8GB / 80GB | 4TB | 2Gbps | $129 | [ Order](https://bit.ly/Gomami) |
| Pro | 6 vCPU / 16GB / 100GB | 8TB | 3Gbps | $259 | [ Order](https://bit.ly/Gomami) |
| Ultra | 12 vCPU / 32GB / 300GB | 15TB | 5Gbps | $599 | [ Order](https://bit.ly/Gomami) |
| Titan | 12 vCPU / 32GB / 600GB | 30TB | 10Gbps | $999 | [ Order](https://bit.ly/Gomami) |

**HKG.Turin** is the performance flagship — Hong Kong only, more NVMe per dollar than Pulse, and Windows-ready on the top two tiers.

| Plan | Specs | Traffic | Port | Price | Order |
| --- | --- | --- | --- | --- | --- |
| Mini | 2 vCPU / 4GB / 100GB | 1TB | 2Gbps | $69 | [ Order](https://bit.ly/Gomami) |
| Air | 4 vCPU / 8GB / 140GB | 2TB | 2Gbps | $129 | [ Order](https://bit.ly/Gomami) |
| Pro | 6 vCPU / 16GB / 180GB | 5TB | 5Gbps | $299 | [ Order](https://bit.ly/Gomami) |
| Ultra | 12 vCPU / 32GB / 220GB | 10TB | 5Gbps | $599 | [ Order](https://bit.ly/Gomami) |

**HKG.Peak.X5** (Ryzen 9 9950X) and **HKG.Forge** (dedicated hardware) round out the catalogue. Note that GoMami's own product overview lists only Turin, Pulse and Forge — Peak X5 exists on the store but isn't in that document, and the store page doesn't display prices.

| Plan | Specs | Traffic | Port | Price | Order |
| --- | --- | --- | --- | --- | --- |
| Peak X5 Mini | 2 vCPU / 4GB / 40GB | 1TB | 2Gbps | $59* | [ Order](https://bit.ly/Gomami) |
| Peak X5 Air | 4 vCPU / 8GB / 60GB | 2TB | 2Gbps | $99* | [ Order](https://bit.ly/Gomami) |
| Peak X5 Pro | 6 vCPU / 16GB / 80GB | 5TB | 5Gbps | $199* | [ Order](https://bit.ly/Gomami) |
| Forge Mini | EPYC 7663, 56C/112T, 128GB / 960GB | 10TB | 2Gbps | $599 | [ Order](https://bit.ly/Gomami) |
| Forge Air | EPYC 7663, 56C/112T, 256GB / 4TB | 20TB | 2Gbps | $899 | [ Order](https://bit.ly/Gomami) |

\* Peak X5 pricing isn't shown on the store page; the figures above come from third-party records, including a $59 launch price reported in an August 2025 review. Confirm before ordering.

Two pricing notes that will save you a support ticket. GoMami's homepage shows a six-plan block — Ryzen 9 9950X at $59/$99/$199 and EPYC 7763 at $39/$79/$169 — without saying which node or product line each belongs to, and those numbers don't match the per-node store prices above. And the figures in these tables come from plan-tracking sites and reviewer records checked in October 2026, not from a price field on the store page. **Confirm the total on the order page for your node before you pay.** [👉 Compare the current GoMami plan prices](https://bit.ly/Gomami)

## The fine print that decides whether $29 is a good deal

The refund window is 24 hours, and it's narrower than that sounds. GoMami refunds new purchases within 24 hours of activation, once per user, back to the original payment method. Renewals don't qualify. Neither do instances terminated for terms-of-service violations, nor IPs that got blackholed by a DDoS attack. Approved refunds delete the instance and its data immediately, so back up first. Alipay refunds land in 1–3 business days, cards take 5–10.

Compare that with the 30-day money-back guarantee Hostinger advertises on its VPS line, and the 24 hours stops looking like a trial period. If your migration takes a weekend, you've spent the window before you've tested anything.

The DDoS picture is similar: the marketing number and the operational number are different things. Default protection is free and best-effort, applied automatically with no configuration. The 600 Gbps scrubbing service is a **paid add-on** you have to arrange with support. And if an attack on your IP starts affecting other customers on the same network segment, the system null-routes you for 30–60 minutes, releases it automatically, and won't let anyone lift it early. During that window all inbound and outbound traffic to your IP is dropped. If you're running anything where a 45-minute blackout is unacceptable, that belongs in your architecture, not your support ticket.

Traffic overages are handled more gracefully than most. You can buy top-up packs instead of upgrading the plan: 100GB for $6, 1TB for $60, 5TB for $300, up to 20TB for $1,200. On the Forge dedicated servers, overage is billed at $0.06/GB instead.

Three more items the marketing pages don't lead with:

- **Backups aren't specified.** The control panel has a Storage tab that references disk management and backups, but the docs don't state whether they're included, how often they run, or how long they're kept. Ask before you depend on them.
- **No published uptime SLA.** The documentation covers hardware, network and billing in detail; an uptime commitment isn't among them.
- **Terms of service are strict on resource abuse and botting.** Intentional overuse of bandwidth, CPU time or disk IO, and botting on platforms like TikTok, lead to termination without refund. The acceptable use policy also makes you responsible for anything done through your account, including by people you've given access to.

## Picking a node: three numbers and a five-minute test

Start with distance, then verify. GoMami publishes typical latency of under 30ms for Hong Kong, under 50ms for Tokyo and under 70ms for Singapore, and its own guidance maps cleanly onto geography: southern China → Hong Kong; northern China → Japan or Hong Kong; nationwide → Hong Kong; Southeast Asia → Singapore; game servers → Hong Kong.

That last one is the least surprising recommendation in the document. A Hong Kong box is physically closest to mainland players and gives you the lowest round trip, which is why the Hong Kong Pulse Nano costs $20/mo more than the Tokyo and Singapore equivalents.

The docs also tell you to test before buying, which is rarer than it should be: ping, traceroute and a download test from your own connection to each candidate node, then pick. Do that at the hour your users are actually online — an evening peak test tells you more than a 9 a.m. one. If you're targeting China broadly and can't test, Hong Kong is the default answer; if you're on a budget and serving Southeast Asia plus southern China, the $29 Singapore Nano is the cheaper entry.

## Ordering, delivery, and the parts of the panel you'll actually use

Buying is a five-step flow: pick the node and product line from the left sidebar, choose a plan, confirm specs and billing cycle on the Configure page, enter a promo code on the cart page if you have one, then check out. Payment options are credit card via Stripe, Stripe Alipay with CNY support, and crypto including USDT. Deployment is automatic and typically finishes in a few minutes, with the IP and login credentials arriving by email.

Billing runs monthly, quarterly, semi-annual or annual. GoMami's docs say annual billing saves 15–20% versus monthly, with quarterly and semi-annual sitting somewhere in between. There's no published renewal price to compare against, which is worth noting given how much of the budget-hosting market funds itself through renewal jumps.

Day-to-day you'll live in the VirtFusion panel. Six tabs: Overview shows running state, IPv4, OS and kernel version, creation date, and live memory/CPU/network usage against your traffic quota; Options holds the VNC console, rescue mode, root password reset and hostname settings; Rebuild reinstalls the OS from the top toolbar. Network handles reverse DNS and resolvers. Beyond the panel there are three self-service tools worth knowing about: you can change your public IP yourself, buy traffic packs without touching your plan, and push an instance to another user's account.

If you've read this far and the route is what you need, the Hong Kong Pulse Mini at $59 is the sensible default for a China-facing workload — 2 vCPU, 4GB, 60GB NVMe, 1TB of traffic — and the $29 Tokyo or Singapore Nano is the cheap way to test whether the network delivers what the docs promise. [👉 Start with a GoMami Nano and test the route yourself](https://bit.ly/Gomami)

## When the $5 box is the smarter buy

Most of the time, honestly. If your users are in Europe or North America, or you're running a side project that nobody in Shenzhen will ever load, the China-route premium buys you nothing.

| Provider | Unmanaged entry | Renewal | What's in the box |
| --- | --- | --- | --- |
| Hostwinds | $4.99/mo | Not published | 1Gbps ports, SSD, snapshots, nightly backups, real-time monitoring, custom ISOs, one-click upgrade to managed |
| Hostinger | $6.49/mo (KVM 1) | $11.99/mo on 24-month term | 1 vCPU / 4GB / 50GB NVMe / 4TB, weekly backups, 30-day money-back guarantee |
| GoMami | $29/mo (Nano, JPN/SIN/LAX) | Not published | 2 vCPU / 2GB / 40GB NVMe, CN2 + AS9929 + CMIN2 routing, best-effort DDoS protection, 24-hour refund window |

The trade-offs aren't subtle. Hostwinds gives you a support floor — it'll tell you the VM is powered on and the network works — plus nightly backups and a one-click path to managed if you decide you want help later. Hostinger gives you the longest refund window of the three and a much larger machine for the money. What neither sells is a specifically engineered path to mainland China, and no amount of panel features closes that gap.

The honest version: **buy GoMami when latency from China is the product requirement.** Buy a $5–8 box when it isn't. Paying $29 for a commodity VM in Tokyo and then complaining about the price is a self-inflicted problem.

## FAQ

**Is GoMami an unmanaged host?**
Functionally, yes. You get root, VNC, rescue mode and OS rebuilds, and there's no managed-support tier. GoMami's own documentation doesn't use the word "unmanaged," so treat it as a description of what the service is rather than an official classification.

**Do I need Linux experience to use it?**
Yes. Nothing in the purchase flow installs a control panel or configures a firewall for you. If you can't comfortably handle SSH, system updates and a rescue-mode recovery, budget for the learning curve or pick a managed plan elsewhere.

**What happens when I hit my traffic limit?**
GoMami sells self-service traffic packs so you can top up without upgrading your plan — 100GB for $6 up to 20TB for $1,200. The docs don't spell out an automatic cutoff behaviour, so buy the pack before you're at zero rather than after.

**Can I get a refund if I don't like it?**
Within 24 hours of activation, once per user, on a first purchase only. Renewals, ToS terminations and DDoS-blackholed IPs are excluded, and approved refunds wipe the instance immediately.

**Is DDoS protection included?**
Best-effort scrubbing is free and automatic on every instance. The 600 Gbps professional scrubbing tier is a paid add-on arranged through support. Large attacks that affect neighbouring customers trigger a 30–60 minute blackhole that nobody can lift manually.

## How to choose, in one pass

Serving mainland China users and want the lowest latency → Hong Kong Pulse, starting at the $49 Nano. Same audience, tighter budget → Tokyo or Singapore Nano at $29 and accept roughly 20ms more. Running CPU-bound work like a game server or compiler jobs → Turin, where $69 gets you 100GB of NVMe on a 2Gbps port. Need a single-tenant box with all 56 cores → Forge. Need a cheap Linux VM for a European or American audience → none of the above; a $5–8 unmanaged plan is the correct purchase.

Two things to do before you pay: open the order page for the exact node you want and read the total there, since the homepage block and the store prices don't agree; and if you're testing rather than committing, remember the refund window is 24 hours, not 30 days. [👉 Check the current GoMami plan list and order page](https://bit.ly/Gomami)
