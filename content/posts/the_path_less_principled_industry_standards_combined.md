---
title: 'The Path Less Principled: A Principled Guide to "Industry Standards"'
date: "2026-04-11"
description: 'The phrase "industry standard" is often used to end conversations rather than start them. Here''s how to evaluate standards on their merit, not their popularity.'
summary: "A concise guide to evaluating industry standards: what the term actually means, the traps it sets, and a practical framework for principled adoption."
tags: ["industry standards", "the-path-less-principled", "pitfalls", "engineering practices", "trade-offs"]
categories: ["pitfalls", "engineering practices"]
series: ["The Path Less Principled"]
ShowToc: true
TocOpen: true
---

*This is a condensed version of my [three-part series on industry standards](/posts/the_path_less_principled_industry_standards). If you've already read that series, you can skip this one. If you prefer the detailed deep dive, [start here](/posts/the_path_less_principled_industry_standards).*

# Introduction

"It's industry standard."

Few phrases end technical discussions faster. The moment someone invokes it, the burden of proof shifts. Suddenly, you're not debating whether a technology fits your context. You're defending why you'd dare deviate from what everyone else does.

Let me be clear: industry standards are great. The Internet would not exist without standards like IP and TCP. Standards enable interoperability, collaboration, and innovation. We all stand on the shoulders of giants.

But when "industry standard" becomes a substitute for principled evaluation, teams adopt solutions that don't fit their context, their scale, or their actual problem. The phrase borrows legitimacy it often hasn't earned.

# What "Industry Standard" Actually Means

In the strict sense, a standard is a **de jure** construct: something governed by a formal body. Think IETF RFCs, ISO specifications, or W3C recommendations. These have defined processes, versioning, and compliance criteria.

Then there's the looser usage: **de facto** standards. These emerge through widespread adoption rather than formal governance. Git for version control. JSON for APIs. No organization certifies compliance. They became "standard" because enough people adopted them, though what counts as "enough" is conveniently never defined.

Consider the spectrum:

- **Network protocols** (Ethernet, IP, TCP) — clearly formal standards
- **Application protocols** (DNS, HTTP) — formal standards
- **Architectural styles** (REST, microservices) — widely adopted, no governing body
- **Data formats** (JSON, Protobuf) — some formalised, some de facto
- **Specific tools** (Kubernetes, Terraform, ArgoCD) — just... popular?

As you move up this stack, the term gets fuzzier. Calling TCP an industry standard is uncontroversial. Calling Kubernetes "industry standard"? That's murky. And the layer on top, like ArgoCD vs. Flux for GitOps? Now we're just picking favourites.

The conflation is the problem. Calling something "industry standard" borrows legitimacy from de jure standards while often meaning just "widely adopted." Real standards solve interoperability. "Standards" in the loose sense often just mean popular. And popular is not the same as appropriate.

# The Pitfalls of Blind Adoption

When we treat "popular" as synonymous with "standard," we stop evaluating and start deferring. Predictable problems follow:

## Context Collapse

What works for Netflix doesn't work for a 10-person startup, and vice versa. Teams routinely adopt technologies without asking whether they share the same constraints as the people who built or popularised them.

Kubernetes is the canonical example. Teams adopt it because "everyone uses it" without asking: Do we have the operational expertise? Does our scale justify the complexity? Many teams would be better served by a managed platform or straightforward virtual machine deployments. But "we run on Kubernetes" sounds more impressive than "we deploy to EC2 instances."

The opposite pattern is equally dangerous. Cron jobs are the "standard" way to schedule tasks: simple, universal, battle-tested. Until you need retries, dependency management, and failure alerting. Teams stretch cron well past its design limits because it's familiar, then wonder why their workflows are a black box of silent failures.

## Cargo Culting Legitimacy

"Industry standard" becomes a rhetorical shortcut to avoid justification. Teams choose tools based on what's trending rather than what fits. The reasoning isn't "this solves our problem well." It's "this is popular, looks good on a resume, and feels modern."

You'll hear that skills are transferable and that nobody gets blamed for picking the obvious choice. These aren't wrong, but they're business and people considerations, not evidence of technical fit. Presenting them as technical justification is arguing in bad faith.

## Hidden Costs Ignored

The "standard" path is often justified as cost-saving. But hidden costs accumulate: upstream changes you don't control, forks you have to maintain, workarounds for a tool that doesn't quite fit. Meanwhile, the cost comparison still assumes the vanilla off-the-shelf version.

The "standard" path also has invisible prerequisites: team size, operational expertise, supporting infrastructure. Adopting without these doesn't give you the benefits. It gives you the complexity without the payoff.

# Not All Standards Are Equal

Before evaluating whether to adopt a standard, you need to understand the traps the term sets.

## THE Standard vs. A Standard

When someone says "X is industry standard," do they mean X is *THE* standard or *A* standard? We often hear the former when the latter is more accurate.

Git is *THE* standard for distributed version control. But GitHub vs. GitLab vs. Bitbucket? Those are each *A* standard for hosted Git. Kubernetes might be *THE* standard for container orchestration at scale, but ArgoCD vs. Flux for GitOps? Those are competing as *A* standard with different trade-offs.

Treating something as *THE* standard shuts out alternatives. Asking whether something is *A* standard opens space for nuance.

## Standards Change. Your Decision Doesn't.

De facto standards are ever-evolving. Look at the [CNCF Cloud Native Landscape](https://landscape.cncf.io/). Projects rise, plateau, and decline. What's "standard" today may not be tomorrow.

But engineering decisions happen at a specific point in time. A choice that was "industry standard" three years ago might look questionable today. This means the current popularity of a standard is weaker evidence than we tend to treat it as.

## Whose Industry? Which Context?

An infrastructure engineer and a frontend developer will have completely different lists of "industry standards." A startup and an enterprise will disagree on what's standard for their scale.

Invoking "industry standard" without specifying *whose* industry and *which* context is often meaningless. Evaluation has to start from your constraints, not from a universal ranking of popularity.

# Build vs. Follow: A False Dichotomy

I frequently hear alarm bells whenever in-house development is proposed: "Why aren't we following industry standards?"

But **in-house development is not mutually exclusive with industry standards.** A custom service that speaks HTTP, serializes with Protobuf, deploys via standard CI/CD pipelines, and exposes Prometheus metrics is following industry standards. It's just not using an off-the-shelf implementation.

The question isn't "build vs. buy." It's: **What problem are we solving, and what's the right tool for this context?** Sometimes that's off-the-shelf. Sometimes it's off-the-shelf with significant customization. Sometimes it's something built in-house that leverages standard building blocks.

# A Framework for Principled Evaluation

Industry standards are useful as a frame of reference that narrows the spectrum of choices. But popularity alone is not a measure of fit. Here are five questions to ground your evaluation.

**1. What problem does this solve, and do I have that problem?**
Don't start with "should we use X?" Start with "what problem are we solving?" Kubernetes solves orchestration at scale. If you're running three services with predictable load, you're paying for capabilities you don't need.

**2. What are the hidden prerequisites?**
What expertise, tooling, or organizational maturity does this require? Adopting microservices without investment in observability and operational practices doesn't give you microservices benefits. It gives you distributed complexity.

**3. What's the total cost of adoption?**
Compare honestly. Include the customization costs, the workaround costs, and the opportunity costs of fighting a tool that doesn't quite fit. Weigh these against the in-house alternative, which can still follow standard protocols and patterns.

**4. What's the cost of being different?**
Sometimes conforming has real benefits: a larger hiring pool, richer ecosystem, easier onboarding. Weigh this honestly. The goal isn't to be contrarian for its own sake.

**5. What does the trajectory look like?**
Is this technology ascending, stable, or declining? Consider not just where it is today, but where it's going and your ability to change course.

# Design for Change

If de facto standards change over time, then clinging to any single standard as a permanent decision is a risk in itself.

The practical tool here is an **indirection layer**: an internal abstraction that shields your systems from the specifics of any one implementation. Instead of coupling directly to a specific tool, define an internal interface that captures what you actually need and let the underlying implementation be swappable.

This guards against the sunk cost fallacy. Without an abstraction layer, switching feels prohibitively expensive, so teams double down on a poor fit. With one, the switching cost drops, and the decision to stay or move becomes a genuine evaluation rather than an emotional one.

The irony: building an in-house abstraction layer, the thing that gets labelled "not following standards," is often what gives you the most freedom to adopt, change, and leverage standards over time.

# Conclusion

"Industry standard" should start conversations, not end them.

The phrase tells you something has achieved widespread adoption. It tells you nothing about whether it fits your context, your constraints, your team, or your actual problems.

The principled approach:

- **Define the term clearly.** Understand what "industry standard" actually means, and recognise the pitfalls of blind adoption.
- **Understand the traps.** Is it de jure or de facto? THE standard or A standard? Framing, timing, and context all shape how a "standard" is perceived and misperceived.
- **Evaluate for fit, not popularity.** Start from the problem. Weigh hidden costs and prerequisites. Consider trajectory. Design for change.

The path less principled adopts standards blindly, treats popularity as proof of fit, and avoids the work of evaluation. The next time someone tries to end a discussion with "it's industry standard," don't let it. And don't let them. Use what we've covered here not to confront them, but to guide them toward the principled approach. And if you find it useful, share this post.

The principled path understands *why* something became a standard, and more important, whether those reasons apply to you.
