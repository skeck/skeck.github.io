---
layout: post
title: "An AL-aware code review bot for Business Central (GitHub Action)"
description: "A small open-source reviewer that understands Business Central: app structure detection, permissions/entitlements, and AL Guideline hints - built for PRs on GitHub."
date: 2025-08-15
categories: [DevOps, Engineering, AI]
tags: [GitHub Actions, Code Review]
author: [skeck]
canonical_url: https://github.com/marketplace/actions/business-central-ai-code-reviewer
excerpt_separator: <!--more-->
---

I built a small GitHub Action for my employer **[@AidentErfurt](https://github.com/AidentErfurt)** that reviews AL pull requests using OpenAI, Azure OpenAI or OpenRouter.ai and some Business Central context out of the box.

Yes, there are plenty of "AI reviewers". This one is opinionated for BC:
- Detects **app structure** and pulls nearby files (like `app.json` and docs) as context.
- Surfaces **permissions/entitlements** changes and missing coverage.
- Adds hints from the **[AL Guidelines](https://alguidelines.dev/)** and links the relevant sections.
- Keeps noise down (inline comment cap) and runs **incrementally** on new commits.

It’s open source (Apache-2.0), and it’s not our core product, just something useful we wanted to share.

* Marketplace:<https://github.com/marketplace/actions/business-central-ai-code-reviewer> 
* Repo: <https://github.com/AidentErfurt/bc-ai-reviewer>

<!--more-->

## Why another reviewer?

Generic code reviewers don’t know AL (yet), Business Central terminology, or the usual pitfalls. This action brings a bit of **BC context** so the feedback is more relevant and less noisy. Also, and this is probably the actual reason, it's my vibe coding project 😇.

## What it does in a pull request

1. Reads the PR’s unified diff and (optionally) linked issues.
2. Automatically discovers **app roots** and adds `app.json`, nearby docs, and (optionally) permissions/entitlements to the context.  
3. Pulls **AL Guideline** docs for patterns it detects in the diff.  
4. Asks the model for a short summary + a limited number of inline comments.  
5. Posts a PR review; subsequent runs focus on **new commits** only.

## Quick start (Azure OpenAI, o3-mini)

Create `.github/workflows/bc-ai-review.yml`:

```yml
name: AI Code Review (BC)

on:
  pull_request:
    branches: [ main ]
    types: [ opened, synchronize ]

permissions:
  contents: read
  pull-requests: write
  issues: read

jobs:
  review:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0

      - name: Run BC AI Reviewer (Azure)
        uses: AidentErfurt/bc-ai-reviewer@main
        with:
          GITHUB_TOKEN:      ${{ secrets.GITHUB_TOKEN }}
          AI_PROVIDER:       azure
          AZURE_ENDPOINT:    https://<your-resource>.openai.azure.com
          AZURE_API_KEY:     ${{ secrets.AZURE_OPENAI_KEY }}
          AZURE_API_VERSION: 2025-01-01-preview
          AI_MODEL:          o3-mini

          # Optional tuning
          MAX_COMMENTS:      10
          INCLUDE_PATTERNS:  "**/*.al,**/*.xlf,**/*.json"
          AUTO_DETECT_APPS:  true
```

## What’s different (BC-specific bits)

* **App structure awareness**
  Finds the nearest `app.json` for changed files and adds relevant context automatically.

* **Permissions & entitlements**
  Highlights permission/entitlement changes and can nudge when coverage is missing.

* **AL Guideline hints**
  Pulls guideline snippets for patterns it detects in the diff (performance/locking/naming/etc.).

* **Incremental and low-noise**
  Hard cap on inline comments; focuses on new commits so you don’t re-litigate old feedback.

## Configuration you’ll probably care about

* `AI_PROVIDER` — `azure` (default), `openai`, or `openrouter`
* `AI_MODEL` — defaults to `o3-mini`
* `INCLUDE_PATTERNS` / `EXCLUDE_PATTERNS` — scope the diff so you don’t review pipelines/docs, unless you want to
* `AUTO_DETECT_APPS`, `INCLUDE_APP_PERMISSIONS`, `INCLUDE_APP_MARKDOWN` — context controls
* `MAX_COMMENTS` — 0 for “as many as needed”, or set a cap (we default to 10)

Full list is in the README.

## Privacy & data flow

The action sends **PR diffs and selected context files** to your chosen provider (Azure OpenAI by default). Keep secrets and sensitive data out of diffs/context. See provider privacy docs before using it in regulated environments.

* Marketplace: [https://github.com/marketplace/actions/business-central-ai-code-reviewer](https://github.com/marketplace/actions/business-central-ai-code-reviewer)
* Repo: [https://github.com/AidentErfurt/bc-ai-reviewer](https://github.com/AidentErfurt/bc-ai-reviewer)