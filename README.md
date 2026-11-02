# vps for minecraft server: how much RAM you actually need, what a year should cost, and how to get one running today

Most people searching for a vps for minecraft server need less than they think: a 2 GB RAM VPS with 2 CPU cores runs a vanilla server for 5–10 players comfortably, and on RackNerd's current annual special that costs **$35.99 for the whole year** — about $3/month. Modded servers are a different story; Forge and Fabric packs routinely want 4 GB or more. This article covers which specs matter, RackNerd's full current plan lineup, what the server really costs across multiple years, the limitations that only show up in the terms of service, and the exact setup steps.

> **Quick picks**
> - Vanilla or light plugins, up to ~10 friends → **2 GB KVM special, $35.99/year**
> - Modpacks (Forge/Fabric/ATM) or 15+ players → **4 GB special, $59.99/year**
> - Just experimenting, 1–4 players → **1 GB special, $21.99/year**
>
> All five annual specials renew at the same price for as long as you keep the service — the discounted rate is not a first-term teaser. [👉 Check the 2GB annual special at $35.99/year](https://my.racknerd.com/aff.php?aff=11397&pid=953)

## What actually matters when choosing a VPS for a Minecraft server

CPU single-thread performance matters more than anything else on the spec sheet. Minecraft runs most of its game logic — chunk simulation, entities, redstone — on one main thread, so a VPS with two fast cores will feel smoother than one with six slow cores at the same RAM. RAM comes second: the JVM needs room for the world, plugins, and mods, and it can't borrow memory it doesn't have. Storage speed matters least for a small server; a standard SSD is fine, though NVMe helps with chunk loading on busy worlds.

Latency is the spec nobody checks until their friends complain. Minecraft is a real-time game, and a server 3,000 km from your players adds lag no hardware upgrade can fix. RackNerd lets you deploy in multiple locations — Los Angeles, San Jose, Utah, Dallas, Chicago, New York, Atlanta, Ashburn, and Toronto in North America, plus European cities like Amsterdam and Dublin depending on the plan. Pick the datacenter closest to where most of your players live. If your group is spread across both US coasts, somewhere central like Chicago or Dallas is usually the reasonable compromise.

One more thing worth knowing before you compare plans: RackNerd's VPS lines give you a KVM virtualized machine with **full root access, a 1Gbps port, and one IPv4 address** on every plan. That means you can install any server software — vanilla, Paper, Spigot, Forge, Fabric — with no restrictions on mods or plugins, and no per-player slot limits.

## RackNerd's current VPS plans at a glance

These are the five annual KVM specials currently listed on RackNerd's specials page. Every plan includes the same core features: KVM virtualization, full root access, 1 IPv4, 1Gbps port, and deployment in multiple datacenters.

| Plan | RAM / vCPU | Storage | Monthly transfer | Price | Order |
| --- | --- | --- | --- | --- | --- |
| 1 GB KVM VPS | 1 GB / 1 vCPU | 20 GB SSD | 3 TB | $21.99/yr | [Order the 1GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=952) |
| 2 GB KVM VPS | 2 GB / 2 vCPU | 35 GB SSD | 5 TB | $35.99/yr | [Order the 2GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=953) |
| 4 GB KVM VPS | 4 GB / 3 vCPU | 60 GB SSD | 7 TB | $59.99/yr | [Order the 4GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=954) |
| 6 GB KVM VPS | 6 GB / 6 vCPU | 100 GB SSD | 12 TB | $89.99/yr | [Order the 6GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=955) |
| 8 GB KVM VPS | 8 GB / 7 vCPU | 150 GB SSD | 20 TB | $119.99/yr | [Order the 8GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=956) |

The 1 GB plan is flagged "Most popular" on the specials page, mostly because it's the entry price for self-hosting in general. For a Minecraft server specifically, 1 GB is the bare minimum — fine for two or three players on a vanilla world, tight beyond that.

RackNerd also sells standard monthly KVM plans (the 1 GB tier lists at $17.99/month and the 2 GB tier at $20.59/month on the standard price list, per third-party reviews). Those exist for workloads that genuinely need month-to-month flexibility. A Minecraft server that stays up 24/7 is the opposite of that, so for this use case the annual specials win by a wide margin — [👉 here's the full specials page if you want to compare every option](https://bit.ly/RacKnerd).

## What a Minecraft VPS really costs per year

The sticker price is misleading in your favor this time. RackNerd's own FAQ states it directly: "These RackNerd VPS specials are lifetime recurring. You can renew at the same rate for as long as you decide to keep the service." So the 2 GB plan is $35.99 in year one, $35.99 in year two, and so on — roughly $3/month forever, not a $3 teaser that renews at $12.

Compare that to the monthly plans and the gap gets absurd. A 2 GB monthly plan at $20.59/month costs about $247 over a year — nearly 7 times the annual special's $35.99. Paying monthly for a server you intend to keep running is throwing money away.

A concrete three-year math for the two most likely picks:

- **2 GB special**: $35.99/year × 3 years = **$107.97**, about $36/year for a server your friends can join any time
- **4 GB special**: $59.99/year × 3 years = **$179.97** — still less than many managed Minecraft hosts charge for a single year at the 10–20 player tier

Third-party reviewers have noted one caveat worth repeating: the review site WebHostingBreak points out that the order flow bills the special price as an annual cycle, and recommends checking your first invoice before the renewal date. That's reasonable advice for any budget host, though RackNerd's own FAQ language on lifetime recurring pricing is unambiguous.

## The limitations nobody puts on the pricing page

RackNerd's VPS is **unmanaged**, and this is the single biggest thing to understand before ordering. You get the infrastructure; you are responsible for installing the game server, keeping Java updated, configuring the firewall, and troubleshooting crashes. Support is ticket-based, and it's for platform issues (network, hardware, panel), not "my server won't start."

Three more restrictions come from the terms rather than the marketing:

- **No money-back guarantee.** This one comes from third-party reviews rather than an official statement, so treat it as the likely state of things: unlike managed hosts with 30-day refunds, assume the annual payment is final. It's another reason to start with the cheaper tier if you're unsure.
- **Backups are your job.** The terms put data responsibility on the customer, and RackNerd recommends keeping backups off the VPS itself. A corrupted world with no backup is the classic self-hosting disaster; a weekly copy of your world folder downloaded to your own machine costs nothing and prevents it.
- **Fair use applies.** Outbound DDoS, crypto mining, and brute-force activity are prohibited, and sustained abuse of disk I/O or CPU can get flagged. A Minecraft server with a dozen players is nowhere near these limits, but it's why you shouldn't plan to run a mining operation "on the side."

One Java-specific trap: never allocate more RAM to the Minecraft process than the VPS has. On the 2 GB plan, giving the JVM all 2 GB leaves nothing for the operating system, and the kernel will eventually kill the process mid-game. Allocate around 1.5 GB on the 2 GB plan and let the OS breathe.

## How much RAM your server needs

RackNerd's own tutorial recommends at least 1 GB RAM and 2 CPU cores for roughly 4 players, which matches what long-term users report. Community experience fills in the rest of the curve, and the pattern is consistent: vanilla Minecraft is cheap on memory, modpacks are not.

| Setup | Players | Minimum RAM | RackNerd plan that fits |
| --- | --- | --- | --- |
| Vanilla, default settings | 1–5 | 1–2 GB | 1 GB ($21.99/yr) or 2 GB |
| Vanilla + light plugins (Essentials, WorldEdit) | 5–15 | 2–4 GB | 2 GB ($35.99/yr) |
| Paper/Spigot community server | 10–20 | 3.5–4 GB | 4 GB ($59.99/yr) |
| Forge/Fabric modpacks (ATM, FTB) | any | 4–6 GB | 4 GB minimum, 6 GB comfortable |
| Heavy modpacks, 30+ players | 30+ | 6–8 GB+ | 6 GB ($89.99/yr) or 8 GB |

If you're at a boundary, remember that view distance is a free performance dial: lowering it in server.properties noticeably reduces CPU and memory load, and one LowEndTalk user reported running a server on a 2.5 GB VPS "with no noticeable lag" after tuning settings. If a heavy modpack is your actual plan, don't talk yourself into 2 GB — [👉 the 4GB special at $59.99/year is the floor for Forge-tier setups](https://my.racknerd.com/aff.php?aff=11397&pid=954).

## Setting up the server: the actual steps

Deployment is automatic — after payment you'll get a welcome email within a few minutes containing your IP, root username, and password. RackNerd's control panel (called ctrl) handles reinstalls, root password resets, and includes an HTML5 VNC console if SSH ever breaks.

One honest warning: RackNerd's own blog tutorial on installing Minecraft dates from 2021 and tells you to install `openjdk-14` and download the server jar from an old S3 link. The method is still conceptually correct, but those specifics are outdated. Here's the current version of the same process on Ubuntu or Debian:

1. **SSH in and update**: `ssh root@your-ip`, then `apt update && apt upgrade -y`
2. **Install a current Java runtime**: `apt install openjdk-21-jdk-headless -y` — verify with `java -version`. (Java 21 is the current LTS; version 14 from the old tutorial is long dead.)
3. **Make a directory and download the official server jar** from Mojang's official server download page into it
4. **Accept the EULA**: open `eula.txt`, set `eula=true`
5. **Install screen** (`apt install screen`) so the server keeps running after you close SSH, then start it:
   `screen java -Xms1024M -Xmx1536M -jar server.jar nogui`
   Adjust the `-Xmx` value to your plan, leaving headroom for the OS — and never more than the VPS total. Reconnect later with `screen -r`.
6. **Open the port**: allow TCP 25565 in your firewall (`ufw allow 25565`)
7. **Connect**: players join using your VPS IP on the default port 25565

For anything beyond a vanilla server, swap step 3's jar for Paper (a drop-in performance-optimized server for plugins) or your modpack's server files — the rest of the process is identical.

## VPS vs. managed Minecraft hosting

Dedicated Minecraft hosting companies charge by player slots and resources — for a 10–20 player server, plan on roughly $20–$40 per month, which is $240–$480 per year. You get a game panel, one-click modpack installs, and support that will fix things for you.

A budget VPS inverts that trade. The 2 GB RackNerd special costs about $36 per year — a fraction of managed hosting — and gives you unlimited players, unrestricted mods, and root access to configure anything. What you give up is the panel and the hand-holding: updates, backups, and crash recovery are on you.

As a rule: if you've never touched a command line and don't want to learn, managed hosting earns its markup. If you're comfortable pasting a few commands (or willing to follow the seven steps above once), the VPS pays for itself within the first two months. The middle ground also exists — the ctrl panel's one-click apps include Docker + Portainer, and n8n or Coolify install comfortably from the 2 GB tier up, so you can add a free web panel alongside the game server.

## FAQ

**Does the promotional price go up at renewal?** No. RackNerd's FAQ describes the VPS specials as "lifetime recurring" — you renew at the same rate for as long as you keep the service.

**Can I run mods and any server software?** Yes. You have full root on a KVM machine, so vanilla, Paper, Spigot, Forge, and Fabric all work, with no plugin or mod restrictions and no player-slot limits.

**How many players fit on the 2 GB plan?** About 5–10 on vanilla with slightly reduced view distance. Light plugins are fine in that range too; heavy modpacks should move up to 4 GB.

**Is there a refund if I change my mind?** Based on third-party reviews, there's no money-back guarantee on the VPS specials. Treat the annual payment as final and pick the smaller plan if you're unsure.

**Which datacenter should I pick?** Whichever is closest to most of your players — Dallas for Texas and central US, Los Angeles for the West Coast, New York or Ashburn for the East. Latency matters more than any spec difference between plans.

## The final call

Small vanilla world for a handful of friends: the 2 GB plan at $35.99/year covers it with room to spare, and stays at that price on renewal. Modpack group or a growing community: skip straight to 4 GB at $59.99/year — trying to run Forge on 2 GB is a false economy. Pure tinkerer who wants to see if self-hosting is for you: the 1 GB plan at $21.99/year is the cheapest real test, and it handles 3–4 vanilla players. [👉 Set up the 1GB annual plan here](https://my.racknerd.com/aff.php?aff=11397&pid=952) if that's you — and whichever tier you pick, download a copy of your world folder the first evening, before anything can go wrong.
