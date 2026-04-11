---
title: 'The Path Less Principled: Not All Standards Are Equal'
date: "2026-01-18"
description: 'Before you can evaluate an "industry standard," you need to understand why evaluation is harder than it sounds.'
summary: "Part 2 of the industry standards series: why not all standards are equal, how framing and timing shape perception, and the traps that make evaluation harder than it appears."
tags: ["industry standards", "the-path-less-principled", "pitfalls", "engineering practices", "trade-offs"]
categories: ["series", "pitfalls", "engineering practices"]
series: ["The Path Less Principled"]
ShowToc: true
TocOpen: true
---

# Introduction

In [Part 1](/posts/the_path_less_principled_industry_standards), we landed on a working definition of "industry standard": *a set of technical criteria, methods, processes, and practices that are formally agreed upon and/or otherwise well accepted and adopted by the tech community.* We explored the pitfalls of blind adoption and concluded that the principled path is to treat "industry standard" as the beginning of evaluation, not the end.

But before we can evaluate, we need to understand why evaluation is harder than it sounds. The term carries traps that, if we're not aware of them, will lead us right back to the blind adoption we're trying to avoid.

# Not All Standards Are Equal

In Part 1, we established that "industry standard" spans a spectrum from de jure (formal, governed by a standards body) to de facto (widely adopted in practice). De jure standards are relatively straightforward to evaluate: there's a specification, a governing body, and clear compliance criteria. You either implement HTTP/2 correctly or you don't.

De facto standards are where things get subjective. By nature of what makes them standards—widespread adoption and acceptance—there are varying levels of subjectivity when deciding whether something qualifies.

Consider the questions that have no objective answers:

- What threshold of adoption makes something "widespread"? 50% of companies? 80% of Big Tech? In which industry segment?
- What measures do we use? GitHub stars? <a href="https://survey.stackoverflow.co" target="_blank" rel="noopener">Stack Overflow Annual Developer Survey</a> results? Job posting frequency? Conference talk counts? Reddit and Hacker News sentiment? Are we running a popularity contest?
- What forms can a "standard" take? Can a guiding principle be a standard? A methodology? A practice? Or only concrete implementations?
- What makes something "well accepted" anyway? Acceptance by whom?

The answers vary drastically based on who you ask and in what context. An infrastructure engineer and a frontend developer will have completely different lists of "industry standards." A startup and an enterprise will disagree on what's standard for their scale.

Here's the uncomfortable truth: labelling something "industry standard" is ultimately stating an opinion. It's an opinion informed by experience and observation, but an opinion nonetheless. Recognizing this doesn't invalidate the term. It just means we need to probe deeper before accepting the label at face value.

# "The" Standard vs. "A" Standard

![XKCD 927: Standards](https://imgs.xkcd.com/comics/standards.png)
*Source: <a href="https://xkcd.com/927/" target="_blank" rel="noopener">xkcd.com/927</a>*

In a healthy ecosystem, multiple solutions evolve around similar use cases. This is a good thing—multiple implementations prevent vendor lock-in and foster healthy competition.

But it creates a linguistic trap. When someone says "X is industry standard," do they mean X is *THE* standard or *A* standard? We often hear the former when the latter is more accurate.

The difference matters.

Git is *THE* industry standard for distributed version control. There's no serious competition. But GitHub vs GitHub On-Prem vs. GitLab vs. Bitbucket? Those are each *A* standard for hosted Git repositories. Declaring any one of them as *THE* standard would be contentious—and unnecessary.

Kubernetes might be *THE* standard for container orchestration at scale (even that's debatable—Nomad has its place). But ArgoCD vs. Flux vs. kube-applier for GitOps? Those are competing as *A* standard, each with legitimate adoption and different trade-offs.

This framing trap has real consequences. Treating something as *THE* standard demands a definitive answer and shuts out alternatives. Asking whether something is *A* standard opens space for nuance: what are the alternatives, and how do they compare?

When we acknowledge that multiple standards can co-exist, conversations shift from the emotional and social—defending territory, signalling tribal allegiance—to the principled and technical: evaluating fit for the context at hand.

# Standards Change. Your Decision Doesn't.

De facto standards are ever-evolving. By nature of what makes them standards—adoption, not decree—they exist within fast-moving ecosystems where something is always ready to take their place.

Look at the [CNCF Cloud Native Landscape](https://landscape.cncf.io/). It's a sprawling visualisation of just how many options exist in cloud-native computing alone. Projects rise, plateau, and decline. New categories emerge. Old categories consolidate. What's "standard" in the moment may not be in the next.

But engineering decisions happen at a specific point in time. They depend on previous decisions—existing infrastructure, team expertise, organizational constraints. You can't continuously chase the latest standard. Nor can you predict which of today's standards will still matter in three years.

A choice that was clearly "industry standard" three years ago might look questionable today. A choice that looks questionable today might be vindicated in two years. What seemed like the safe bet can turn out to be a dead end, and what looked like a risky deviation might turn out to be prescient.

This creates a tension: how much should we index our decisions on de facto standards that may be obsolete soon? The answer isn't "ignore them entirely." But it means that the current popularity of a standard is weaker evidence than we tend to treat it as.

# Whose Industry? Which Context?

Part 1 covered context collapse as a pitfall of blind adoption. But context also shapes what counts as a "standard" in the first place.

Git is the standard for version control—until you're dealing with monorepos at massive scale, or repositories with large binary files. Then the "standard" tool has sharp edges that demand workarounds or alternatives.

GitHub might be the leading hosted Git platform by adoption. But is it "standard" for enterprises with strict data residency requirements? For organizations that need on-premise hosting? For teams that prioritize specific CI/CD integrations?

Every tool on the CNCF landscape exists because some context made it valuable to someone. That's not chaos. It's the natural result of a diverse industry with diverse needs. But it means that invoking "industry standard" without specifying *whose* industry and *which* context is often meaningless.

The same technology can be the obvious choice in one context and a poor fit in another. Evaluation has to start from your constraints, not from a universal ranking of popularity.

# Conclusion

None of this means the term "industry standard" is useless. It means the label alone tells you very little. Before you can meaningfully evaluate whether to adopt something labelled "industry standard," you need to ask:

- **What kind of standard is it?** De jure standards with formal specifications carry different weight than de facto popularity.
- **THE or A?** Is it the only viable option, or one of several? What are the alternatives?
- **Where is it in its lifecycle?** Rising, stable, or fading? How much should that trajectory factor into a decision you'll live with for years?
- **Does the context match?** Whose industry? What scale? What constraints?

These aren't evaluation criteria yet. They're the questions you need to answer *before* evaluation can even begin. Without them, you're evaluating a label, not a technology.

In [Part 3](/posts/the_path_less_principled_industry_standards_part_3), we'll take these questions and build them into a practical framework for principled evaluation. We'll also tackle a common misconception: the assumption that building in-house is somehow the opposite of following standards.
