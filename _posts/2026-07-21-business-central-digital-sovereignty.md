---
title: "Business Central and Digital Sovereignty: How Much Room to Maneuver Is Left?"
date: 2026-07-21 00:00:00 +0200
lang: en
permalink: /posts/business-central-digital-sovereignty/
categories: [Business Central, Digital Sovereignty]
tags: [business-central, digital-sovereignty, cloud, ai-agents, mcp, on-premises]
description: "How sovereign can Business Central remain across On-Premises, cloud, AI agents, MCP, GitHub, and Azure telemetry?"
---

> Deutsche Version: [Business Central und digitale Souveränität: Welchen Spielraum gibt es (noch)?](/posts/business-central-digitale-souveraenitaet/)

Self-determination and reducing our dependence on Big Tech are certainly among the most important challenges of our time. I still consider this question fundamental in the Business Central world as well. At the same time, the conditions are changing so quickly that it is becoming increasingly difficult to keep track of the overall picture.

Business Central On-Premises is still available. Microsoft's strategic direction is nevertheless clear: the cloud transformation is considered complete, and visible product innovation is now focused heavily on AI features and AI agents. With the [Universal Code initiative](https://www.microsoft.com/en-us/dynamics-365/blog/it-professional/2022/10/28/the-dynamics-365-business-central-universal-code-initiative-is-live/), announced in 2021 and activated in 2022, Microsoft already made the cloud-optimized extension architecture the norm for new on-premises installations as well. Several Bridge to the Cloud promotions have supported the move to Business Central Online for years. Since April 2025, new customers can no longer obtain Business Central On-Premises as a perpetual license, but only under a [subscription model](https://techcommunity.microsoft.com/t5/business-applications-for/simplifying-licensing-across-our-smb-erp-solutions-don-t-miss/m-p/3808035). Microsoft therefore keeps On-Premises formally open while clearly steering the commercial and technological model toward cloud and subscription.

Organizations running Business Central On-Premises control the Service Tier, SQL database, network, and backups. But as soon as AI features, AI agents, telemetry, or modern DevOps processes enter the picture, a growing part of the architecture moves outside their own playing field. The usual question, “SaaS or On-Premises?”, therefore often falls short. Strategically, this is not a black-and-white decision. It requires a close look at the individual layers: Which parts can organizations continue to operate themselves, replace, or move into a European operating environment without abandoning Business Central as their ERP platform?

Where Microsoft uses open interfaces, standards, or open source, alternatives remain possible in principle. The decisive question, however, is not only whether a service can be accessed, but whether the service behind the interface can also be replaced or run in a different operating environment. As long as central platform services—such as the execution of AI agents, telemetry analysis, or parts of the development platform—are provided exclusively by the vendor, a structural dependency remains. The decisive sovereignty boundary therefore does not simply run between cloud and on-premises. It runs between services that remain interchangeable and services whose operation remains exclusive to the platform provider.

This matters for control-oriented or regulated organizations: the ERP core can still be operated locally or regionally. The limitation lies outside that core and affects the innovation layer. Copilot features, native AI agents, the official Business Central MCP server, parts of the Power Platform integration, the productized telemetry analysis, and GitHub-centered development processes are created primarily within Microsoft's cloud ecosystem and are either unavailable on-premises or require custom integrations.

> **The ERP core can be hosted. The innovation layer is cloud-first.**

On-Premises therefore does not solve the sovereignty question. But it preserves an important starting point: data, business logic, and central operational processes do not have to disappear entirely into the Microsoft Cloud.

## What Kind of Sovereignty Are We Actually Talking About?

In discussions about digital sovereignty, I often see three different questions mixed together.

The first concerns data protection and compliance: Where is data stored, who may access it, how are accesses logged, and which regulatory requirements can be demonstrated?

The second concerns operational and platform control: Can a service run in a different operating environment? Can the underlying platform service be operated independently or replaced? Can an organization switch model providers or run its own implementation?

The third is strategic: Who determines the product roadmap, the interfaces, and the conditions under which a central component may be used in the future?

These levels are connected, but they are not the same. A service can be well secured and operated in a fully compliant manner without being architecturally replaceable. Conversely, an open interface alone does not create a production-ready alternative.

In my view, digital sovereignty cannot be discussed only in terms of hosting and data protection. The more closely Business Central integrates with GitHub, AI, MCP, and AI-agent systems, the clearer it becomes to me that long-term dependencies increasingly arise outside the traditional ERP database.

## What Microsoft Already Addresses in Business Central Online

Anyone discussing the Microsoft Cloud and European requirements today should fairly acknowledge how much has changed in recent years. Some discussions still sound as if we were in 2019. In reality, Microsoft has invested substantially in data residency, encryption, governance, and controlled administrative access.

Business Central Online is provisioned in a selected Azure region. For European customers, the [EU Data Boundary](https://learn.microsoft.com/en-us/privacy/eudb/eu-data-boundary-learn) is also relevant. Microsoft commits to storing and processing customer data for a large part of its commercial cloud services within the EU and EFTA. Such commitments do not resolve every legal question, but they are not meaningless either. Data residency reduces transfers, simplifies governance, and creates a clearer technical and organizational boundary.

Business Central adds specific safeguards. By linking a Business Central environment to a Power Platform environment, customers can use [customer-managed encryption keys](https://learn.microsoft.com/en-us/dynamics365/business-central/admin-customer-managed-encryption-key). This does not remove encryption entirely from Microsoft's platform, but it gives customers greater control over the key lifecycle. Microsoft also documents [Customer Lockbox](https://learn.microsoft.com/en-us/dynamics365/business-central/admin-customer-lockbox) for Business Central. It allows organizations to explicitly approve or reject Microsoft support access to customer data in certain support cases and to track that access.

Identity and governance are another strength of the Microsoft ecosystem. Entra ID, Conditional Access, Privileged Identity Management, audit and compliance capabilities, and the tools in Microsoft Purview provide a level of control that many organizations could reproduce on their own only with considerable effort. This is part of a fair sovereignty assessment as well: self-hosting does not automatically mean better governance.

### The CLOUD Act Does Not Make Every Safeguard Worthless

In discussions about the [CLOUD Act](https://www.congress.gov/bill/115th-congress/house-bill/4943), I often encounter the claim that all technical and organizational safeguards are ultimately useless because US authorities could access all data anyway. I consider that conclusion too simplistic.

The CLOUD Act does not establish general real-time or direct access by US authorities to cloud systems. Among other things, it governs the conditions under which US providers must disclose data based on legally valid orders when that data is in their possession, custody, or control. The physical storage location alone therefore does not remove this possibility.

But this does not mean that data residency, encryption, access controls, key management, or Lockbox are worthless. They reduce the number of possible access paths, limit internal permissions, improve traceability, and can influence which data a provider is technically able to supply in plaintext at all. Legal review, opportunities to challenge orders, and notification rules may also apply where permitted in the specific case. The CLOUD Act is a relevant jurisdictional risk, but it is not a master key to every piece of data held by European cloud customers.

A European storage location is likewise not complete protection against government access. European states also have disclosure and surveillance powers. The meaningful question is therefore not whether every conceivable access can be ruled out in theory. What matters is which legal bases apply, which technical access paths exist, how transparent the procedures are, and which layers of protection the organization controls itself. The specific data-protection assessment therefore depends on the use case, the data being processed, and the agreed technical and organizational safeguards.

Microsoft is also trying to address the remaining uncertainty through its [European Digital Commitments](https://blogs.microsoft.com/on-the-issues/2025/04/30/european-digital-commitments/) and [Microsoft Sovereign Cloud](https://blogs.microsoft.com/on-the-issues/2025/06/16/microsoft-sovereign-cloud/) offerings. These include European operating and governance options as well as commitments to operational continuity. These measures do not change the ownership structure and do not replace an organization's own risk assessment. But they do show that the discussion should not stop at “US provider equals unprotected.”

### AI Features and AI Agents Are Treated Separately

AI requires a closer look because data flows and product commitments differ by service. Microsoft separates consumer offerings, Microsoft 365 and Dynamics Copilots, and Azure AI services contractually and technically. For [Copilot features in Dynamics 365 and Power Platform](https://learn.microsoft.com/en-us/dynamics365/faqs-copilot-data-security-privacy) and for [Azure AI services](https://learn.microsoft.com/en-us/azure/foundry/responsible-ai/openai/data-privacy), Microsoft documents product-specific commitments: prompts, outputs, and customer data are generally not used to train or improve the underlying models unless the customer or tenant administrator explicitly opts into such data use. This is an important distinction from public consumer services.

For Business Central, however, this still does not mean that every AI feature runs within the same data and operational boundaries as the ERP database. Native AI agents and Copilot features use Microsoft-provided cloud services for model access and orchestration. Which models and regions are available, which diagnostic and abuse-monitoring mechanisms apply, and which data is processed for operation depend on the particular Business Central feature being used.

The right review therefore asks more than: “Is my data used for training?” Processing region, retention, logging, model provider, tool access, and approvals are equally important.

Business Central supplements these general commitments with concrete controls. Administrators can enable or disable individual Copilot and agent features, manage user access through permissions, and—where processing takes place in another geography—allow or prevent cross-region data movement. Microsoft describes these controls in the [Business Central documentation for Copilot and agent capabilities](https://learn.microsoft.com/en-us/dynamics365/business-central/enable-ai). The currently available native AI agents also use [dedicated user identities and assigned permission sets](https://learn.microsoft.com/en-us/dynamics365/business-central/payables-agent), along with [traceable task histories and human review steps](https://learn.microsoft.com/en-us/dynamics365/business-central/supervise-agent-tasks).

These are real safeguards for data protection, governance, and secure operation. They do not change the fact that AI features and AI agents are executed within platform services provided by Microsoft.

## Models and Infrastructure: European Options in the Microsoft Stack

A similar tension appears in models and compute capacity. Europe has its own providers and open-weight models. Open weight means that the trained model weights—roughly speaking, the parameters learned during training—are available. This does not automatically make the training data, training code, or usage rights open. Europe still does not have a comparable integrated stack combining a frontier model, hyperscale compute, a global cloud, a developer ecosystem, and enterprise sales. The EU is investing in its own capacity through [AI Factories and planned Gigafactories](https://commission.europa.eu/topics/competitiveness/ai-continent_en). At the same time, Microsoft is [expanding its German data centers](https://news.microsoft.com/source/emea/2026/03/spatenstich-fuer-rechenzentrums-cluster-in-nordrhein-westfalen-microsoft-staerkt-die-digitale-infrastruktur-fuer-deutschlands-ki-zukunft/?lang=de). Both improve European infrastructure, but neither automatically changes who controls the platform, its central management services, and the product strategy.

### Microsoft and Mistral: More Choice, but Not a Fully European Stack

I find the significantly expanded [partnership between Microsoft and the French AI provider Mistral](https://www.prnewswire.com/in/news-releases/microsoft-and-mistral-expand-strategic-partnership-to-give-enterprises-and-regulated-industries-frontier-ai-they-can-control-302830228.html), announced in July 2026, particularly interesting. Microsoft plans to use several billion dollars' worth of the GPU infrastructure Mistral is building in Europe. At the same time, Mistral Medium 3.5 and OCR 4 are being offered through Microsoft Foundry, while [Medium 3.5 is also available as a model choice in Copilot Studio](https://www.microsoft.com/en-us/microsoft-copilot/blog/copilot-studio/mistral-joins-copilot-studios-growing-lineup-of-model-providers/). Selected open-weight Mistral models are also intended to run through Azure Local in customer-controlled and even fully disconnected environments.

This is more than just another model in the Azure catalog. It adds a European option at the model layer, additional European capacity at the infrastructure layer, and—at least for certain models—a genuine local or isolated operating option. In my view, that matters particularly for regulated organizations.

For Business Central, the most immediate benefit is initially outside the native AI agents. A Copilot Studio agent can connect to Business Central Online through the connector or the Business Central MCP Server and use Mistral Medium 3.5 as its model, currently still as an experimental option. For custom integrations, including On-Premises scenarios, I find [OCR 4](https://techcommunity.microsoft.com/blog/azure-ai-foundry-blog/mistral-document-ai-with-ocr-4-and-mistral-medium-3-5-arrive-in-microsoft-foundr/4529863) perhaps even more interesting: a controlled service could analyze invoices or other business documents and return the structured results to Business Central.

This still does not create complete European independence. Microsoft Foundry, Copilot Studio, and Azure Local remain Microsoft platforms, while the European compute infrastructure relies in part on Nvidia hardware. At the same time, Microsoft becomes an important distribution partner and major customer of a European model provider.

I would therefore neither celebrate the partnership as a complete European AI stack nor dismiss it as mere sovereignty marketing. It creates real additional choices within an ecosystem that remains closely intertwined across Europe and the United States. To me, that reinforces the core argument of this article: what matters is not only where a provider comes from, but which parts of a service remain interchangeable, self-hostable, and controllable over the long term.

## Development and DevOps: Openness Under Consolidation Pressure

Large parts of the development layer are open, especially compared with the C/AL and C/SIDE era: Visual Studio Code is based on the open-source Code - OSS project, [AL-Go for GitHub](https://github.com/microsoft/AL-Go) is open source, and large parts of the base and system applications developed in AL are publicly viewable in the [BCApps repository](https://github.com/microsoft/BCApps). The underlying Business Central platform, however, remains proprietary.

This mixed picture continues with coding agents. Since spring 2026, Microsoft has documented a standalone [AL MCP Server](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/al-agent-tools/al-mcp-server). It runs as a separate process and exposes AL tools such as build, compile, publish, symbol search, and diagnostics to any MCP-compatible coding agent. It is explicitly not limited to a Microsoft coding agent and can run locally or in a custom automation environment.

At the same time, the market is consolidating quickly. Continue.dev was a model-flexible coding assistant that I personally enjoyed using. The project has since been [acquired by Cursor](https://www.continue.dev/). Shortly afterward, the [agreed but not yet completed acquisition of Anysphere, the company behind Cursor, by SpaceX](https://www.sec.gov/Archives/edgar/data/1181412/000162828026043411/spaceexplorationtechnologi.htm) became public. The timing does not prove a causal connection. But it shows how quickly ownership and operator structures can change, even for tools initially perceived as open alternatives.

It is therefore all the more noteworthy that GitHub itself is reopening some room for choice in specific areas. [Copilot CLI supports custom model providers and an offline mode](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/use-byok-models), including OpenAI-compatible endpoints and locally operated models through Ollama, vLLM, or Foundry Local. Contact with GitHub servers can be prevented, provided that the model provider also runs inside the isolated environment.

This does not make GitHub Copilot sovereign as a whole. The feature applies to the CLI and not automatically to all IDE and cloud capabilities. But it shows that the model provider can be interchangeable in a specific development workflow.

For many BC partners and customers, the move from Azure DevOps to GitHub and Microsoft's AL-Go solution built on top of it has been one of the most important platform decisions of recent years. Microsoft provides a consistent, maintained DevOps path. At the same time, this creates a dependency on GitHub as a US cloud platform.

GitHub Enterprise Cloud with [Data Residency](https://docs.github.com/en/enterprise-cloud@latest/admin/data-residency/about-github-enterprise-cloud-with-data-residency), or GHE.com, expands the available options. Repositories and Actions data can be stored in a selected region, including the EU. This is a relevant data-residency option, but it is not a European developer platform. The provider and the central control and management services remain GitHub and Microsoft.

The official AL-Go repositories and templates target GitHub.com; GHE.com is therefore not currently a regular Microsoft-supported path. [Freddy](https://github.com/freddydk), the original author of AL-Go and BcContainerHelper, maintains a [downstream fork with a dedicated GHE.com scenario](https://github.com/Freddy-DK/AL-Go/blob/main/Scenarios/UsingGitHubEnterprise.md) that specifically adapts the toolchain to GHE.com. Hopefully this makes it back into the standard version :)

## MCP and AI Agents: Technically Open, Operationally Demanding

The tension is most visible with AI agents.

Microsoft integrates native AI agents deeply into Business Central Online. These AI agents handle multi-step business processes and are controlled through permissions, tasks, profiles, visible pages, and user interactions. With the [Agent SDK for AL](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/ai/ai-agent-sdk-overview), partners can define their own AI agents programmatically.

The underlying model connection and orchestration are not freely interchangeable, however. Business Central can choose between the models available in the Microsoft environment. Microsoft currently documents no way to configure an arbitrary local or European model endpoint as the model provider for the native AI agents. The expanded Microsoft-Mistral partnership does not change that for now: Medium 3.5 is available in Microsoft Foundry and Copilot Studio, but not as a freely configurable model provider for native Business Central AI agents. A significant part of the agent module is visible in AL, but central functions are presumably executed in proprietary platform services.

Anyone who therefore wants to use the native, deeply integrated AI-agent functionality is tied to Business Central Online. Custom AI integrations remain possible on-premises. They are, however, custom and investment-intensive software solutions rather than the same product feature.

It is also important to distinguish between several offerings:

- The **AL MCP Server** is a locally executable development tool for coding agents.
- The **Business Central MCP Server** exposes business data and Business Central APIs as tools and is officially documented only for [Business Central Online](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/ai/configure-mcp-server).
- The **Admin Center MCP Server**, currently in [public preview](https://learn.microsoft.com/en-us/dynamics365/release-plan/2026wave1/smb/dynamics365-business-central/connect-ai-agents-admin-center-through-mcp-server), addresses administrative and operational tasks in the Business Central Admin Center.
- **Native AI agents in Business Central** are executed by Microsoft's platform services within Business Central Online.

The Model Context Protocol (MCP) is an open standard. It allows AI applications to discover and call tools and data sources in a consistent way. The official Business Central MCP Server is nevertheless a Microsoft-hosted product endpoint. Whether it will also be made available for On-Premises in the future remains, in my view, an open question. There are indications in both directions.

Custom MCP servers are therefore an alternative. Community projects such as [SShadowS/business-central-mcp](https://github.com/SShadowS/business-central-mcp) demonstrate that this is technically feasible.

This also makes AI agents for Business Central On-Premises a realistic option in principle: a custom MCP server translates Business Central APIs into narrowly scoped business tools. An external AI-agent platform uses a local, European, or otherwise controlled model. A custom AL extension in Business Central could manage tasks, permissions, approvals, and audit information. An external service, for example based on the [Microsoft Agent Framework](https://github.com/microsoft/agent-framework) or an open-source orchestrator such as LangGraph, executes the AI-agent runs and writes the results back.

A genuinely production-ready AI-agent platform for On-Premises would nevertheless require substantial investment. It would need an AL extension for configuration and user interface, a permanently operated external service, persistent task and execution states, a controlled interface and tool layer, approvals, logging, security, idempotency, error handling, monitoring, and an update process. This option therefore makes sense primarily where model location, governance, and long-term freedom of choice justify building a proprietary or community-supported platform.

## Telemetry: The Azure Dependency Remains

For telemetry, the picture is clearer.

Business Central can send structured telemetry from both SaaS and on-premises environments to [Azure Application Insights](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/telemetry-overview). Microsoft provides [Power BI apps](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/telemetry-power-bi-app) on top of this for usage, errors, performance, and administration. In the online service, the telemetry catalog additionally covers Agent Lifecycle, AI Consumption, MCP configurations, and tool calls.

Telemetry therefore becomes an important control and analysis layer for AI agents and MCP. It shows which AI agents and tools are used, how long calls take, and where errors or unexpected behavior occur.

A custom [`IngestionEndpoint`](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/telemetry-control-cost#use-a-custom-endpoint) initially looks like an escape route. Microsoft documents that a custom endpoint can be placed in front of the standard path to filter or enrich data or forward it to another data store. This is technically relevant, but it is not a ready-made alternative telemetry platform.

The documented and productized standard path remains Application Insights. The official Power BI apps connect directly to an Application Insights resource. Replacing the entire telemetry solution therefore means operating not only a custom ingestion endpoint, but also storage, queries, alerting, dashboards, permissions, and ongoing compatibility.

That is possible, but it is not a realistic standard option for typical Business Central projects. Azure Application Insights remains the de facto standard path for Business Central telemetry.

## Not Every Dependency Has to Be Replaced

I think it is important to look at dependencies soberly. If you understand their boundaries, you can accept them consciously. If you ignore them, you often give up freedom of choice without noticing. Digital sovereignty does not mean complete self-sufficiency to me. Organizations do not have to develop every cloud feature themselves. But they should know where a second operating option exists and where it does not.

For important processes, a degradation strategy is often more useful than a blanket ban on cloud services:

- Can critical hotfixes be built if GitHub is temporarily unavailable?
- Which manual processes remain if AI features are disabled?
- Which operational information is visible without Application Insights?

The sovereignty question therefore shifts from the ERP core to the entire process chain.

## Conclusion

Business Central is neither a completely sovereign nor a completely non-sovereign product. It is a controllable ERP core with an increasingly cloud-bound innovation layer.

Microsoft now addresses traditional cloud risks much more comprehensively than some discussions suggest. European data residency, Customer Managed Keys, Customer Lockbox, Identity Governance, and enterprise commitments for AI reduce real risks. The CLOUD Act does not make these measures worthless. But it reminds us that data residency and jurisdiction are not the same thing.

In other areas, Microsoft relies on open standards and open source. This preserves options: local development tools, alternative model providers, custom MCP layers, external AI-agent platforms, and community-maintained DevOps tools.

Other options are considerably harder to exercise. The execution of deeply integrated AI agents remains part of Business Central Online. Azure Application Insights is the productized standard path for telemetry. And GHE.com with EU Data Residency is not a European platform, but a regionalized operating option from a US provider.

The central task is not to pit cloud and on-premises against each other. We need to decide, layer by layer, which dependency we consciously accept, which should be secured through a second option, and where the strategic importance justifies building a proprietary or community-supported alternative. Sovereignty does not mean having as few dependencies as possible. It means having consciously chosen the dependencies that matter.

## Further Reading

The most important primary sources and technical documentation supporting this assessment:

**Business Central, Cloud, and Governance**

- [Microsoft: Universal Code Initiative](https://www.microsoft.com/en-us/dynamics-365/blog/it-professional/2022/10/28/the-dynamics-365-business-central-universal-code-initiative-is-live/)
- [Microsoft: On-Premises licensing change from April 2025](https://techcommunity.microsoft.com/t5/business-applications-for/simplifying-licensing-across-our-smb-erp-solutions-don-t-miss/m-p/3808035)
- [Microsoft Learn: EU Data Boundary](https://learn.microsoft.com/en-us/privacy/eudb/eu-data-boundary-learn)
- [Microsoft Learn: Customer Managed Encryption Key for Business Central](https://learn.microsoft.com/en-us/dynamics365/business-central/admin-customer-managed-encryption-key)
- [Microsoft Learn: Customer Lockbox for Business Central](https://learn.microsoft.com/en-us/dynamics365/business-central/admin-customer-lockbox)
- [Microsoft: European Digital Commitments](https://blogs.microsoft.com/on-the-issues/2025/04/30/european-digital-commitments/)
- [Microsoft: Sovereign Cloud](https://blogs.microsoft.com/on-the-issues/2025/06/16/microsoft-sovereign-cloud/)
- [U.S. Congress: CLOUD Act](https://www.congress.gov/bill/115th-congress/house-bill/4943)
- [EDPB/EDPS: Impact of the US CLOUD Act on the European data-protection framework](https://www.edpb.europa.eu/documents/edpb-correspondence/edpb-edps-joint-response-to-the-libe-committee-on-the-impact-of-the_en)

**AI, MCP, and AI Agents**

- [Microsoft Learn: Copilot data security and privacy in Dynamics 365](https://learn.microsoft.com/en-us/dynamics365/faqs-copilot-data-security-privacy)
- [Microsoft Learn: Data privacy for Azure Direct Models in Microsoft Foundry](https://learn.microsoft.com/en-us/azure/foundry/responsible-ai/openai/data-privacy)
- [Microsoft and Mistral: Expanded partnership for European AI infrastructure and flexible deployment](https://www.prnewswire.com/in/news-releases/microsoft-and-mistral-expand-strategic-partnership-to-give-enterprises-and-regulated-industries-frontier-ai-they-can-control-302830228.html)
- [Microsoft Copilot Blog: Mistral Medium 3.5 in Copilot Studio](https://www.microsoft.com/en-us/microsoft-copilot/blog/copilot-studio/mistral-joins-copilot-studios-growing-lineup-of-model-providers/)
- [Microsoft Foundry: Mistral Document AI with OCR 4 and Mistral Medium 3.5](https://techcommunity.microsoft.com/blog/azure-ai-foundry-blog/mistral-document-ai-with-ocr-4-and-mistral-medium-3-5-arrive-in-microsoft-foundr/4529863)
- [Microsoft Learn: Configure Copilot and agent capabilities in Business Central](https://learn.microsoft.com/en-us/dynamics365/business-central/enable-ai)
- [Microsoft Learn: Payables Agent permissions and roles](https://learn.microsoft.com/en-us/dynamics365/business-central/payables-agent)
- [Microsoft Learn: Supervise agent activities in Business Central](https://learn.microsoft.com/en-us/dynamics365/business-central/supervise-agent-tasks)
- [Microsoft Learn: AL MCP Server](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/al-agent-tools/al-mcp-server)
- [Microsoft Learn: Business Central MCP Server](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/ai/configure-mcp-server)
- [Microsoft Learn: Admin Center MCP Server (Public Preview)](https://learn.microsoft.com/en-us/dynamics365/release-plan/2026wave1/smb/dynamics365-business-central/connect-ai-agents-admin-center-through-mcp-server)
- [Microsoft Learn: Agent SDK for AL](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/ai/ai-agent-sdk-overview)

**Development, Infrastructure, and Telemetry**

- [Microsoft Learn: Business Central telemetry](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/telemetry-overview)
- [Microsoft Learn: Power BI apps for Business Central telemetry](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/telemetry-power-bi-app)
- [Microsoft Learn: Custom telemetry ingestion endpoint](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/telemetry-control-cost#use-a-custom-endpoint)
- [GitHub Docs: Custom model providers and offline mode in Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/use-byok-models)
- [GitHub Docs: Enterprise Cloud with Data Residency](https://docs.github.com/en/enterprise-cloud@latest/admin/data-residency/about-github-enterprise-cloud-with-data-residency)
- [Freddy-DK AL-Go: GHE.com scenario](https://github.com/Freddy-DK/AL-Go/blob/main/Scenarios/UsingGitHubEnterprise.md)
- [European Commission: AI Factories and Gigafactories](https://commission.europa.eu/topics/competitiveness/ai-continent_en)
- [Microsoft: Expansion of data-center infrastructure in Germany](https://news.microsoft.com/source/emea/2026/03/spatenstich-fuer-rechenzentrums-cluster-in-nordrhein-westfalen-microsoft-staerkt-die-digitale-infrastruktur-fuer-deutschlands-ki-zukunft/?lang=de)
- [Continue: Acquisition by Cursor](https://www.continue.dev/)
- [SEC: Agreed acquisition of Anysphere by SpaceX](https://www.sec.gov/Archives/edgar/data/1181412/000162828026043411/spaceexplorationtechnologi.htm)
