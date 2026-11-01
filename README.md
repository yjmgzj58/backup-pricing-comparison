# backup services: Real Prices From $4/Mo, What Each Plan Actually Includes, and How to Pick Between Managed Backup and S3 Storage

Most people searching for backup services want three answers: what it costs, what's actually included at that price, and whether the invoice will surprise them later. Here's the short version based on Sharktech's current published plans: managed Acronis backup starts at **$4/month** with a 200GB default configuration, S3-compatible object storage runs **$4.90/TB per month** with 1TB of bandwidth included at no extra charge, and self-managed cloud servers for running your own backup software start at **$7.95/month** (roughly $3.98/month on annual billing). No long-term contracts on any of them.

The catch, and it's a small one: the $4 entry price on the Acronis side is a floor, and the final recurring number depends on the capacity and protection options you select in checkout. This article walks through every plan, the math behind each one, and which option fits which situation.

> **Quick picks**
> - Just need an offsite copy of files, databases, or VM images? → **S3 Object Storage, 1TB for $4.90/mo**, bandwidth included.
> - Want agent-based backup with ransomware protection and a recovery console, without managing anything yourself? → **Acronis Cyber Protect, from $4/mo**.
> - Running your own backup server (Veeam, Restic, Duplicati)? → **Public Cloud Tiny, $7.95/mo**.
>
> 👉 [Compare Sharktech's current backup plans and configure yours](https://bit.ly/SharKtech)

## Sharktech backup services at a glance: every current plan

Sharktech traces its history to 2003 and, per the company, serves more than 1,000 customers across 70-plus countries from data centers in Los Angeles, Las Vegas, Denver, Chicago, and Amsterdam. Its backup-relevant offerings split into three families: managed Acronis backup, raw S3 object storage, and OpenStack-based public cloud for self-hosted backup setups. Here's the full lineup currently published:

| Plan | Type | What you get | Price & billing | Order |
| --- | --- | --- | --- | --- |
| Acronis Cyber Protect | Managed backup | Agent-based backup for Windows, Linux, macOS, VMs and mobile; web console; 200GB default config, final price set at checkout | **From $4/mo**, monthly | [Order the Acronis plan](https://bit.ly/SharKtech) |
| S3 Object Storage – 1TB | Raw storage | 1TB S3-compatible storage, redundant cluster, 1TB bandwidth included | **$4.90/mo**, monthly | [Order S3 storage](https://bit.ly/SharKtech) |
| Public Cloud – Tiny | Self-managed | Configurable NVMe/SSD/HDD storage, small scalable resource pool, 5TB outgoing traffic | $7.95/mo (≈$3.98/mo annual) | [Order Cloud Tiny](https://bit.ly/SharKtech) |
| Public Cloud – Small | Self-managed | 300GB SSD, 4 vCPU, 8GB RAM, 1 IPv4, 20TB outgoing | $39.00/mo, monthly | [Order Cloud Small](https://bit.ly/SharKtech) |
| Public Cloud – Medium | Self-managed | 800GB SSD, 8 vCPU, 16GB RAM, 1 IPv4, 20TB outgoing | $79.00/mo, monthly | [Order Cloud Medium](https://bit.ly/SharKtech) |
| Fixed-Price Cloud – XS | Self-managed | 500GB SSD, 8 vCPU, 16GB RAM, 1 IPv4, 20TB outgoing | $86.23/mo, fixed monthly | [Order Fixed XS](https://bit.ly/SharKtech) |
| Fixed-Price Cloud – S | Self-managed | 500GB SSD, 16 vCPU, 32GB RAM, 1 IPv4, 20TB outgoing | $140.95/mo, fixed monthly | [Order Fixed S](https://bit.ly/SharKtech) |

All prices are in USD. Inbound traffic is free on the Public Cloud plans; on S3, storage and bandwidth are the only two line items on the bill.

## What the $4/month Acronis plan actually gets you

The Acronis Cyber Protect plan is managed backup in the proper sense: you install an agent on each machine, and everything else runs through a web console that Sharktech hosts. The current product page describes protection for physical servers, virtual machines, and cloud workloads across Windows, Linux, and macOS — plus, per the company's knowledge base, Android devices through the Acronis mobile app.

Concretely, you get:

- **Custom schedules and retention.** You choose what gets protected, when backups run (daily or hourly both work), and how long recovery points are kept. Different machines can have different plans.
- **Granular recovery.** Restore a single file, a folder, or an entire machine from the console, picking the recovery point you want.
- **Monitoring before things break.** The console shows backup status, activity, reports, and storage consumption, so a failed job gets spotted before a recovery emergency rather than during one.
- **Built-in security features.** Acronis bundles backup with security capabilities, including ransomware-oriented protection. The exact security feature set depends on the license and options you pick at checkout, which is worth confirming if security features are your main reason for choosing Acronis.

The Acronis engine itself has a decent independent track record: PCMag rated Cyber Protect an Editors' Choice at 4.5/5, and G2's recent grid reports placed it near the top in SaaS backup and cloud security categories. Sharktech sells that same platform as a partner, packaged as a single per-storage line item instead of Acronis's usual per-workload licensing — which makes quoting much simpler when you're backing up five machines instead of one.

There's no control panel dependency either. The Acronis console is a separate platform, which matters if your servers run different stacks.

One honest caveat: capacity and protection options change the recurring price from the $4 floor. File Sync & Share and additional protection options are priced separately, and the page explicitly tells you to check the itemized selection before confirming your order. So treat $4 as the starting point, and read the checkout summary as the real number.

👉 [Configure Acronis backup from $4/month in Sharktech's portal](https://bit.ly/SharKtech)

## The invoice math that most backup articles skip

This is where Sharktech's pricing differs from the hyperscaler model, and it's the part most comparison articles gloss over.

On the S3 Object Storage plan, the bill has exactly two items: storage at $4.90/TB and bandwidth. The first 1TB of bandwidth is included at $0. As one third-party review of the service put it: "No API call fees, no per-object charges, no 'actually, that tier costs more' surprises on the invoice." The rate doesn't change with volume either — the per-TB price is the same whether you're storing 1TB or 100TB.

Why that matters: egress fees are the classic budget-killer in cloud backup. Restoring data from a major cloud provider typically triggers per-GB download charges, which means the worst possible moment to discover them is when you're recovering from ransomware or a dead server. Third-party comparisons of S3-compatible storage generally put mainstream pricing at $5–$25+ per TB before egress fees, which makes Sharktech's $4.90 with included bandwidth sit at the low end of that range — with the variable that usually blows up budgets removed.

The Acronis plan has a quirk of its own, and it's counterintuitive. Multiple third-party breakdowns of the plan agree on this structure: the 200GB base price drops as you commit to longer billing cycles — $4 monthly, $8 quarterly, $12 semi-annually, $24 annually — but the per-GB overage rate climbs the same direction, from $0.02/GB on monthly billing up to $0.12/GB on annual billing. File Sync & Share follows the same pattern, starting at $0.03/GB monthly. In practice: if your backup volume might grow past 200GB, monthly billing with the cheapest overage rate is the safer bet; if your dataset is stable at or under 200GB, annual billing costs the least overall. Do your own math in the checkout, where the itemized totals are shown before you pay.

## Managed Acronis or self-managed S3: a decision rule

Both routes protect your data, but they solve different problems, and picking the wrong one costs either money or flexibility.

Choose the **Acronis plan** if you want backups to happen without you thinking about them. It handles scheduling, retention, encryption, and gives you a recovery console with a dashboard. It fits businesses backing up servers, workstations, and even phones, where the person responsible for backups also has ten other jobs. The trade-off: capacity is bundled into the plan price, so very large datasets will scale the bill faster than raw storage would.

Choose **S3 Object Storage** if you already run backup software and just need somewhere to point it. It's S3 API-compatible, so Veeam, Restic, Duplicati, rclone, and Minio all work with it directly. You're paying for storage and nothing else — which is exactly right if you know how to configure the backup jobs yourself.

Choose a **Public Cloud plan** if you want full control of the backup environment itself: your own backup server, your own retention logic, snapshots, and the ability to download entire server disk images for offsite copies. Storage is tiered within the same plan — NVMe for hot backups, SSD for balance, HDD for cheap bulk archives — so you can mix speeds in one deployment. Tiny handles one lightweight backup server; Small and Medium fit small-business restore environments and multi-server setups; the Fixed-Price plans exist for teams that need a predictable monthly number on the invoice.

There's also a hybrid pattern worth knowing: some teams run the backup software on a cheap Public Cloud instance and push the archive copies to S3 storage, keeping fast local restores and cheap deep storage separate.

For scale context, one third-party comparison notes that another managed-hosting competitor charges roughly $11/month for 100GB of hosted Acronis backups — about $134/month at the 1TB mark — while Acronis's direct per-device licensing starts around $85 per device per year before storage. Sharktech's $4 for 200GB undercuts both on price, with the trade-off that it's a more self-service add-on than a fully managed concierge service. If you need multi-region, petabyte-scale retention with custom policies, enterprise backup vendors or hyperscaler tooling remain the better fit.

## What to confirm before you order

Sharktech publishes transparent pricing, but a few details live in checkout rather than on the marketing pages. None of these are dealbreakers; they're just the questions to settle before your card is charged.

1. **The exact Acronis total.** Capacity and protection options change the recurring price from the $4 floor. Check the itemized list in the portal before confirming — especially if you're adding File Sync & Share, which is priced as a separate optional service and adds nothing to your bill if you skip it.
2. **The security feature set you need.** Acronis bundles security capabilities with backup, but which ones apply depends on your license and workload. If ransomware protection features are the reason you're choosing this plan, confirm what your selected options include.
3. **Recovery expectations.** Recovery time depends on data size and the recovery method you choose. Sharktech's own guidance is to make recovery testing part of your operating routine — a restore you've never tested is a hope, not a plan.
4. **The refund question.** No refund policy or free trial is published on the pages reviewed here, and third-party review aggregators show a modest Trustpilot score around 3.5 from a small number of reviews, with the absence of a money-back guarantee among the recurring complaints. If a trial matters to you, ask the 24/7 support team directly before ordering. On the positive side, the same reviews highlight fast, responsive support — and support is human-led and available around the clock, including by phone.

## Frequently asked questions

**Is there a long-term contract?**
No. Sharktech states on its backup services pages that plans come without long-term contracts, and the S3 and cloud plans are billed monthly, with optional annual billing that discounts Public Cloud Tiny to roughly $3.98/month.

**Can I use my existing backup software?**
If it speaks the S3 API, yes. The object storage is compatible with Veeam, Restic, Duplicati, rclone, and Minio, plus CI/CD pipelines. The Acronis plan is the opposite approach — it brings its own agent and console.

**Can I back up phones and laptops, not just servers?**
Yes. The backup service covers servers, desktops, laptops, and mobile devices. Android backup runs through the Acronis app from Google Play, managed from the same console.

**What about ransomware?**
The Acronis plan combines backup with security features aimed at ransomware, and the whole point of an offsite copy is that ransomware encrypting your production machines can't touch it. Sharktech's FAQ cites a Truelist statistic that 70% of small businesses close after a major data loss event — their argument, and a reasonable one, is that a clean offsite backup is what lets you rebuild without paying anyone.

**What if my storage needs grow?**
The cloud storage expands automatically as usage grows, per the service description. On Public Cloud, you can scale resources up and mix storage tiers within a plan. On the Acronis plan, growth beyond your base capacity is billed at the per-GB overage rate tied to your billing cycle — which is exactly why the monthly plan's lower overage rate matters for growing datasets.

## Which plan should you actually pick?

Here's the short path through the table above:

- Backing up one or a few machines and want zero management? **Acronis from $4/mo** — pick monthly billing if your data might outgrow 200GB, annual if it won't, and verify the checkout total either way.
- Already running backup software and need a cheap, honest archive target? **S3 Object Storage at $4.90/TB**, with the first 1TB of bandwidth free so restores don't bill you twice for your own data.
- Want to own the whole backup environment? **Public Cloud Tiny at $7.95/mo** to start, annual billing if you're keeping it; move up to Small or Medium when one backup server stops being enough.
- Need petabyte scale or fully managed enterprise retention? Look at the enterprise backup vendors instead — Sharktech's plans are built for single-organization budgets, not hyperscale.

Two things worth doing in either case: run one test restore after your first successful backup, and read the itemized order summary before paying. Then, when you're ready: 👉 [check Sharktech's current backup plans and pricing](https://bit.ly/SharKtech) and pick the one that matches how much you want to manage yourself.
