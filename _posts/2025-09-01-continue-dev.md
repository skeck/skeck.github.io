---

layout: post
title: "Build an AL Coding Agent for Business Central with Continue.dev"
date: 2025-09-01
tags: [Business Central, AL, Continue.dev, Azure, GitHub]
description: A practical note on setting up an AL-aware coding agent for Business Central with Continue.dev.
excerpt_separator: "<!--more-->"
image:
  path: /assets/img/continue.png
  alt: "Continue AL Agent."
---

Creating a useful coding agent for Business Central can be tricky. AL (Application Language) is niche, so many models don't handle AL or ERP-specific flows well. Licenses can get pricey if you buy Copilot seats for every developer. And code is sensitive: partners probably need EU data residency, no training on your prompts, and GDPR/ISO-aligned processing.

A good middle path can be [Continue.dev](https://docs.continue.dev). It ships as a VS Code extension ([https://marketplace.visualstudio.com/items?itemName=Continue.continue](https://marketplace.visualstudio.com/items?itemName=Continue.continue)) and lets you choose where models run (local, self-hosted, cloud, or commercial APIs) and which ones you use. You get Chat, Plan, and Agent modes, and it can read GitHub issues to plan work or even write code. It can feel a bit rough or buggy at times, but I've seen steady improvements. Flexibility is the big win here.

<!--more-->

Since you're in the Microsoft universe anyway, spin up models with **Azure AI Foundry** and wire them into Continue. This checks the big boxes: pay-per-use (often cheaper than per-seat), the freedom to pick the best model for each task, and EU region hosting with enterprise data handling ([no training on your data per provider terms, GDPR/ISO posture](https://learn.microsoft.com/en-us/azure/ai-foundry/responsible-ai/openai/data-privacy?tabs=azure-portal)). You can then connect your GitHub org so Plan/Agent mode can pull issues and propose steps or changes.

I published a small AL agent as a starting point: [https://hub.continue.dev/aident/al-public](https://hub.continue.dev/aident/al-public). It comes with AL-tuned and gpt-5 optimized rules and example prompts. Use it as-is or click **Remix** to swap models, adjust rules, and add prompts. If you prefer OpenRouter, search the Hub for existing model definitions and add your keys: [https://hub.continue.dev/?q=openrouter\&type=models](https://hub.continue.dev/?q=openrouter&type=models).

For Azure AI Foundry, deploy three models: [**GPT-5**](https://ai.azure.com/catalog/models/gpt-5) for chat/edit/apply (good reasoning and reliable structured edits), [**text-embedding-3-large**](https://ai.azure.com/catalog/models/text-embedding-3-large) for embeddings (solid multilingual retrieval to power repo/docs search and RAG), and [**Mistral Codestral**](https://ai.azure.com/catalog/models/Codestral-2501) for fast, high-quality inline code completion in VS Code. You can find and deploy all three from Microsoft's **Azure AI model catalog** - pick an **EU region** at deploy time if you need EU data residency: [https://azure.microsoft.com/en-us/products/ai-model-catalog](https://azure.microsoft.com/en-us/products/ai-model-catalog).

Getting started is straightforward:

* register at [https://continue.dev](https://continue.dev)
* add the AL agent (or remix it)
* add API keys and a GitHub PAT as **User Secrets**

If you don't want Hub-managed models or extra logins, you can define local assistants in YAML instead: [https://docs.continue.dev/customize/deep-dives/configuration](https://docs.continue.dev/customize/deep-dives/configuration).

For a company setup, the **Team** plan (\~\$10/developer/month) lets you manage API keys and shared agents centrally. Otherwise, it also works fine if each developer keeps their own secrets.

![continue vs code extension](/assets/img/continue-vs-code.png)
