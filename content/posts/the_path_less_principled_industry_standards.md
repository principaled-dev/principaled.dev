---
title: 'The Path Less Principled: When "Industry Standards" Lead You Astray'
date: "2026-01-17"
description: 'The phrase "industry standard" is often used to end conversations rather than start them. When it becomes a substitute for principled evaluation, teams adopt solutions that don''t fit.'
summary: "Part 1 of a series examining industry standards: what they actually are, why they matter, and the pitfalls of blind adoption."
tags: ["industry standards", "the-path-less-principled", "pitfalls", "engineering practices", "trade-offs"]
categories: ["series", "pitfalls", "engineering practices"]
series: ["The Path Less Principled"]
ShowToc: true
TocOpen: true
---

# Introduction

"It's industry standard."

Few phrases end technical discussions faster. The moment someone invokes industry standard, the burden of proof shifts. Suddenly, you're not debating whether a technology fits your context. You're defending why you'd dare deviate from what everyone else does.

Let me be clear: industry standards are great. The Internet would not exist without standards like IP and TCP. Standards enable interoperability between systems that would otherwise have no way to communicate. They foster environments where people and organizations can collaborate, innovate, and build on each other's work. We all stand on the shoulders of giants.

But here's the problem: when "industry standard" becomes a substitute for principled evaluation, teams adopt solutions that don't fit their context, their scale, or their actual problem. The phrase borrows legitimacy it often hasn't earned.

# What "Industry Standard" Actually Means Nowadays

In the strict sense, a standard is a de jure construct: something governed by a formal body. Think IETF RFCs for network protocols, ISO specifications, or W3C recommendations for web technologies. These have defined processes, versioning, compliance criteria, and exist specifically to solve interoperability problems between systems that need to communicate.

Then there's the looser usage: de facto standards. These exist in practice rather than by decree, emerging through widespread adoption rather than formal governance. Git for version control. JSON for APIs. YAML for configuration. No organization certifies compliance. No specification defines what qualifies. They became "standard" because enough people adopted them, though what counts as "enough" is conveniently never defined.

People use the term "industry standard" loosely, where both variants can be meant. So let me attempt a working definition for this three-part series that encompasses both. "Industry standard," as used nowadays, amounts to: *a set of technical criteria, methods, processes, and practices that are formally agreed upon and/or otherwise well accepted and adopted by the tech community.*

But even with this working definition, things are still tricky. Consider the spectrum:

- **Network protocols** (Ethernet, IP, TCP) — clearly formal standards
- **Application protocols** (DNS, HTTP) — formal standards
- **Architectural styles** (REST, microservices) — widely adopted patterns, no governing body
- **Data formats** (JSON, Protobuf) — some formalised, some de facto
- **Programming languages** (Python, Go, Rust) — popular choices, not "standards"
- **Specific tools** (Kubernetes, Terraform, ArgoCD) — just... popular?

As you move up this stack, the term "industry standard" gets fuzzier. Calling TCP an industry standard is uncontroversial: there's a spec, a governing body, and universal adoption. Calling Kubernetes an industry standard? That's murky—is it *the* standard or *a* standard? For whom? At what scale? And what about the layer on top, like ArgoCD vs. Flux vs. kube-applier for GitOps? Now we're just picking favourites. The term starts doing rhetorical work that it hasn't earned.

The conflation is the problem. Calling something an "industry standard" borrows legitimacy from de jure standards while often meaning de facto, meaning just "widely adopted." Real standards solve interoperability and decrease fragmentation. "Standards" in the loose sense often just mean "popular." And popular is not the same as appropriate.

With all of this ambiguity (de jure and de facto conflated, and what often amounts to a popularity contest), it's worth asking: if the term is held this loosely, should we even be using it at all? Or perhaps we should return to using it strictly, as it was originally meant: governed by specification and upheld by a standards body.

# The Pitfalls of Blind Adoption

When "industry standard" substitutes for principled technical evaluation, predictable problems follow.

## Context Collapse

What works for Netflix doesn't work for a 10-person startup. And the reverse is also true: a tool beloved by small teams for its simplicity may collapse under hyperscale load. Context collapse works both ways. Yet teams routinely adopt technologies without asking whether they share the same constraints as the people who built or popularised them.

Kubernetes is the canonical example. (Don't get me wrong: I've spent nearly a decade working with Kubernetes and built much of my career around the ecosystem and layers above it.) But teams adopt it because "everyone uses it" without asking basic questions: Do we have the operational expertise to run it? Does our scale justify the complexity? What problem are we actually solving that simpler alternatives can't address?

The answer is often uncomfortable. Many teams would be better served by a managed platform like Heroku or Railway, or even a straightforward deployment to virtual machines. But "we run on Kubernetes" sounds more impressive than "we deploy to EC2 instances," so the complexity gets absorbed without examination.

The opposite pattern is equally dangerous. Cron jobs are the "standard" way to schedule tasks: simple, universal, battle-tested. Until you need retries, dependency management, failure alerting, or visibility into what's running. Teams stretch cron well past its design limits because it's familiar, then wonder why their scheduled workflows are a black box of silent failures.

## Cargo Culting Legitimacy

"Industry standard" becomes a rhetorical shortcut to avoid justification. Instead of articulating why a technology fits the problem, teams appeal to the authority of adoption. The logic runs: if enough companies use it, if it has enough GitHub stars, if it was presented at KubeCon, or if it's backed by someone with name recognition, it must be good.

This shows up constantly in tech stack decisions. Teams choose languages, frameworks, and tools based on what's trending rather than what fits their problem domain. The reasoning isn't "this tool solves our problem well." It's "this tool is popular, it looks good on a resume, and it feels like the modern choice."

You'll also hear that skills are transferable: easier onboarding, and individuals can leverage that expertise elsewhere. There's a defensive element too: nobody gets blamed for picking the obvious choice. But deviate from the herd and fail? Now you have to explain yourself.

None of those are technical arguments. They're arguments about human capital, career portability, and organizational risk. And they're not necessarily wrong. But they should be weighed as what they are: business and people considerations, not evidence of technical fit. Presenting them as technical justification is arguing in bad faith.

## Hidden Costs Ignored

The "standard" path is often justified as cost-saving: it's off-the-shelf, no need to build from scratch. But when the choice isn't grounded in technical merit, hidden costs accumulate that never make it into the comparison.

Need to make it fit for purpose? That means upstream changes, which aren't as simple as submitting a pull request. There are CLAs to sign, maintainer priorities to navigate, and release cycles you don't control. Often it means carrying a fork and maintaining your own build infrastructure indefinitely.

Or you work around the limitations instead of through them, building clunky architecture to compensate for a tool that doesn't quite fit. Meanwhile, the cost comparison still assumes you're using the vanilla off-the-shelf version. The customization costs, the workaround costs, the opportunity costs of fighting the tool: none of that gets weighed against the "more expensive" purpose-built alternative that would have just worked.

Beyond customization, the "standard" path often has invisible prerequisites: team size, operational expertise, organizational maturity, supporting infrastructure. Does it fit your existing architecture? Is there already an internal offering that solves the same problem? What's the adoption cost across teams? And critically: is your organization actually committed to this direction, or is this a half-hearted adoption that will be abandoned in two years?

Adopting without answering these questions doesn't give you the benefits. It gives you the complexity without the payoff. You end up with the worst of both worlds: the learning curve and operational burden of the "standard" tool, plus the ongoing cost of making it do something it wasn't designed for.

# Conclusion

So should we stop using the term "industry standard" altogether? Not necessarily. Rather than fight the loose definition most people carry around, we can accept that the concept is still useful: as a frame of reference, not as a decision-maker. That's why I attempted a working definition in the first place.

Standards, broadly defined, help narrow the spectrum of choices. They point to what's been tried, what's gained traction, what has community support. That's valuable signal. The problem isn't the term itself. It's using it as a conversation-stopper rather than a conversation-starter.

Invoking "it's industry standard" without evidence—without explaining *what* standard, *who* follows it, and *why* it applies to your situation—is a bad faith argument that shuts down discussion rather than advancing it. It borrows legitimacy without earning it. That's the path less principled.

The principled path is to treat "industry standard" as the beginning of evaluation, not the end. Ask the hard questions. Weigh the hidden costs. Understand your context. And if someone uses the phrase to avoid that work, _call it out_ (and maybe share this post with them).