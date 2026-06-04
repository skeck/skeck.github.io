---
layout: post
title: "Business Central AL Development in GitHub Codespaces"
date: 2026-06-04
tags: [Business Central, AL, GitHub-Codespaces, VSCode]
description: GitHub Codespaces for AL development in Business Central is now production-ready. A practical overview of setup, benefits, and current caveats.
excerpt_separator: "<!--more-->"
---

On April 1st, Microsoft published official Learn documentation for using GitHub Codespaces for AL development in Business Central.

That is a nice milestone. A few years ago, community experiments with AL in the browser were still limited. Some things did not work, or needed workarounds because the AL extension was not really ready for Linux-based environments. That has changed. Native Linux support for the AL extension makes Dev Containers and Codespaces much more realistic today.

The basic idea is simple: add a `.devcontainer/devcontainer.json` to your repository and let GitHub create a ready-to-use VS Code environment in the browser.

<!--more-->

Good starting points are:

- [Microsoft Learn: Use GitHub Codespaces for AL development](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-code-spaces-al)
- [BCApps devcontainer example](https://github.com/microsoft/BCApps/tree/main/.devcontainer/BCApps)
- [Tobias Fenster's earlier Codespaces experiment](https://tobiasfenster.io/al-development-in-a-github-codespace-with-sources-in-an-azure-devops-repo)
- [Stefan Maron on AL, Linux, Dev Containers and Codespaces](https://stefanmaron.com/posts/al-on-linux-devcontainers-codespaces/)

## What You Get

My first impression: it works quite well for normal sandbox development. The environment comes pre-loaded with AL, PowerShell, and the usual GitHub tooling without installing anything locally.

The real wins are simplicity and consistency. Every developer gets the same environment right away, which is especially useful for onboarding. No more "works on my machine" problems.

## The Preview Extension Catch

There is one caveat: preview development.

If you work with preview sandboxes or preview containers, you usually need the prerelease AL extension. The Microsoft BCApps example uses the prerelease AL extension and also enables the new VS Code authentication setting:

```json
"al.useVsCodeAuthentication": true
```

At the moment, there is still an open authentication bug with the prerelease AL version. Connecting to sandboxes outside your own tenant (?) can fail.

I found that authentication was unreliable. Sometimes it worked, sometimes it didn't. Here's what helped:

1. Run **AL: Clear Credentials** (from the command palette)
2. Reload the VS Code window
3. Download symbols again to trigger the sign-in flow

If your Microsoft account appeared in the VS Code **Accounts** menu (bottom-left corner), authentication usually worked afterwards :).

## Current Status

GitHub Codespaces for Business Central is already very usable with the stable AL extension. For preview work, keep an eye on the [open AL issue #8223](https://github.com/microsoft/AL/issues/8223).
