---
title: 'The Path Less Principled: From Hype to Principled Evaluation'
date: "2026-03-11"
description: 'A framework for evaluating "industry standards" and why building in-house isn''t the opposite of following standards.'
summary: "Part 3 of the industry standards series: how to actually evaluate technologies, and addressing the false dichotomy between in-house development and industry standards."
tags: ["industry standards", "the-path-less-principled", "pitfalls", "engineering practices", "trade-offs"]
categories: ["series", "pitfalls", "engineering practices"]
series: ["The Path Less Principled"]
ShowToc: true
TocOpen: true
---

# Introduction

In [Part 1](/posts/the_path_less_principled_industry_standards), we defined what "industry standard" means and explored the pitfalls of blind adoption. In [Part 2](/posts/the_path_less_principled_industry_standards_part_2), we examined why evaluation is harder than it sounds: not all standards are equal, framing shapes perception, standards evolve, and context changes everything. We ended with four questions you need to answer before evaluation can even begin.

Now the practical part. How do we actually evaluate? And let's clear up a misconception I encounter frequently: the assumption that building in-house is somehow the opposite of following standards.

# The False Dichotomy: Build vs. Follow

"Why aren't we following industry standards?"

I've heard this alarm raised frequently whenever in-house software development is proposed or when an existing homegrown project is revisited. The concern is understandable: in-house development carries costs around maintenance, sustainability, and opportunity cost. If something off-the-shelf exists, shouldn't we use it?

But here's the thing: **in-house software development is not mutually exclusive with industry standards.**

The assumption often goes like this: using an off-the-shelf open-source project, as-is, is lower cost, more sustainable (because of the community behind it), and therefore higher value—because we don't have to pour engineering resources into development.

This assumption isn't always true.

You can build in-house solutions that follow standard protocols, standard interfaces, and standard patterns. A custom service that speaks HTTP, serializes with Protobuf, deploys via standard CI/CD pipelines, and exposes Prometheus metrics is absolutely following industry standards—it's just not using an off-the-shelf implementation.

The question isn't "build vs. buy." The question is: **What problem are we solving, and what's the right tool for this context?**

Sometimes that's an off-the-shelf solution adopted as-is. Sometimes it's an off-the-shelf solution with significant customization. Sometimes it's something built in-house that leverages standard building blocks. The "industry standard" framing often obscures this spectrum of options.

# A Framework for Principled Evaluation

Industry standards—even de facto ones—are useful. They serve as a frame of reference, help gauge market direction, and narrow the spectrum of choices. But popularity alone is not a measure of fit. FOMO is real. The temptation to adopt something because "everyone else is using it" is real. Resist the urge to solutioneer.

In Part 2, we identified four questions to ask before evaluating: What kind of standard is it? THE or A? Where in its lifecycle? Does the context match? Those questions help you see the technology clearly. The framework below helps you decide whether to adopt it.

## 1. What problem does this solve, and do I have that problem?

This is the most important question, and the one most often skipped.

Understand the use cases and constraints the technology was designed for. Then compare honestly to your own context. Don't start with "should we use X?" Start with "what problem are we solving?" and work outward from there.

Kubernetes solves orchestration at scale for organizations with many services, dynamic scaling requirements, and dedicated platform teams. If you're running three services with predictable load, you may be paying for complexity you don't need. Standards often solve problems at scale. If you're not operating at that scale, you're paying for capabilities without receiving the benefits.

## 2. What are the hidden prerequisites?

What expertise, tooling, or organizational maturity does this require? Be honest about whether you have these prerequisites—or are willing to invest in building them.

Adopting a microservices architecture without investment in observability, service discovery, and operational practices doesn't give you microservices benefits. It gives you distributed complexity. The "standard" path often has invisible prerequisites that never make it into the cost comparison.

## 3. What's the total cost of adoption?

The off-the-shelf path is often justified as cost-saving. But when the choice isn't grounded in technical merit, hidden costs accumulate.

Need to make it fit for purpose? That means upstream changes—CLAs to sign, maintainer priorities to navigate, release cycles you don't control. Often it means carrying a fork indefinitely. Or you build workarounds, compensating for a tool that doesn't quite fit while the cost comparison still assumes the vanilla version. The customization costs, the workaround costs, the opportunity costs of fighting the tool: none of that gets weighed against the "more expensive" alternative that would have just worked.

Compare this honestly against the in-house option; which, as we covered above, can still follow standard protocols and patterns.

## 4. What's the cost of being different?

Sometimes conforming to a popular choice has real benefits: a larger hiring pool, richer ecosystem tooling, more community support, easier onboarding for new team members.

Weigh this honestly. These are legitimate business and people considerations. The goal isn't to be contrarian for its own sake: it's to make deliberate choices rather than default ones.

## 5. What does the trajectory look like?

Is this technology ascending, stable, or declining? As we explored in Part 2, de facto standards are ever-evolving. A choice that's clearly "industry standard" today might be fading in three years.

Consider not just where something is today, but where it's going. And consider your ability to change course if the trajectory shifts—more on that below.

# When Standards Help

This series has focused on pitfalls, but let me be clear: industry standards, used correctly, are enormously valuable.

**As a frame of reference.** When evaluating options, starting with widely adopted solutions makes sense. There's signal in adoption—problems have been encountered and solved, documentation exists, and expertise is available.

**To gauge market direction.** Understanding where the industry is heading helps with strategic planning. It's useful to know what's gaining momentum and what's fading.

**To narrow the spectrum.** You can't evaluate every option. Standards help you focus on viable candidates rather than starting from scratch.

**To leverage community knowledge.** Widely adopted solutions have communities that produce documentation, answer questions, fix bugs, and share patterns. More recently, that body of community knowledge feeds into AI model training, meaning widely adopted tools tend to get better AI-assisted support-another practical advantage of adoption.

The key is using standards as input to your evaluation, not as a substitute for it.

# Designing for Change

In Part 2, we established that de facto standards change over time. If that's true, and the CNCF landscape is proof enough, then clinging to any single standard as a permanent decision is a risk in itself.

This doesn't mean you should avoid commitment. It means you should design for the possibility of change.

The practical tool here is an **indirection layer**: an internal abstraction that shields your systems from the specifics of any one implementation. Instead of coupling your application directly to a specific message broker, CI/CD tool, or deployment target, you define an internal interface that captures what you actually need and let the underlying implementation be swappable.

This isn't speculative over-engineering. It's a deliberate architectural choice that acknowledges a reality: the "standard" tool you adopt today may not be the right one in two years. Teams that build this indirection from the start can pivot when the landscape shifts without rewriting their entire stack.

It also guards against the sunk cost fallacy. Without an abstraction layer, switching away from a tool feels prohibitively expensive, so teams double down on a poor fit rather than cut their losses. With one, the switching cost drops, and the decision to stay or move becomes a genuine evaluation rather than an emotional one.

The irony is worth noting: building an in-house abstraction layer—the thing that gets labelled "not following standards"—is often what gives you the most freedom to adopt, change, and leverage standards over time.

# Conclusion

"Industry standard" should start conversations, not end them.

The phrase tells you something has achieved widespread adoption. It tells you nothing about whether it fits your context, your constraints, your team, your existing systems, or your actual problems.

Throughout this series, we've built up a principled approach:

- **Define the term clearly.** Is it de jure or de facto? THE standard or A standard? ([Part 1](/posts/the_path_less_principled_industry_standards))
- **Understand the traps.** Framing, timing, and context all shape how a "standard" is perceived and misperceived. ([Part 2](/posts/the_path_less_principled_industry_standards_part_2))
- **Evaluate for fit, not popularity.** Start from the problem. Weigh hidden costs and prerequisites. Consider trajectory. Design for change.

The path less principled adopts standards blindly, treats popularity as proof of fit, and avoids the work of evaluation.

The principled path understands *why* something became a standard, and more important, whether those reasons apply to you.
