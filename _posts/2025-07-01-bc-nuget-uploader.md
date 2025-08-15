---
layout: post
title: "A small helper for getting BC .app files into NuGet"
description: "A small GitHub Action that turns committed Business Central .app files into NuGet packages, making it easy to share partner apps or integrate them into your DevOps workflow."
date: 2025-07-01
categories: [DevOps]
tags: [GitHub Actions, NuGet]
author: [skeck]
excerpt_separator: <!--more-->
---

**bc-nuget-uploader** - GitHub Action: Upload BC .app files to NuGet

[Bc-nuget-uploader](https://github.com/marketplace/actions/upload-bc-app-files-to-nuget) is a small, practical Action I wrote for my employer **[@Aident](https://github.com/AidentErfurt)** because it solved a recurring problem on real projects. If you work with Business Central and you keep getting `.app` files from different partners, this helps you put them into a NuGet feed with minimal ceremony.

<!--more-->
---

## Why NuGet

NuGet has become a first-class citizen in the Business Central DevOps toolchain. With [AL-Go for GitHub](https://github.com/microsoft/AL-Go) now supporting NuGet feeds out-of-the-box and BcContainerHelper providing production-ready cmdlets (`New-BcNuGetPackage`, `Publish-BcNuGetPackageToContainer`, etc.), the ecosystem is ready for package-based distribution. Using NuGet means you get proper versioning, dependency resolution, retention policies, and an easy way to share or consume extensions without juggling raw `.app` files.

## Why this exists

Not everyone is running AL-Go for GitHub or another managed DevOps setup. In many customer engagements you need to integrate apps from multiple vendors, and most of the time you’ll just receive compiled `.app` files (e-mail, download link, etc.). You still want the benefits of NuGet-versioning, retention, dependency resolution-without rebuilding someone else’s code.

One simple way is to create a NuGet feed (GitHub Packages, Azure Artifacts, any v3-compatible feed) and store those apps there. **bc-nuget-uploader** helps with exactly that: you **commit** `*.app` files to a repo and the Action turns them into Business Central NuGet packages and pushes them to your feed(s).

Is storing binaries in a repo ideal? **No.** It’s a little hacky. But it’s pragmatic and lets project leads upload a new version through the GitHub web UI-quick and obvious.

* Marketplace: <https://github.com/marketplace/actions/upload-bc-app-files-to-nuget>

---

## What it does

* Detect `.app` files under a folder you choose (e.g., `/upload`) and run on commit.
* Wrap BcContainerHelper cmdlets to build a NuGet package with the expected layout.
* Push to one or many feeds (GitHub, Azure Artifacts, etc.).
* Skip duplicates if the exact version already exists.

---

## How to use it

Minimal workflow (trimmed for clarity):

```yaml
name: Process uploaded .app files
on:
  push:
    branches: [ main ]
    paths:   [ 'upload/*.app' ]
  workflow_dispatch:

permissions:
  contents: read
  packages: write      # needed for GitHub Packages

jobs:
  upload-apps:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Upload BC apps to NuGet
        uses: AidentErfurt/bc-nuget-uploader@v1
        with:
          feed-map: nuget-feed-map.json     # optional, see below
          fail-on-any-error: true
        env:
          GITHUB_TOKEN:           ${{ secrets.GITHUB_TOKEN }}
          MY_NUGET_FEED_TOKEN:    ${{ secrets.MY_NUGET_FEED_TOKEN }}
```

### Multi-feed mapping (optional)

When the app `id` should go to multiple feeds, add a small JSON map:

```json
{
  "b1755fc0-be57-424a-8e0a-8533dc9122d7": [
    {
      "url":   "https://nuget.pkg.github.com/your-org/index.json",
      "token": "GITHUB_TOKEN"
    },
    {
      "url":   "https://your-azure-artifacts/_packaging/bc/nuget/v3/index.json",
      "token": "MY_NUGET_FEED_TOKEN"
    }
  ]
}
```

Each GUID is the app’s `id` from `app.json`. Add more entries as needed.

---

## Where it fits

```
Partner sends .app ──▶ commit to /upload ──▶ bc-nuget-uploader
                                         │
                                         ├─▶ GitHub Packages
                                         ├─▶ Azure Artifacts
                                         └─▶ Any v3 NuGet feed
                                                   │
                                                   ├─▶ AL-Go restore / deploy
                                                   └─▶ BcContainerHelper publish
```

* **Upstream**: no need to change your main pipeline. This is a side entrance for third‑party apps.
* **Downstream**: consumers restore from feeds; no more passing `.app` files around.
* **Governance**: use feed policies (scopes, approvals, retention) to keep things tidy.

---

## Quick start

1. Create or pick a NuGet feed (GitHub Packages or Azure Artifacts).
2. Add the workflow above.
3. Commit an `.app` to `/upload`.
4. Check that the package shows up in your feed and reference it like any other NuGet package.

