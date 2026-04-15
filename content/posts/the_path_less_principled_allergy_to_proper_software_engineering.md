---
title: "The Path Less Principled: Allergy to Proper Software Engineering"
date: "2026-04-14"
description: "Some engineers have built entire careers assembling off-the-shelf tools and have developed an allergic reaction to any custom-built software. That allergy isn't grounded in engineering judgement. It's rooted in insecurity. And when paired with organizational power, it becomes hostile engineering."
summary: "When 'build vs. buy' becomes 'buy, always, no exceptions,' something deeper than engineering judgement is at play. On insecurity masquerading as pragmatism, hostile engineering disguised as collaboration, and what organizations lose when custom work becomes a dirty word."
tags: ["the-path-less-principled", "engineering practices", "build-vs-buy", "abstractions", "software engineering", "hostile engineering"]
categories: ["series", "engineering practices"]
series: ["The Path Less Principled"]
ShowToc: true
TocOpen: true
draft: false
---

# Introduction

There's a particular kind of engineer who breaks out in hives at the sight of custom code.

I'm not talking about the obviously reckless "write a new ACID-compliant database" kind. I'm talking about the reasonable kind. A purpose-built abstraction that simplifies a complex workflow. A controller that encapsulates operational logic. A thin layer that formally separates concerns between teams. The kind of custom work that exists because the off-the-shelf option either doesn't exist, doesn't fit, or actively makes the problem harder.

And yet, the moment it appears, the allergic reaction kicks in. The objections come fast: "Why aren't we using the standard tool?" "This isn't how the industry does it." "We should be collaborating on this." People who aren't users of the system, who have no stake in its outcomes, suddenly insert themselves as partners and stakeholders. The tone is reasonable. The intent is not. Because the conversation doesn't end until the custom work is dead.

This isn't principled engineering. It's insecurity wearing an engineering hat.

# The "Glue Things Together" Engineer

Let me be clear: I'm not writing this from the outside looking in. I started my career in infrastructure, operating datacentres and hosting services at scale. I pivoted through full-stack development and front-end work before landing in operations. Assembling off-the-shelf tools, running open-source projects in-house, building deployment pipelines, wiring services together: this is real engineering. I've done it. Orchestration, integration, and operations are skills that keep production systems alive.

But there's a subset of engineers whose entire careers have been exactly and only this. They've never written a custom line of code that forms part of a service's core capability. Every problem they've solved has been: find the open-source project, deploy it, configure it, glue it to the next thing. Their expertise is selection and operation, not design and construction.

Again, there's nothing inherently wrong with this. The problem starts when this background becomes the only lens through which all engineering decisions get evaluated. When you've spent a career assembling other people's software, you develop a particular worldview: that the right answer is always to adopt, never to build. That custom code is inherently suspect, always "overkill." That if a tool doesn't already exist for your problem, you're probably defining the problem wrong.

This worldview isn't engineering judgement. It's a comfort zone mistaken for a principle.

# The Insecurity Behind the Allergy

Here's the part that rarely gets said out loud: the allergy to custom work is often rooted in insecurity, not pragmatism.

If you've never designed an abstraction, never reasoned through a system's interface boundaries, never written the code that *is* the capability rather than the code that *deploys* the capability, then encountering someone who does, or who's actively advocating to build something, is uncomfortable. You can't evaluate what they're proposing. You can't review it with confidence. You can't tell whether it's elegant or over-engineered, because you don't have the frame of reference.

That's a vulnerable position, especially if you're in a senior role. You're supposed to be the technical authority. You're supposed to have opinions on architecture. And now someone's put custom code in front of you that you can't meaningfully assess. The options are: admit the gap and lean on the people who can evaluate it, or reject it outright and steer back toward territory you understand.

The insecure choice is the second one. And it doesn't present itself as insecurity. It presents itself as rigour: "We should use proven solutions." "This introduces unnecessary risk." "Let's not reinvent the wheel." "We're not doing anything special to warrant special work." "We don't operate at a scale that's larger than anyone else." "We're not so different from others." "If it was a real problem, we would have heard about it by now, and an industry standard solution would already exist." "I just think it's overkill." All perfectly reasonable-sounding objections that happen to conveniently land on the same conclusion every time: don't build, adopt. Stay in the comfort zone. Keep the decision space confined to tooling you can evaluate.

The tell is consistency. A principled engineer sometimes says "build" and sometimes says "buy," depending on context. An insecure one always says "buy." Every single time. Regardless of context. That's not a principle. That's a reflex.

# Hostile Engineering

I have a name for what happens when this insecurity gets paired with organizational power: **hostile engineering**.

It works like this. Someone or some team builds something custom. A controller, a service, an internal abstraction. It works. It solves a real problem. It may even be well-documented and well-tested. But it exists outside the comfort zone of the person with authority.

So the "collaboration" begins.

Except it isn't collaboration. It's a siege. People who were never users of the system, who have no operational stake, no dependency, and no prior involvement, force themselves into the conversation as partners and stakeholders. They schedule review meetings. They propose alternatives (always off-the-shelf). They raise concerns about maintenance burden, bus factor, and "alignment with the broader ecosystem." Each objection sounds reasonable in isolation. Taken together, they form a pattern: the conversation will not end until the custom work is abandoned.

The insertion itself is the move. It often arrives dressed as generosity: "Well, we have lots of experience in this space. We can help you navigate." The offer sounds collegial. But it's not an offer. It's a foothold. Once they're "helping," they're in the room. Once they're in the room, they have opinions. Once they have opinions, those opinions become objections. And by the time anyone notices, they've claimed a seat at the table for a system they don't use and didn't build, and manufactured the authority to dismantle it. They're not collaborating. They're colonizing a decision space that isn't theirs.

This is the defining feature of hostile engineering: the false pretence of collaboration. It looks like an open discussion. It sounds like a technical evaluation. But the outcome was decided before the first meeting. The "collaborator" won't stop until they get their way. Compromise isn't on the table. The only acceptable result is capitulation.

And because it's wrapped in the language of collaboration and best practices, it's remarkably hard to call out. Anyone who pushes back looks like they're resisting collaboration. Anyone who defends their custom work looks like they have "not invented here" syndrome. The framing is rigged. The person undermining the work gets to look like the reasonable one, while the person who built something valuable gets cast as the obstacle.

## The War of Attrition

Hostile engineering doesn't need to win the argument. It just needs to keep having it.

Meeting after meeting, objection after objection, review after review, until the people who actually care about doing the right thing get worn down. Eventually, the calculus shifts. It's no longer about what's technically correct. It's about mental well-being. The engineers defending the work reach a point where their own health matters more than the fight, and they quietly let go. Not because they were wrong. Not because they were convinced. Because they were exhausted.

And that's how hostile engineering wins: not by being right, but by being relentless.

## Acting in Bad Faith

There's an even more corrosive variant. You spend three hours in a room walking through the technical justifications. You lay out the trade-offs, address every concern, answer every question. By the end, there's alignment. Everyone leaves the room on the same page.

And then, days later, the same person pushes the same narrative as if the conversation never happened. The same objections. The same framing, often in a different venue or forum, in front of a different audience. No acknowledgement of what was discussed, agreed, or understood. The meeting wasn't a meeting. It was theatre: a way to appear reasonable while having no intention of being moved.

When alignment is something the other party will accept only on their terms, the process isn't collaboration. It's coercion with extra steps.

## The Fallout

The damage isn't just to the project. It's to the people.

Engineers who've had their work killed this way learn the lesson quickly: don't build anything original. Don't stick your neck out. Don't invest in something that might get torn down by someone who couldn't evaluate it in the first place. The organization doesn't just lose the work. It loses the willingness to do the work.

And here's the final insult: the engineers who lost the fight are now stuck building and operating the inferior solution that was forced on them. They're the ones holding the bag. They're the ones paged at 2 AM when the ill-fitting tool breaks in exactly the ways they predicted. They're the ones fielding complaints from the real users and customers who have to live with the degraded experience. They're the ones writing the workarounds, filing the upstream issues, and absorbing the operational pain of a design they never agreed with.

The people who did the coercing? They pat themselves on the back and walk away. They never interact with the system again. They never operate it. They never feel the consequences of the decision they forced. They got their way, declared victory, and moved on, crafting a narrative that their expertise saved the company yet again, while the real engineers are left to live with the wreckage.

And when the struggle becomes visible? The off-the-shelf solution is never at fault. It's your execution. You architected your solution wrong. You didn't configure it right. You didn't adopt it fully enough. The answer is always to buy deeper into the off-the-shelf solution and leverage more of its features. The logic is unfalsifiable: when it works, it validates the approach. When it fails, it is only considered evidence that you weren't bought in enough. The prescription is always more of the same medicine, and the patient is always blamed for not responding.

# The Business Value You're Not Shipping

Here's the part that should concern leadership: if everything you deliver is off-the-shelf commodity software glued together, what exactly is your competitive advantage?

Taking open-source projects off the shelf, configuring them, and running them in-house is table stakes. It's necessary. It's not differentiating. Every one of your competitors can run the same Kubernetes cluster, deploy the same service mesh, and wire up the same CI/CD pipeline. The commoditized layer is, by definition, not where business value lives.

Business value lives in what you build *on top*. The custom capabilities. The domain-specific logic. The workflows, abstractions, and services that exist because your problem space demands them. That's the layer where engineering judgement, creativity, and deep understanding of your users actually matters.

Consider a concrete shape this takes. Most organizations have at least one problem that sits at the intersection of technical complexity and organizational complexity, where the challenge isn't just "how do we run this software" but "how do we coordinate many teams contributing to a shared system without everything drifting apart." No off-the-shelf tool solves that, because the problem is as much about your organization's structure as it is about the technology. The principled response is to build a thin custom layer, one that uses commodity tooling under the hood but provides a formal interface on top that turns coordination chaos into something manageable. That abstraction is custom because it has to be. The off-the-shelf alternative is a spreadsheet and a prayer.

Problems like these are everywhere. And every time the allergic reaction kills the custom solution, the organization is left with the commodity layer and nothing on top of it. An organization that's allergic to custom work is an organization that has optimized for running other people's software and has forgotten to ship its own. It's an engineering department that can stand up infrastructure but can't build capability. That's not engineering. That's operations wearing an engineering title.

This isn't an argument against adopting off-the-shelf solutions. The entire point of commoditized tooling is that you *should* adopt it for the problems it solves well, so that you can focus your custom engineering effort where it actually matters. Build vs. buy isn't a philosophical stance. It's a per-problem evaluation. And the answer should be "buy" for commodity concerns and "build" for differentiating ones.

The allergy to custom work gets this exactly backwards. It applies "buy" universally, including to the layer where the business value actually lives. And then everyone wonders why the engineering organization can't seem to deliver anything that moves the needle.

# Abstractions Have Their Place

There's a deeper engineering argument that gets lost in the noise: well-designed abstractions aren't just nice-to-have. They formally separate roles, responsibilities, and actors within a system, allowing each to interact with the system independently.

Consider a Kubernetes controller or operator. This is a pattern that creates a formal interface between the user-facing configuration: what gets exposed through a Custom Resource Definition (CRD), and the operational internals that the team responsible for the system manages behind the scenes. Users configure the dials they're meant to configure. Operators manage the complexity they're responsible for. The boundary is explicit. The contract is clear. Each side can evolve independently.

Now contrast this with the "industry standard" alternative that often gets proposed: Helm charts. A Helm chart offers an *informal* interface. The contract between the user and the system is a `values.yaml` file and a set of Go templates. There's no schema enforcement beyond what you bolt on yourself. There's no reconciliation loop. There's no separation between what the user should touch and what the team/human operator should control. It's all flattened into one bag of values and templates. Every configuration dial, whether user-facing or operational, lives in the same surface area.

This isn't to say Helm charts are bad. They solve a real packaging and distribution problem. In fact, there's a principled approach that embraces both: start with Helm charts and informal interfaces first. Use them to explore the interaction points, learn what users actually need, and let the interface mature through real usage. Then, once the boundaries are well-understood, graduate the informal interface into a formal one: a CRD backed by a controller, with schema validation, a reconciliation loop, and a clear separation of concerns. This is a deliberate engineering progression, not a rejection of either tool.

But when someone proposes replacing a controller, one that has already gone through that maturation, with a Helm chart in the name of "industry standards," they're not making an engineering argument. They're regressing a formal abstraction back into an informal one because the informal one is more familiar to them. They're not just collapsing an interface. They're undoing the engineering judgement that went into graduating it. The "standard" label is doing the work that engineering analysis should be doing.

This connects directly to the [industry standards piece](/posts/the_path_less_principled_industry_standards_combined): "industry standard" borrows legitimacy it often hasn't earned. A Helm chart is popular. A controller is principled. These are not the same axis of evaluation, and conflating them is how organizations end up with worse interfaces, blurred responsibilities, and systems that are harder to operate, all in the name of standardization.

Well-designed abstractions are an act of engineering. They require understanding the problem domain, identifying the actors, and drawing boundaries that serve each actor's needs. Dismissing them because they're "custom" is dismissing the engineering itself.

# The Principled Path

The principled engineer doesn't have a reflexive answer to "build or buy." They have a framework:

- **Is this a commodity concern?** If the problem is well-solved by existing tooling and isn't a source of competitive advantage, adopt. Don't reinvent the wheel for solved problems.
- **Is this a differentiating capability?** If the problem is specific to your domain, your users, or your organizational context, and the off-the-shelf option doesn't fit or doesn't exist, build. That's what engineers are for.
- **Does this need a formal abstraction?** If multiple actors interact with the system and have different concerns, build an abstraction that separates those concerns cleanly. An informal interface isn't a substitute for a formal one just because it's more familiar.
- **Can I evaluate what's in front of me?** If someone's built something custom and you can't assess it, that's a signal to learn, not to reject. Bring in people who can evaluate it. Ask questions. Do the homework. Don't substitute familiarity for judgement.

The principled path values both adoption and construction. It recognizes that the goal isn't to minimize custom code. It's to put engineering effort where it delivers the most value. Sometimes that's integrating an off-the-shelf tool. Sometimes that's writing something from scratch. The answer depends on the problem, not on the evaluator's comfort zone.

# Counteracting the Hostility

Recognizing hostile engineering is one thing. Surviving it is another. I won't pretend the cards aren't stacked against you. Over the years, across different teams and different organizations, I've watched this play out repeatedly, and it never gets easier. The framing is rigged, and the person doing the right thing is always the one who looks unreasonable. But there are approaches that can help.

## Make the Decision Legible

The single most effective defence against hostile engineering is documentation that speaks for itself. Write down the decision: what alternatives were evaluated, what trade-offs were considered, and why the custom approach was chosen. Make the reasoning explicit, public, and easy to find. When the hostile party shows up in a different forum pushing a different narrative, anyone in the room can point to the record. It's much harder to pretend a conversation never happened when the decision document is linked in the meeting invite.

## Establish Legitimate Stakeholders Early

If you know who the actual users and operators of the system are, name them. Make the stakeholder list explicit. When someone without a legitimate stake tries to insert themselves as a partner, having a clear record of who the system serves (and who it doesn't) gives you standing to ask: "What's your dependency on this system?" It's a simple question, but it forces the hostile party to articulate a claim they often can't back up.

## Force the Conversation Into Writing

Hostile engineering thrives in meetings. The ambiguity of verbal conversation, the pressure of real-time debate, the ability to later deny what was said. All of it favours the aggressor. Move the conversation into writing wherever you can. Proposals, evaluations, and decisions should be documented. Follow up meetings with written summaries of what was agreed. When the hostile party resurfaces the same objections in a different venue, you have a paper trail that makes the bad faith visible.

## Escalate on Pattern, Not on Incident

A single objection isn't hostile engineering. A pattern is. If you escalate after one disagreement, you look defensive. If you escalate after the fifth time the same person has relitigated the same decision in the same way, you have a case. Keep notes. Track the pattern. When you do escalate, whether to your skip-level, a peer leader, or whoever has the organizational standing to intervene, present the pattern, not the emotion. "This decision has been revisited four times, each time without new information" is a statement that's hard to argue with.

## Build Alliances with the Actual Users

The people using your system are your strongest advocates, but only if they know the fight is happening. Often, the engineers and teams who depend on the custom work have no idea it's under threat. Keep them informed. If the custom solution is replaced with an inferior one, they'll be the ones filing the complaints. Better they weigh in before the decision than after.

## Know When to Escalate Beyond Engineering

Sometimes the hostile party has enough organizational power that no amount of documentation or stakeholder clarity will matter. The decision will be overridden regardless of merit. At that point, the question is no longer technical. It's organizational. If the pattern is persistent and damaging, it needs to be visible to someone with the authority and willingness to address it. That might be a Lead Architect. That might be a VP. It might be a CTO. It might be an HR conversation if the behaviour crosses into bullying. Not every technical fight can be won with technical arguments. Some require organizational intervention.

## Protect Your People

If you're a lead or a manager watching this happen to your team, your job is to shield them. Engineers shouldn't have to spend their energy defending well-reasoned work from people who refuse to engage in good faith. That's your fight to take on, not theirs. Absorb the political cost so they can focus on the engineering. And if you can't protect them, if the hostile party has more authority than you and won't be moved, be honest with your team about the situation. They deserve to know the constraints they're operating under, even when those constraints aren't fair.

# Conclusion

The allergy to proper software engineering isn't about pragmatism or risk management. It's about comfort. It's about staying in the territory you know and dismissing anything that falls outside it. And when that allergy is paired with organizational power, it becomes hostile engineering: custom work gets killed not because it's wrong, but because the person with authority can't evaluate it and won't admit that.

The cost is enormous. Not just in lost projects, but in lost capability, lost morale, and lost business value. An engineering organization that can only assemble other people's software isn't engineering. It's operating. And the difference matters.

If you find yourself reflexively reaching for the off-the-shelf option every single time, ask yourself: is this engineering judgement, or is this the boundary of my comfort zone? The answer might be uncomfortable. But discomfort is where growth starts: both for the engineer and for the organization.

The path less principled treats "build" as a dirty word, wraps coercion in the language of collaboration, and mistakes familiarity for rigour.

The principled path asks the harder question: what does this problem actually need?
