# Windows Cloud Hosting: Is the Sticker Price the Real Price? Licensing, RDP Seats, Server Sizes and SpinServers' Current Lineup (Full Plan Table)

On a Windows server, licensing and the number of people who log in at once decide the bill far more often than core count does. SpinServers' pre-built machines start at **$79/month** on a monthly term: 4 cores, 32 GB RAM, 1 TB NVMe and 30 TB of transfer, in Dallas or San Jose, with Windows among the installable operating systems.

That $79 buys hardware and bandwidth. It does not automatically buy a Windows Server licence, and it does not buy a third remote desktop seat. Both change what the machine really costs per month, so they come first below, then the full plan table, sizing rules by workload, and how SpinServers sits next to the cheaper Windows hosts quoting $4 to $30 a month.

> **Fastest path to a decision**
> - One person remoting in to run business software or a bot: a 4-core / 32 GB box is more machine than you need. A 2 vCPU / 4 GB Windows VPS elsewhere at roughly $4–$30/month fits better.
> - A small IIS site, an internal app, or SQL Server with one or two concurrent users: the E3-1280 v5 at $79/month is the sane entry point.
> - Three or more people needing a desktop at the same time: add per-user RDP licensing to whatever you buy, and confirm the host sells it.
>
> 👉 [See the current SpinServers configurations and monthly prices](https://bit.ly/Spinservers)

## The current SpinServers lineup for Windows workloads

Four pre-built configurations are listed on the pricing pages, all on monthly terms, all with 30 TB of transfer and 10 Gbps ports. Two are the same chassis in different locations; the other two are proper multi-socket machines aimed at heavy virtualisation, database or multi-tenant work.

| Plan (location) | CPU | RAM / Storage | Price and term | Order |
| --- | --- | --- | --- | --- |
| Intel Xeon E3-1280 v5 (Dallas) | 4 vCPU | 32 GB DDR4 / 1 TB NVMe | $79.00/mo, monthly | [Check this configuration](https://bit.ly/Spinservers) |
| Intel Xeon E3-1280 v5 (San Jose) | 4 vCPU | 32 GB DDR4 / 1 TB NVMe | $79.00/mo, monthly | [Check the San Jose build](https://bit.ly/Spinservers) |
| Dual Intel Xeon Gold 6148 (Dallas) | 40 vCPU | 256 GB DDR4 / 3.8 TB SSD | $235.00/mo, monthly | [Check the 40-core build](https://bit.ly/Spinservers) |
| Dual Intel Xeon Platinum 8173M (Dallas) | 56 vCPU | 512 GB DDR4 / 7.7 TB SSD | $390.00/mo, monthly | [Check the 56-core build](https://bit.ly/Spinservers) |

A few things that table does not show:

- **Networking:** 10 Gbps ports as standard, 30 TB of monthly transfer on these four, one IPv4 and a /64 IPv6 block. Extra IPs, RAM and disk are sold separately.
- **Locations:** Dallas and San Jose (listed as Santa Clara in places). Dallas for general workloads; the Bay Area site is the one aimed at visitors from Asia.
- **Delivery:** standard configurations are advertised as automatic within about 30 minutes; the biggest custom builds take days.
- **Uptime commitment:** 99.99% SLA, with a public status page.
- **Payment:** cards, PayPal, Alipay and WeChat Pay are all accepted, which matters if you are buying from outside the US.
- **Renewal:** the pricing pages show a monthly rate and do not state a separate post-term rate. Month-to-month means no lock-in, but ask what the rate is after the first billing period before you commit to a long project.
- **Promo pricing:** the E3-1280 v5 also circulates on coupon roundups at $49/month. That figure assumes a discount code; the list price on the plan itself is $79. If a code fails at checkout you are back at $79, so budget from the list price.

SpinServers also sells smaller VPS tiers below this dedicated line. The prices you'll find for those online are almost always coupon-driven, so ask for the un-discounted rate before you compare them to anyone else.

## What the licence actually covers on a Windows cloud server

A hosting provider can license **Windows Server** for you. It cannot rent you desktop Windows. That single rule explains most of the confusing pricing you'll meet while shopping, because Windows 10 Pro and Windows 11 Pro images get installed unactivated and you supply your own product key after first login.

Which edition you pick matters for a second reason: Windows Server ships with two usable Remote Desktop sessions, desktop editions ship with one interactive session and no multi-user story at all. Windows Server 2025 is the default build on new servers now; 2016, 2019 and 2022 stay available for software that has not been certified on the newer release.

### The 180-day evaluation, step by step

Most budget Windows hosts, including SpinServers-style self-managed server sellers, hand you Microsoft's evaluation image rather than a pre-paid licence. The rules are the same everywhere:

1. The image installs as an evaluation build at no licence cost.
2. It must activate online within the first **10 days**.
3. It then runs fully featured for **180 days**, with the remaining days shown on the desktop.
4. After day 180 your data and installed software stay put, but the server **shuts down every hour** and only accepts security updates.
5. Adding a licence converts the installation in place. No reinstall, no migration.

Point 4 is the one that catches people. A machine you set up in spring and forget about will start powering itself off in autumn, and if it is running a scheduled job or a trading bot at the time, that is a bad afternoon. Diarise day 150.

How the licence gets priced varies by provider. Some charge per vCPU (one host publishes $6.31 per vCPU per month), some fold it into the plan price and just call the plan "Windows Server", some let you bring an existing key or Enterprise Agreement and activate the pre-installed image yourself. Whichever model you meet, the question to ask is blunt: **is the licence in this number, or is this the evaluation image?**

### Desktop Windows is a different animal

Windows 10 Pro reached end of support on **14 October 2025** and no longer receives security updates. If a vendor still advertises it for new deployments, that is legacy convenience, not a recommendation. New desktop-Windows work belongs on Windows 11 Pro, which needs at least 2 GB of RAM, or on Windows Server.

The practical difference in cost is small at the bottom of the market: one provider lists a 1 vCPU / 1 GB Windows Server Starter at $3.99/month and its smallest Windows 11 Pro build, 1 vCPU / 2 GB / 32 GB NVMe, at $4.79/month.

## RDP seats: two included, the third costs money

Every Windows Server installation gives you **two administrator sessions** over Remote Desktop. Those two are yours, at no extra charge, on any plan from any host.

From the third simultaneous user onward you need RDP user licensing. One provider publishes **$8.90 per user per month** for extra RDP users, which is a fair benchmark for what this line item looks like on an invoice. Three people sharing a server is not three times the hosting cost, but it is hosting plus one user licence, every month, forever.

Two operational details worth knowing before you buy:

- The administrator password is normally emailed at provisioning, and RDP answers on the standard port 3389 straight away.
- Ask whether the control panel includes a web KVM or VNC console. When a firewall rule or a bad RDP setting locks everyone out, that console is the only way back in without a support ticket.

## Billing: monthly, per-minute, or a 24-month intro rate

Three billing models show up in this market, and they are not interchangeable.

**Per-minute, pay-as-you-go.** True cloud platforms bill by the minute and stop charging when you delete the instance, with no minimum contract. Good for test benches, build agents, and anything with a short life. Bad if you want a predictable number on the first of the month.

**Flat monthly.** SpinServers' listed plans work this way: one price, one month, no lock-in, and the machine is yours for the term. This is the easiest model to budget and the easiest to leave.

**Intro pricing tied to a long term.** Contabo, for example, lists its Windows CLOUD VPS 6 at $29.40/month, with $27.60/month for the first 24 months; the 16-core CLOUD VPS 16 at $120.10 against $111.20 for the first 24 months; the CLOUD VPS 18 at $151.20 against $139.44. The saving on the entry plan is about $43 spread over two years, and you trade two years of commitment for it. If you cancel early, check what happens to the discount.

The general lesson: compare the **standard rate**, not the headline rate. A $27.60 sticker that reverts to $29.40 is a mild case; on other hosts the same structure runs from $3.99 to triple that at renewal. SpinServers at least keeps the term short enough that a price change is a monthly decision rather than a two-year one.

👉 [Compare SpinServers' monthly Windows-capable plans side by side](https://bit.ly/Spinservers)

## How much server do you actually need?

Configurations in this market are oversized for most buyers, so start from the workload:

- **One person on RDP, running desktop software, a bot or an emulator:** 2 vCPU and 4 GB is usually enough, 8 GB if the app is a browser automation stack. Windows 11 Pro needs 2 GB minimum; Server runs on 1 GB at the smallest tiers.
- **A small IIS site or an internal line-of-business app:** 2 to 4 vCPU, 4 to 8 GB, and put the money into NVMe instead of cores.
- **SQL Server:** memory decides performance, and licensing decides cost. Express is free but capped; Web and Standard are licensed per core, so a 40-core machine can cost more in database licences than in hosting. Size the database, not the CPU.
- **Three or more concurrent RDP users:** any reasonable size works, but add per-user licensing at roughly $8.90/user/month and confirm the host will actually sell it to you.
- **GPU, AI inference or rendering:** none of the pre-built plans above include a GPU, and that is a different shopping trip.

For a single remote worker, the 40-core and 56-core SpinServers builds are irrelevant. Even the 4-core E3 with 32 GB is generous; its value is the 1 TB of NVMe and the 10 Gbps port, not the cores.

## SpinServers vs other Windows hosts

The budget end of this market is crowded, and the honest answer is that SpinServers is not the cheapest way to get a Windows desktop. It is a hardware-per-dollar play.

| Provider | Windows entry point | Licensing model | Where it fits |
| --- | --- | --- | --- |
| SpinServers | $79/mo, 4 cores / 32 GB / 1 TB NVMe, monthly | Windows installable; confirm licence terms at order | Heavy single-tenant machines, big storage, 10 Gbps, US locations |
| MassiveGRID | $3.99/mo Windows Server Starter (1 vCPU / 1 GB); Windows 11 Pro from $4.79 | 180-day evaluation or $6.31 per vCPU; extra RDP user $8.90/mo | Single-user desktops, small IIS sites, bots, accounting software |
| Contabo | $29.40/mo CLOUD VPS 6, Windows Server included | Licence bundled into the plan | Cheap multi-core Windows VPS, 9 regions / 11 locations, 99.9% uptime, unmanaged |
| Atlantic.Net | Configurable cloud servers, Windows/Linux/FreeBSD | Pay-as-you-go or reserved instances | Compliance-sensitive work (HIPAA, PCI), US/Canada/UK/Singapore, vendor claims deployment in under 30 seconds |
| IONOS | Cloud Cubes, Windows available | Pay-as-you-go, billed to the minute | Short-lived instances, no minimum contract, ISO 27001 data centres |

Reading that table: if you need 32 GB of RAM and a terabyte of NVMe for $79, SpinServers is competitive. If you need one Windows desktop for one person, MassiveGRID at $3.99 or Contabo at $29.40 with more cores will cost less, and neither is worse for that job. If your contract mentions HIPAA or PCI, Atlantic.Net's compliance posture is the reason to look at it. If the machine exists for three weeks and then dies, IONOS's per-minute billing wins.

## Before you order

Two questions decide whether the monthly price you see is the monthly price you pay:

1. **Is the Windows Server licence included, and which version?** Evaluation image means free for 180 days, then an invoice. Bring-your-own-key means you supply the licence. Bundled means it is already in the price.
2. **How many people will log in at once, and what does seat three cost?** Two admin sessions are free everywhere. Everything above that is a monthly line item.

Then place the order against the smallest configuration that covers the workload for the next six months, not the biggest one you can afford today. Capacity is easy to add later; a licence you never needed is money gone.

👉 [Start with SpinServers' entry configuration at $79/month and scale up only if the workload asks for it](https://bit.ly/Spinservers)
