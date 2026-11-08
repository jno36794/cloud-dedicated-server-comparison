# Cloud dedicated server: are you renting a whole machine, a few vCPUs, or an entire host? (full plan comparison + cost breakdown)

Four different products get sold under the name "cloud dedicated server," and the difference between them decides whether you pay VPS money or bare-metal money. Before you compare a single price, work out which one is on the table: a whole physical machine you can virtualize yourself, one instance sitting alone on a parent server, a handful of dedicated vCPUs, or an entire host billed per host.

SpinServers, the provider covered here, sells the plainest of the four. Single-tenant bare metal in Dallas, Texas or San Jose, California, provisioned in minutes, with entry configurations listed from $79/month on month-to-month billing. No hypervisor layer between you and the hardware unless you install one yourself, which the platform supports through an ESXi auto-install option alongside Linux and Windows.

The rest of this page does three things: shows every configuration currently listed, explains why the same phrase produces wildly different products elsewhere, and works out what the bill actually looks like once bandwidth, licensing and refund terms are included.

> **Most readers should start with the Dallas Xeon E3-1280 v5.** 4 cores / 8 threads at 3.7 GHz turbo, 32 GB DDR4 ECC, 1 TB M.2 NVMe, 30 TB of monthly transfer on a 10 Gbps port, one IPv4 included, auto-provisioned. At $79/month it covers a busy single site, a VPN endpoint, a game server, or a small virtualization host. Move up only when you can name the workload that needs more than 32 GB of RAM.
> 👉 [See the current Dallas configuration and price](https://bit.ly/Spinservers)

## Every SpinServers configuration currently listed

Two locations, eight published builds. Dallas runs the entry single-socket box and a 56-core dual Xeon Platinum. San Jose carries the mid and high-core count configurations, all on dual 10 Gbps ports with 30 TB of monthly transfer and instant provisioning.

| Configuration | CPU | RAM / Storage | Network | Price & billing | Order |
| --- | --- | --- | --- | --- | --- |
| Intel Xeon E3-1280 v5 (Dallas) | 4C / 8T, 3.7 GHz turbo | 32 GB DDR4 ECC / 1 TB M.2 NVMe | 30 TB on 10 Gbps, 1 IPv4 | from $79/mo, month-to-month | [Check price](https://bit.ly/Spinservers) |
| Xeon 4C / 8T (San Jose) | 4C / 8T, 3.7–4.0 GHz | 32 GB DDR4 ECC / 1 TB M.2 NVMe | 30 TB, 2 × 10 Gbps | quoted per configuration | [Check price](https://bit.ly/Spinservers) |
| Xeon 12C / 24T (San Jose) | 12C / 24T, 2.6–3.1 GHz | 64 GB DDR3 ECC / 240 GB SSD | 30 TB, 2 × 10 Gbps | quoted per configuration | [Check price](https://bit.ly/Spinservers) |
| Xeon 16C / 32T (San Jose) | 16C / 32T, 1.8–2.9 GHz | 64 GB DDR4 ECC / 1.6 TB SSD | 30 TB, 2 × 10 Gbps | quoted per configuration | [Check price](https://bit.ly/Spinservers) |
| Xeon 16C / 32T + RAID (San Jose) | 16C / 32T, 1.8–2.9 GHz | 256 GB DDR4 ECC / 2 × 1.6 TB SSD, RAID with cache | 30 TB, 2 × 10 Gbps | quoted per configuration | [Check price](https://bit.ly/Spinservers) |
| Xeon 24C / 48T (San Jose) | 24C / 48T, 1.8–2.5 GHz | 64 GB DDR4 ECC / 1.6 TB SSD | 30 TB, 2 × 10 Gbps | quoted per configuration | [Check price](https://bit.ly/Spinservers) |
| Xeon 32C / 64T + RAID (San Jose) | 32C / 64T, 2.1–3.0 GHz | 512 GB DDR4 ECC / 2 × 3.84 TB SSD, battery-backed RAID | 30 TB, 2 × 10 Gbps, 1 IPv4 | quoted per configuration | [Check price](https://bit.ly/Spinservers) |
| Dual Xeon Platinum 8173M (Dallas) | 56C / 112T, 3.50 GHz turbo | 512 GB DDR4 / 4 × 1.92 TB SSD | 30 TB, 2 × 10 Gbps LACP, 1 IPv4 | quoted per configuration | [Check price](https://bit.ly/Spinservers) |

A note on the price column. SpinServers lists configurations in detail but quotes the larger San Jose builds at order time rather than publishing a flat per-config price list, and the numbers move with hardware and stock. An independent price tracker's September 2026 snapshot recorded four headline tiers on the order pages: $79 for the 32 GB / 1 TB NVMe build, $99, $149 for 256 GB RAM with 2 × 1.6 TB SSD, and $679 for 768 GB RAM with 8 × 2 TB SSD, all month-to-month with no setup fee. Treat those as a ladder, not a quote. The order page on the day you buy is the only figure that binds.

There is no free tier and no trial, only paid service.

## Four products, one name: which one are you actually buying?

This is where most comparisons go wrong. Vendors use "cloud dedicated" for things that share almost no technical ground.

**1. A whole physical machine with a hypervisor on top.** A bare metal hypervisor is installed on the server hardware and all of it goes to a single client, who can then carve it into as many virtual machines as they want. Liquid Web describes exactly this setup and runs it on its own kernel-based virtualization stack, with servers live in minutes. You get bare metal performance plus the ability to resize your own VMs without a support ticket.

**2. One instance alone on a parent server.** In Liquid Web's other use of the term, the cloud dedicated server is the only virtual instance running on its parent machine, so it gets every CPU core of that parent. Their cloud VPS puts several instances on the same parent and each takes a share, which is why performance can dip when a neighbour spikes. Liquid Web's cloud dedicated configurations run from 14.1 GB to 121.6 GB of RAM and 391 GB to 3.22 TB of storage.

**3. A few dedicated vCPUs.** Hetzner's "dedicated" cloud plans assign vCPUs that are reserved for you alone, with no noisy neighbours, listed side by side with shared plans that spread work across the same hardware. You are not renting a machine. You are renting guaranteed CPU time on someone else's machine, and it is priced accordingly.

**4. An entire host, billed per host.** Atlantic.Net charges for the physical host and nothing for the instances running on it. Launch as many dedicated instances, at as many sizes, as the host can hold. Instance placement lets you pin a workload to a known host. The single add-on charge is Microsoft Windows Server licensing, required because Microsoft enforces license affinity on Windows Server images. Customers with existing Oracle, SQL Server or Exchange licenses can bring them along (BYOL) as long as the host has the matching physical core count. Eight data centres across the US, Canada, Asia and Europe, 100% uptime SLA.

The billing consequence is bigger than the technical one. Option 3 prices like a VPS with a premium attached. Option 4 prices like a server. Option 2 sits in between. Option 1 usually lands near bare metal pricing, because either way you are paying for the whole box.

SpinServers sells the hardware layer without the hypervisor. That makes it closest to traditional dedicated hosting with one important difference, which is that deployment is instant rather than measured in hours or days. If you want the full option-1 setup, install ESXi from the control panel and build your own VMs on top.

## Cloud dedicated vs VPS vs traditional dedicated

The three-way split comes down to who else is on the hardware and how fast you can change your mind.

|  | Cloud dedicated | Cloud VPS | Traditional dedicated |
| --- | --- | --- | --- |
| Tenancy | Single | Multiple per parent | Single |
| CPU | All cores of the parent, or your own machine | Shared cores | All cores |
| Performance consistency | High | Varies with neighbour load | High |
| Deployment | Minutes | Minutes | Longer, provisioned on demand |
| Scaling | Fast, minimal downtime | Fast | Hardware swap, data migration, DNS propagation |
| Hardware choice | Fixed to listed configurations | Fixed to listed configurations | Fully customisable |
| Redundancy | Highest | Provider-dependent | Achievable, at a cost |

Two rows matter more than the rest. Hardware customisability is the real cost of buying cloud dedicated anywhere: you pick from the provider's catalogue. A traditional dedicated server can be built to spec. The second is scaling. Liquid Web notes that resizing a traditional dedicated server involves hardware provisioning, data migration and DNS propagation, each carrying downtime, while a cloud instance scales with minimal interruption.

SpinServers sits on the traditional side of that table on hardware (you choose from eight builds) and on the cloud side on speed (instant provisioning, plus IPMI/iKVM remote management and VPC networking with private Layer 2 connectivity between your own machines).

If a page loads in three seconds and roughly 83% of visitors expect that, and an online store loses about 0.3% of conversion for every extra second according to Portent, the difference between consistent and inconsistent CPU delivery shows up in revenue, not benchmarks.

## What the bill actually looks like

Sticker price is the least reliable number in this category. Billing granularity changes the total.

**Hourly with a monthly cap.** Hetzner bills cloud products hourly on a postpaid model, and the monthly cap means the bill never exceeds the monthly price. Delete a server mid-month and you pay for the hours it ran. Servers keep billing until you delete them, and outstanding unbilled usage blocks permanent account closure.

**Per host, instances free.** Atlantic.Net charges for the dedicated host only. Launching instances, deploying instance families and running multiple instance sizes cost nothing extra. Windows Server licensing is added automatically. Monthly, one-year and three-year commitments carry discounts.

**Predictable monthly, no capital spend.** Liquid Web frames cloud dedicated as a flat monthly fee with no upfront capital expenditure and no maintenance overhead, which is the comparison that matters against on-premises hardware.

**Month-to-month with a bandwidth allowance.** SpinServers bills monthly, and the configurations above come with 30 TB of transfer on 10 Gbps ports (the headline tiers range from 10 TB to 40 TB). Month-to-month service generally carries no refund policy, so the first invoice is a commitment, not a trial.

👉 [Check the current billing terms and bandwidth allowance before you order](https://bit.ly/Spinservers)

The practical rule: divide the monthly cost by the number of dedicated cores you actually get, then add the extras that vary by provider. A $79 box with 4 dedicated cores costs about $19.75 per core-month. A $149 box with 16 cores costs about $9.30. A $679 box with 32 cores costs about $21, which is why the high-RAM configurations only make sense when memory or storage density is the constraint, not CPU.

## Limits that only show up after you order

- **Hardware is fixed to the catalogue.** No adding RAM or swapping drives on a listed build. Hetzner states plainly that custom configurations are not offered.
- **Bandwidth is shared, not guaranteed.** Hetzner's hosts run redundant 10 Gbit links shared by every instance on the host, with no guarantee and roughly 300–500 Mbit in practice. SpinServers specifies a monthly transfer allowance per server, so overage, not port speed, is the number to watch.
- **Windows licensing costs extra.** On Atlantic.Net it is added automatically per instance.
- **Two locations only for SpinServers.** Dallas and San Jose. Distance to your users hurts latency, and a CDN softens it rather than removing it.
- **No published backup or disaster recovery layer.** Power and network redundancy are covered; anything beyond that is your responsibility to architect.
- **PCI-compliant facilities, not managed PCI compliance.** Compliance work and scanning stay with you.
- **SLA percentages are not comparable across vendors.** A 100% network and power SLA at one provider and a 99.9% uptime SLA with defined credits at another measure different things. Read the credit schedule, not the headline number.

## Matching a configuration to a workload

**A single high-clock workload.** The Xeon E3-1280 v5 at 3.7 GHz handles game servers, VPN endpoints and single-site hosting better than a higher core count at lower clock speed. This is the $79 build.

**CPU-heavy databases and analytics.** The 32C / 64T build with 512 GB RAM and battery-backed RAID gives you the memory headroom to keep a working set in RAM and the write cache to survive a power event. The 24C / 48T build is the cheaper middle step.

**Agency and multi-site hosting.** The 16C / 32T with 256 GB RAM is the one to virtualize on. Install ESXi or run containers, give each client an isolated slice, and keep the core count in one place instead of spreading sites across small VPS instances.

**Private cloud and compliance-driven networking.** The dual Xeon Platinum 8173M with 112 threads in Dallas, paired with VPC private Layer 2 between your own servers, keeps internal traffic off the public interface.

**AI and machine learning.** SpinServers' published configurations are CPU, RAM and storage builds. GPU work needs a provider that lists GPU capacity explicitly, and Liquid Web sells GPU hosting for exactly that. Don't buy a 56-core box hoping it substitutes for an accelerator.

**Microservices and horizontal scaling.** Several mid-size boxes beat one giant one here, because failure domains stay small. The 12C / 24T and 16C / 32T builds are the natural units.

👉 [Pick a San Jose configuration matched to your core count](https://bit.ly/Spinservers)

## Who should not buy this

If your site gets low to moderate traffic and fits comfortably in a few shared vCPUs, a cloud VPS is cheaper and the performance difference will not be visible. Liquid Web draws that line explicitly: cloud VPS for small sites and low-to-medium traffic, cloud dedicated for CPU-intensive workloads, high-traffic sites and databases.

If your cost model depends on bringing existing Oracle, SQL Server or Exchange licences, an Atlantic.Net-style dedicated host with BYOL support fits the licensing terms better than a per-server rental.

If you need presence in many regions, SpinServers' two US locations rule it out. Atlantic.Net covers eight, Hetzner covers Germany, Finland, Singapore and the US, and no amount of CDN configuration fixes a server on the wrong continent.

And if a single hard outage would cost more than the annual contract, the 2023 Uptime Institute finding that over two-thirds of organisational outages cost at least $100,000, and IBM's 2023 average breach cost of $4.45 million, argue for redundancy you have designed rather than redundancy you have assumed.

## FAQ

**Is a cloud dedicated server the same as a dedicated server?**
Only sometimes. On SpinServers it is a physical machine, single-tenant, with instant provisioning. Elsewhere the term can mean one virtual instance alone on a parent server, or a set of reserved vCPUs on shared hardware. Ask which before comparing price.

**Can I upgrade the machine later?**
Not in place. Configurations are fixed per order, so moving up means provisioning a new server and migrating data. Plan for the next 12 months of growth when you order, not the next three.

**Hourly or monthly billing?**
Hourly with a monthly cap suits short-lived or spiky workloads, since you pay for the hours used and never exceed the monthly figure. Monthly suits steady production, and month-to-month terms keep you flexible without a multi-year commitment.

**Do I need a hypervisor?**
Only if you want to split the machine into multiple VMs. Otherwise install Linux or Windows directly. ESXi auto-install is available when you do want the cloud layer on your own hardware.

**How much does a SpinServers cloud dedicated server cost?**
Entry configurations are listed from $79/month for 4 cores, 32 GB RAM and 1 TB NVMe. Mid and high-core builds in San Jose are quoted at order time, with a September 2026 third-party snapshot putting the tiers at roughly $99, $149 and $679 per month. Confirm the figure on the order page for your location and build.

## Before you order

Match the box to the workload, not to the biggest number on the page:

- One busy site, a game server, a VPN → the 4C / 8T build at $79/month.
- Multiple client sites or a virtualization host → the 16C / 32T with 256 GB RAM.
- Database or analytics with a large working set → the 32C / 64T with 512 GB and battery-backed RAID.
- Licence-heavy enterprise software → look at a dedicated host model with BYOL instead.
- Low traffic, tight budget → a cloud VPS is the honest answer.

Two things to confirm before the card comes out. First, what "dedicated" means in the product you are buying: a whole machine, one instance on a parent, or reserved vCPUs. Second, the numbers that never appear in the headline price: monthly transfer allowance and overage rate, Windows licensing if you need it, and the refund policy, since month-to-month service here generally does not come with one.

👉 [Start with the Dallas entry configuration at SpinServers](https://bit.ly/Spinservers)
