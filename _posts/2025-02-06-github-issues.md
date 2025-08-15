---

layout: post
title: "Planning the Work: Jira, Azure DevOps, or GitHub Issues"
description: "Planning with Jira/Azure Boards/GitHub Issues, and practical migration tips."
date: 2025-02-06
categories: [DevOps, Planning]
tags: [GitHub Issues, Jira, Azure DevOps, AL-Go]
author: [skeck]
excerpt_separator: "<!--more-->"
---

No DevOps loop is complete without a reliable planning tool. For most teams this boils down to one of three options.

<!--more-->

## The options

### 1) Jira

Mature workflows, heaps of integrations, and fine-grained control. You can wire it to GitHub via webhooks and apps so issues, PRs, and deployments show up where you need them. Great if you want deeply customised flows and already live in the Atlassian ecosystem.

### 2) Azure DevOps (Boards)

Boards is part of Microsoft’s end-to-end DevOps suite. You can connect GitHub repos so PRs, commits, and build status sync into Boards. It shines for enterprises that want prescriptive processes and change control. The trade-off is that process templates are heavier; mid-project changes aren’t as casual as flipping a switch.

### 3) GitHub Issues

Historically simpler, but since **January 2025** GitHub has rolled out **sub-issues** and **issue types** (public preview in January, GA in April). Sub-issues give you a parent/child hierarchy; issue types let you standardise how work is named and tracked across repos. Together with improved search and Projects views, it’s a credible planning option on its own now. ([The GitHub Blog][1], [GitHub Docs][2])

## So... which one?

It depends on your governance needs, what your org already uses, and how much ceremony you want around process. If you’re already on GitHub, and especially if you’re using **AL-Go for GitHub**, keeping planning and code in one place keeps the surface area small. AL-Go itself is built and maintained on GitHub and slots neatly into that workflow. ([Microsoft Learn][3], [GitHub][4])

My bias: **GitHub Issues**. It’s flexible, the learning curve is shallow, and it adapts as the project evolves-change issue types, add custom fields, and tweak workflows without a big “process migration” exercise. Azure Boards is excellent for regulated environments, but for typical BC work it can feel heavier than needed.

## Migrating work items (if you’re moving to GitHub)

If you want to consolidate planning on GitHub:

* **APIs** - Both Jira and Azure DevOps expose solid REST APIs for exporting and transforming data.
* **Existing tools** - For Azure DevOps → GitHub Issues, Josh Johanning’s open-source migrator is a practical starting point. Expect to do some mapping (states, users, labels) and review attachments/links after the first dry run. ([GitHub][5], [josh-ops][6])

## Bottom line

All three tools integrate well with GitHub. If you want deep, centralised process control, Jira or Azure Boards are safe bets. If you value simplicity and tight coupling to your repos-and you’re already using AL-Go-GitHub Issues is good enough for most BC teams now, with room to grow thanks to issue types and sub-issues. ([The GitHub Blog][1])

[1]: https://github.blog/changelog/2025-01-12-evolving-github-issues-public-preview/ "Evolving GitHub Issues (public preview) - GitHub Changelog"
[2]: https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/adding-sub-issues "Adding sub-issues"
[3]: https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/al-go/algo-overview "Overview of AL-Go - Business Central"
[4]: https://github.com/microsoft/AL-Go "microsoft/AL-Go: The plug-and-play DevOps solution for ..."
[5]: https://github.com/joshjohanning/ado_workitems_to_github_issues "Migrate Azure DevOps work items to GitHub Issues"
[6]: https://josh-ops.com/posts/migrate-azure-devops-work-items-to-github-issues/ "Migrate Azure DevOps Work Items to GitHub Issues"
