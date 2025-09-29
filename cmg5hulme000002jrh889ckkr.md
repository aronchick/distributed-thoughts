---
title: "Why LLMs Can't Replace Your SREs (Yet)"
seoTitle: "AI Won't Replace SREs Soon"
seoDescription: "Large Language Models can't replace Site Reliability Engineers yet; AI can augment human expertise for enhanced incident management"
datePublished: Mon Sep 29 2025 19:00:39 GMT+0000 (Coordinated Universal Time)
cuid: cmg5hulme000002jrh889ckkr
slug: why-llms-cant-replace-your-sres-yet
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1759099613528/f070ccf7-1742-45e8-860b-fad9f789739a.png
tags: data-science, machine-learning, sre, data-engineering

---

# The Reality Check

[ClickHouse](https://clickhouse.com/) just dropped a [study](https://clickhouse.com/blog/llm-observability-challenge) that every executive should read: LLMs are great at some things, but basing your infrastructure on them? Too much, too soon.

They tested five leading models ([Claude Sonnet 4](https://www.anthropic.com/claude), [GPT-o3](https://openai.com/gpt-4), GPT-4.1, [Gemini 2.5 Pro](https://deepmind.google/technologies/gemini/), and the newly released GPT-5) against real [observability](https://www.honeycomb.io/what-is-observability) scenarios. The verdict? We're nowhere near the autonomous operations future Silicon Valley's been selling.

## The Experiment That Matters

Here's what I love about this study: they stuck to first principles. No abstract benchmarks. No synthetic tests. Just real [OpenTelemetry](https://opentelemetry.io/) data thrown at these models with a simple ask - do what [SREs](https://sre.google/sre-book/introduction/) do every day: figure out why production's on fire.

The prompt? "You're an Observability agent and have access to OpenTelemetry data from a demo application. Users have reported issues using the application, can you identify what is the issue, the root cause and suggest potential solutions?"

They tested four scenarios - payment failures, cache errors, product catalog issues. The stuff that actually happens at 3 AM.

## Where the Rubber Meets the Road

The results? Mixed bag. Claude Sonnet 4 and OpenAI o3 nailed some payment failures without help. But throw them a curveball - [cache errors](https://www.cloudflare.com/learning/cdn/what-is-caching/), catalog issues - and suddenly every model needs a human to hold its hand.

Here's the killer quote about Claude: "The model tends to lock onto a single line of reasoning and doesn't explore other possibilities." That's debugging 101 failure right there. Real troubleshooting means constantly questioning your assumptions, not death-gripping one theory.

Gemini 2.5 Pro? Even worse. It straight-up [hallucinated](https://en.wikipedia.org/wiki/Hallucination_(artificial_intelligence)) root causes: "It then began to formulate an imaginary cause (for which it had no evidence), and began trying to prove its case." 

Confidently wrong. The worst kind of wrong.

## The Economics Don't Add Up (Yet)

Let's talk money. [Token usage](https://help.openai.com/en/articles/4936856-what-are-tokens-and-how-to-count-them) swung wildly - thousands to millions. Cost per investigation? Anywhere from $0.10 to $6. Time? One minute to 45.

Sure, even $60 per incident beats an engineer's hourly rate - if it actually worked. But here's the rub: an SRE still has to review everything, understand the context, and actually fix the problem. The diagnosis isn't even half the battle.

Try explaining to your CFO why this month's AI bill is 60x last month's because the model went down a rabbit hole.

## GPT-5: The Emperor's New Clothes?

Mid-study, OpenAI drops GPT-5. The result? Same performance as everything else, just using fewer tokens. Efficiency bump, not a capability leap.

This isn't GPT-5's fault. These models haven't been trained on this stuff - there's no structured training data, no proper evals. They don't have the pathways to give better answers.

## The Human-in-the-Loop Imperative

[Tomasz Szandała's study](https://www.iccs-meeting.org/archive/iccs2025/papers/159090307.pdf) backs this up: LLMs hit 44-58% accuracy in [zero-shot root cause analysis](https://en.wikipedia.org/wiki/Zero-shot_learning). Humans? 62%. With [prompt engineering](https://www.promptingguide.ai/), LLMs reached 60-74%. Humans still beat them at 80%+.

The gap matters most exactly where you need it least; those complex, ambiguous scenarios that define real incidents.

## Where LLMs Actually Shine

Not everything's terrible. LLMs crush it at:
- Turning noise into narratives (summarizing logs and [traces](https://www.dynatrace.com/news/blog/what-is-distributed-tracing/))
- Writing [post-mortems](https://sre.google/sre-book/postmortem-culture/) and status updates
- Suggesting investigation paths
- Sanity-checking human findings

They're force multipliers, not replacements.

## The Path Forward: Augmentation, Not Replacement

The verdict's in: AI assists, humans decide. [As Varun Biswas notes](https://www.linkedin.com/pulse/ai-future-site-reliability-engineering-sre-jobs-varun-biswas-fwxle/), AI handles the grunt work, humans handle strategy.

This isn't AI failing - it's acknowledging reality. [Distributed systems](https://www.confluent.io/learn/distributed-systems/) are detective stories. You need intuition, experience, context. You need to know not just what broke, but why it was built that way.

## What This Means for Engineering Teams

Here's your playbook:

1. **AI augments, doesn't replace** - Use it to make your team better, not smaller
2. **Deploy strategically** - Documentation, triage, pattern recognition. Keep humans in charge
3. **Budget for chaos** - Token costs are unpredictable. Set hard limits
4. **Train for collaboration** - Your SREs need to learn to work with AI, not against it
5. **Stay skeptical** - Anyone selling autonomous incident response is selling BS

## The Distributed Data Challenge

Here's the kicker: even if LLMs could diagnose problems perfectly, there's another issue: [data locality](https://en.wikipedia.org/wiki/Data_locality). Your observability data's scattered across regions, clouds, edge locations. Moving terabytes to a central spot for AI analysis? That's physics working against you.

At [Expanso](https://expanso.io/), we're flipping the script - bring compute to the data, not the other way around. When you're generating logs globally, data movement becomes your bottleneck. Those token costs the study mentioned? They explode when you're processing redundant, unfiltered data.

The ClickHouse study hints at the solution: better context, better tools. Process and filter at the edge before hitting your LLMs. Be smart about what actually needs central processing versus what stays local.

## The Bottom Line

ClickHouse's study is the reality check we needed. LLMs are powerful tools when paired with human expertise. They're not replacing your SREs - they're making them more effective.

The researchers nailed it: "Can LLMs replace SREs right now? No. Can they shorten incidents and improve documentation when paired with a fast observability stack? Yes."

The future isn't human or machine. It's both. And when production melts down at 3 AM, you'll still want a human on call.

--- 

*Want to learn how intelligent data pipelines can reduce your AI costs?* [***Check out Expanso***](https://expanso.io/). Or don't. Who am I to tell you what to do.*

**NOTE: I'm currently writing a book based on what I have seen about the real-world challenges of data preparation for machine learning, focusing on operational, compliance, and cost. [I'd love to hear your thoughts](https://github.com/aronchick/Project-Zen-and-the-Art-of-Data-Maintenance)!**

---

*What's your experience with LLMs in production operations? Have you found specific use cases where they excel or fail? Share your thoughts in the comments below.*

## Further Reading

- [The original ClickHouse LLM Observability Challenge](https://clickhouse.com/blog/llm-observability-challenge)
- [Google SRE Book](https://sre.google/sre-book/) - The foundational text on Site Reliability Engineering
- [Honeycomb's Guide to Observability](https://www.honeycomb.io/what-is-observability) - Understanding modern observability practices
- [OpenTelemetry Documentation](https://opentelemetry.io/docs/) - The standard for telemetry data
- [The State of AI in Production](https://www.oreilly.com/radar/ai-in-production/) - O'Reilly's perspective on production AI
- [Chaos Engineering Principles](https://principlesofchaos.org/) - How to build resilient systems
- [Platform Engineering](https://platformengineering.org/) - The evolution of DevOps and SRE practices