---
title: "AL-Go flat compiling: the fast lane that almost got faster"
date: 2026-06-04 00:00:00 +0200
categories: [Business Central, AL-Go]
tags: [al-go, github-actions, docker, ci-cd]
---

Sometimes I do not need a full Business Central container in CI/CD. I just want a fast answer to one question: does it compile and if yes, please deploy it.

That is where AL-Go's "flat compiling" mode is really useful. With [`useCompilerFolder`](https://github.com/microsoft/AL-Go/blob/main/Scenarios/settings.md#usecompilerfolder) and `doNotPublishApps` enabled, the pipeline can act as a lightweight compile lane: no publish, no tests, no full container-based validation. Just a much faster signal for pull requests or feature branches.

But there is one annoying detail: AL-Go for GitHub still runs Docker commands in the Windows CI/CD path, even when those two settings mean that no container should be needed for the actual compile. In [`RunPipeline.ps1`](https://github.com/microsoft/AL-Go/blob/main/Actions/RunPipeline/RunPipeline.ps1), it calls `Assert-DockerIsRunning` and starts a background `docker pull` for the generic image before the later flat-compilation exit path is reached.

So the fast lane is nice, but it still expects Docker to be there.

That naturally leads to the next idea: GitHub custom images for larger runners. Custom images became available in public preview in October 2025 and are generally available since March 2026. In theory this would be perfect for AL-Go: pre-warm the runner with Business Central artifacts, compiler folders, generic images, and probably even Docker images on top.

The catch is the base image.

The standard GitHub runner images, such as `windows-latest`, are documented in the [actions/runner-images](https://github.com/actions/runner-images) repository and already come with a long list of installed tooling. That is exactly the kind of image I would like to extend.

But in practice, this runs into the Docker problem again. During the custom-image preview, [Freddy](https://github.com/orgs/community/discussions/177495) pointed out the practical blocker: the partner/base images did not include Docker, and installing the Windows container feature plus Docker in one workflow was not possible.

So the current chain looks like this:

Flat compiling would be a great fast lane. A custom GitHub runner image could make it even faster. But AL-Go still expects Docker, and creating a usable Windows custom image with Docker support is blocked by the image-generation limitations.

Conclusion for now: unfortunately, this is not really usable for AL-Go for GitHub yet :(.
