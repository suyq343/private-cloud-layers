# Private cloud hosting solution: which layer you're buying, what the quote leaves out, and when bare metal beats a VPC (with a quote checklist)

A private cloud hosting solution is infrastructure reserved for a single organisation, and buyers mean three different things by that phrase: dedicated hardware a provider runs for you, a software platform you install in your own racks, or a control plane that deploys applications into infrastructure you already own. Spin Servers sells the first in bare-metal form, with dedicated servers and private networking quoted per configuration instead of sold as fixed plans.

That shapes how you have to compare it. Spin Servers does not publish private cloud prices. Its listed dedicated servers start at **$79/month**, and the private cloud itself is a custom quote built from servers, network capacity and optional management. For scale on the managed side, UpCloud lists its dedicated private cloud from **$3,669/month** for a single compute node, with storage billed separately at **$0.097 to $0.25 per GB per month**. Two very different price structures, and the gap between them is mostly about what is included.

> **Quick view**
>
> - **Dedicated hardware, US facilities, custom network design, no platform licence:** Spin Servers bare metal private cloud, quoted per configuration. Listed dedicated servers start at **$79/month**. 👉 [Request a Spin Servers private cloud quote](https://bit.ly/Spinservers)
> - **A provider-managed VMware platform sold through a partner channel:** a sovereign cloud provider such as Copaco.
> - **Cloud services on your own site with a hyperscaler control plane:** AWS Outposts, Azure Stack Hub, Oracle OCI Dedicated Region.
> - **You already have racks and cloud accounts and only need a deployment workflow:** an application control plane such as Northflank BYOC.
> - **No hard data-residency requirement:** public cloud plus an isolated VPC is cheaper.

## What Spin Servers actually builds for you

Spin Servers' private cloud is a cluster of dedicated servers reserved for your organisation, connected by private networking rather than a shared virtual network. The base connectivity is dual 10Gbps links, with 40Gbps, 100Gbps and custom options for larger workloads. On top of that you can add network engineering support on an ongoing basis, hardware firewalls in managed or unmanaged form, and dedicated connectivity to AWS, Google Cloud or Azure if part of the workload should stay in a public cloud.

The scope split is set in the quote. Spin Servers states that the scope of management and your team's responsibilities are agreed as part of the custom quote, which is the sentence to pay attention to. "Managed firewall" and "network management" are optional line items, not bundled features, so two quotes for the same hardware can differ substantially in what your team still has to operate. Expansion is planned rather than instant: additional servers and network capacity depend on hardware and connectivity availability at the time.

The company also draws a line its own marketing could blur. A VPS is a virtual machine on shared physical infrastructure; the bare metal private cloud uses dedicated servers reserved for one organisation. That distinction matters because the VPS line is where the visible prices are.

## The configurations Spin Servers lists publicly

The private cloud page sells a quote, not a plan. The pre-built dedicated configurations in the store are the closest thing to a public price list, and they are what the private cloud clusters get built from.

| Configuration | Specs | Monthly transfer | Price (USD) | Billing | Order |
| --- | --- | --- | --- | --- | --- |
| Bare Metal Private Cloud | Dedicated server cluster, private networking, optional managed firewall and cloud connectivity | Dual 10Gbps standard; 40/100Gbps options | Custom quote | Monthly | [Get the current quote](https://bit.ly/Spinservers) |
| Single Xeon E3-1280 v5, Dallas | 4 vCPU / 32 GB RAM / 1 TB NVMe | 30 TB | **$79/mo** | Monthly | [Check this configuration](https://bit.ly/Spinservers) |
| Single Xeon E3-1280 v5, San Jose | 4 vCPU / 32 GB RAM / 1 TB NVMe | 30 TB | **$79/mo** | Monthly | [Check this configuration](https://bit.ly/Spinservers) |
| Dual Xeon Gold 6148, Dallas | 40 vCPU / 256 GB RAM / 3.84 TB SSD | 30 TB | **$235/mo** | Monthly | [Check this configuration](https://bit.ly/Spinservers) |
| Dual Xeon Platinum 8173M, Dallas | 56 vCPU / 512 GB RAM / 7.68 TB SSD | 30 TB | **$390/mo** | Monthly | [Check this configuration](https://bit.ly/Spinservers) |

Prices are the listed starting prices on the store page; custom builds and other locations are quoted. All configurations are monthly.

There is also a KVM VPS line, from 6 vCPU and 8 GB RAM with 120 GB RAID-10 SSD and 8 TB of transfer up to 32 vCPU and 32 GB RAM with 500 GB SSD and 20 TB. Those run on shared physical hosts, so they are not a private cloud. Only one price is published on that page, **$74.00/month** for 16 vCPU, 16 GB RAM, 320 GB SSD and 15 TB of transfer; the rest are shown in the store. One operational detail worth knowing before you buy either: port 25 is closed by default on every VPS, and opening it requires a ticket with a justification that the company can refuse.

## Three layers, and the one you actually need

Comparisons that put AWS Outposts, Azure Stack Hub, Google Distributed Cloud, Oracle OCI Dedicated Region, Civo Private Cloud and VMware Cloud Foundation in a single list are grouping products that are not interchangeable. They sit at different layers, and buying a layer above or below what you need is the most expensive mistake in this category.

**Hardware layer.** AWS Outposts is AWS-managed hardware installed at your site and connected back to an AWS Region. Oracle OCI Dedicated Region is an Oracle-operated region inside your data centre. UpCloud's dedicated private cloud gives you exclusive AMD EPYC compute hosts with hardware-level isolation, up to 500 VMs per node on the largest tier, across 15 data centres. Spin Servers sits here too, with the difference that nothing ties the design to a hyperscaler's service catalogue; the private network is sized around your racks.

**Platform software layer.** VMware Cloud Foundation combines virtualisation, Kubernetes, storage and networking on hardware you or a partner owns. Copaco delivers that as a partner-only sovereign cloud on VCF 9 in six data centres across the Netherlands and Belgium, with dedicated resource domains and ISO 27001 plus ISAE 3400/3402 attestations. Astra Cloud Platform is the same idea in a different regulatory universe: an on-premise platform deployed inside a closed perimeter, certified against Russian requirements (ФСТЭК, ГИС К1, ИСПДн УЗ-1) and aimed at government systems and banks that need an isolated environment.

**Application control plane.** Northflank connects to AWS, Google Cloud or Azure accounts you already own, or to existing Kubernetes clusters including on-premises and bare metal, and handles builds, deployments, preview environments and GPU workloads. Its own documentation is explicit that it is an application control plane, not a rack or a data centre, and that with bring-your-own-Kubernetes the cluster lifecycle stays with you.

Where you buy determines what you sign. Hardware layer means a lease plus a connection plus a facilities obligation. Platform software means licences, plus a hardware owner who has to stay compatible with the vendor's roadmap. Control plane means a software subscription over infrastructure you already pay for. Spin Servers sells the first, and its optional management is how far up the stack it will go for you.

## What a private cloud quote tends to leave out

The advertised entry price is usually the compute node, nothing else. UpCloud publishes three node tiers with 64, 64 and 32 cores and 1,920 GB, 1,280 GB and 640 GB of memory, all from **$3,669/month**, and allocates storage separately:

| Storage type | Price |
| --- | --- |
| MaxIOPS block storage | **$0.25/GB/mo** |
| Standard block storage | **$0.097/GB/mo** |
| Archive block storage | **$0.065/GB/mo** |

Run the arithmetic on a realistic deployment. Ten terabytes of standard block storage is 10,240 GB at $0.097, or about **$993/month**, on top of the $3,669 node. That is roughly 1.27 times the advertised starting price before you have added a second node for redundancy, support, or migration work. UpCloud throws in zero egress fees and a two-month free migration window; those are the two line items that most often turn up as surprises elsewhere.

Apply the same four checks to any quote, including Spin Servers':

1. **Storage.** Is it included, priced per GB, or sized to the server's local disks? Local NVMe in a dedicated server is a different cost model from network block storage you can detach and resize.
2. **Traffic and IPs.** The listed Spin Servers dedicated configurations include 30 TB of transfer per month. Ask whether private cloud quotes carry the same allowance, what overage costs, and how many IPv4 addresses are included.
3. **Support and your own labour.** UpCloud's own page suggests partners when in-house DevOps capacity is short. Spin Servers prices network management and managed firewalls as options. Either way, someone has to patch, monitor and answer pages at 3am.
4. **Spare capacity.** One node is not a private cloud, it is a server. Redundancy doubles the compute line, and disaster recovery testing adds a second site's worth of capacity you hope never to use.

👉 [Ask Spin Servers what the quote includes before you compare it to anyone else](https://bit.ly/Spinservers)

## VPC is not a private cloud

A VPC is a logically isolated network inside a public cloud. It does not mean the physical hosts underneath are yours. If your requirement says the hardware must be dedicated, or the environment must run disconnected, you need dedicated hosts or a separate deployment, and that should be written into the agreement rather than assumed from the word "private". The existence of Outposts, OCI Dedicated Region and bare metal offerings like Spin Servers' is the proof: nobody would buy dedicated hardware if a VPC gave the same isolation.

## Connected or air-gapped

This is an architecture question, not a checkbox. Google Distributed Cloud ships connected, air-gapped and software-only variants that are not interchangeable, and Azure Stack Hub's disconnected deployments are a subset of its supported scenarios rather than a toggle. An environment that reaches out for updates, identity and monitoring needs a management path; a fully disconnected one needs its own update, backup and recovery chain, sized and staffed separately.

Spin Servers treats public cloud connectivity as optional, which is the right default for this decision: you can connect the cluster to AWS, Google Cloud or Azure, or leave it isolated on private networking and manage it yourself.

## Compliance follows the contract, not the label

Buying something called a private cloud does not make you compliant. Compliance depends on the requirements that apply to you, what the service agreement actually commits to, and how the environment is configured and operated: who can access it, how long logs are retained, where keys live, what encryption is enforced, where data resides, and how recovery is tested. Copaco's ISO 27001 and ISAE 3400/3402 attestations cover its platform and processes, not your configuration on top of it. Ask for the clause, not the badge.

One contractual risk worth flagging if you are building on VMware: Copaco states that Broadcom's partner programme changes require hardware to be owned only by Pinnacle partners in future, and that continued use requires VCF 9 compatibility assessed per component. That is a channel partner's account of a vendor policy and it reflects its own commercial position, so treat it as a claim to verify with your own supplier rather than an industry fact.

## When private cloud is the wrong purchase

Skip it if your workload fits comfortably on a handful of shared instances, if no regulation or contract requires data residency or physical separation, or if nobody on your team can own patching, backup and incident response. A public cloud account with a properly segmented VPC and tight identity controls will cost less and break less often. The honest test is simple: if the monthly cost of one dedicated node exceeds your entire current compute bill, you are buying isolation you have not justified yet.

## Picking by scenario

- **Dedicated hardware in a US facility, custom network design, and no appetite for a VMware licence:** Spin Servers bare metal private cloud, quoted per configuration. Cheapest entry into genuinely dedicated hardware here is **$79/month** for a single Xeon E3-1280 v5 with 32 GB RAM.
- **A provider-managed VMware platform delivered through your own channel:** Copaco-style partner-only sovereign cloud.
- **Hyperscaler services running on your site, tied to a region:** AWS Outposts or Oracle OCI Dedicated Region.
- **An isolated environment inside a strict national certification regime:** Astra Cloud Platform or an equivalent on-premise platform.
- **Racks and cloud accounts already in place, missing deployment workflow:** a control plane such as Northflank.
- **No hard residency requirement:** public cloud with an isolated VPC.

Before you sign anything, confirm three things in writing: what "private" covers (physical hosts, network, management plane, or all three), exactly which line items the quoted price includes (storage, transfer, IPs, power, firewall management, support hours), and which clause of the agreement carries the compliance obligations you are being asked to meet.

👉 [Start with Spin Servers' private cloud page and put your requirements into a quote](https://bit.ly/Spinservers)
