---
title: "What the F*ck Are We Even Measuring? The Definition Problem in AI Evals"
seoTitle: "AI Evaluation: Defining What We Measure"
seoDescription: "Uncover the challenges of measuring AI success and the need for clear definitions and real-world performance metrics in AI evaluations"
datePublished: Mon Oct 06 2025 18:00:29 GMT+0000 (Coordinated Universal Time)
cuid: cmgffs6hc000102kzdtc682pr
slug: what-the-fck-are-we-even-measuring-the-definition-problem-in-ai-evals
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1759770015441/f2b04186-aa11-4ead-97eb-53002f26141c.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1759770043984/941cba6d-3037-4f4f-8601-a9a8cc4c4165.png
tags: artificial-intelligence, machine-learning, agi, evals

---

I recently came across a paper with a title that neatly sums up the state of AI: ["What the F*ck Is Artificial General Intelligence?"](https://arxiv.org/abs/2503.23923) by Michael Timothy Bennett. It's direct, unlike so much AI slop out there, and it asks exactly the right question.

But the question isn't just about AGI. It's about EVERYTHING we're measuring in AI right now.

If we can't even agree on what [intelligence](https://en.wikipedia.org/wiki/Intelligence) IS, how are we supposed to measure it? And if we can't measure it properly, how do we know if we're making progress or just fooling ourselves?

## The Rorschach Test Problem

Bennett quotes [Melanie Mitchell](https://melaniemitchell.me/)'s observation that [AGI](https://en.wikipedia.org/wiki/Artificial_general_intelligence) has become a "[Rorschach test](https://en.wikipedia.org/wiki/Rorschach_test)" (I prefer the analogy to the "[I Ching](https://en.wikipedia.org/wiki/I_Ching)") - everyone sees what they want to see. Some peg it to human-level performance across tasks. Others define it as the ability to generalize and acquire new skills. Still others frame it in terms of adaptation or goal satisfaction.

But this same thought applies to everything in AI.

Companies race to top [leaderboards](https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard) on benchmarks like [MMLU](https://paperswithcode.com/dataset/mmlu), [GSM8K](https://github.com/openai/grade-school-math), and [HumanEval](https://github.com/openai/human-eval). Press releases trumpet "state-of-the-art performance" with impressive percentages. Investors pour money into models that score 0.3% higher than the competition.

And almost nobody is asking: "What the fuck are we actually measuring here?"

Everyone sees what they want in their benchmarks. [OpenAI](https://openai.com/) sees reasoning capability. [Anthropic](https://www.anthropic.com/) sees safety and helpfulness. [Google](https://deepmind.google/) sees multimodal understanding. The academic community sees generalization. Same numbers, completely different conclusions.

It's measurement [Kabuki theater](https://en.wikipedia.org/wiki/Kabuki), and we're all in the audience.

## The Validity Crisis

A recent paper on [evaluation science for generative AI](https://arxiv.org/abs/2503.05336) lays it out plainly: "Commonly used static benchmarks face validity challenges, and ad hoc case-by-case audits rarely scale." The tools we're using to measure AI capability are broken at a foundational level.

Concrete example: evaluating a model's [cybersecurity capabilities](https://en.wikipedia.org/wiki/Computer_security). You create a task where the model exploits a [vulnerability](https://en.wikipedia.org/wiki/Vulnerability_(computing)) in code to acquire hidden information. Reasonable, right?

Except if that vulnerability is in the [training set](https://en.wikipedia.org/wiki/Training,_validation,_and_test_data_sets), you're testing memory, not research capability.

Fine. Exclude it from training. But now the model can use online search to find information about the vulnerability. You're testing its ability to utilize previously discovered vulnerabilities, not uncover new ones.

So you disable internet access. Except now your evaluation no longer represents a realistic [threat model](https://en.wikipedia.org/wiki/Threat_model).

Every "solution" creates a new [validity](https://en.wikipedia.org/wiki/Validity_(statistics)) issue. We're playing [whack-a-mole](https://en.wikipedia.org/wiki/Whac-A-Mole) with our own metrics.

## The Gap Between Measurement and Meaning

You can ace [MMLU](https://arxiv.org/abs/2009.03300) - score in the 90th percentile on high school and college-level multiple choice questions - and still be completely useless for actual work. We've seen teams leapfrog each other on the leaderboard while their audiences complain it doesn't "feel" any better.

The gap between "what we measure" and "what we care about" is ENORMOUS.

Most prominent LLM benchmarks focus on "straightforward tasks that many LLMs have largely saturated (e.g. high school science questions), and generally do not accurately represent the tasks LLMs are used for in practical real-world applications" (from the excellent [position paper on statistical rigor in evals](https://arxiv.org/abs/2503.01747)).

We're judging chefs by their ability to identify ingredients, not cook meals. We're evaluating race cars based on how shiny the paint is. We're measuring the wrong things because measuring the right things is HARD.

## We Need Fucking Definitions

You can't have success without defining what success MEANS.

Bennett's paper settles on "[intelligence in terms of adaptation](https://en.wikipedia.org/wiki/Adaptation)" and frames AGI as "an artificial scientist." That's a clear, testable definition. You can build experiments around it.

But what's the definition of success for:

- [Customer service bots](https://en.wikipedia.org/wiki/Chatbot)? Ticket resolution time? Customer satisfaction? Cost per interaction? How do you weight them?
- [Code generation](https://github.com/features/copilot)? Lines of code? Bugs per commit? Developer productivity?
- [Scientific research assistance](https://www.semanticscholar.org/)? Papers published? Hypotheses generated? Reproducibility?

If you can't define it, you can't measure it. If you can't measure it, you can't improve it. This isn't deep wisdom - it's the [scientific method](https://en.wikipedia.org/wiki/Scientific_method). We've got to decide that vibes and leaderboard positions are not good enough.

## The Real-World Performance Chasm

Evaluation metrics must be "applicable to real-world performance." Seems obvious, right?

When's the last time you saw a model evaluation that actually measured [real-world performance](https://en.wikipedia.org/wiki/Ecological_validity)? Not synthetic benchmarks or academic datasets, but ACTUAL deployment scenarios with ACTUAL users doing ACTUAL work?

Static benchmarks are fundamentally disconnected from reality. They capture a snapshot of capability at a moment in time, against fixed tasks, with predetermined success criteria. Reality is dynamic, messy, and full of [edge cases](https://en.wikipedia.org/wiki/Edge_case) nobody thought to test for.

[Ad hoc audits](https://en.wikipedia.org/wiki/Audit) don't solve this - they don't scale, and they're performed AFTER problems emerge. By the time you've done your audit, your model is deployed and potentially causing harm.

We need evaluation systems that:

1. Continuously monitor real-world performance
2. Adapt as models and use cases evolve
3. Capture the full spectrum of success and failure modes
4. Provide actionable feedback for improvement

And we need to be brutally honest about the limitations of our current measurements.

## What Actually Matters

Benchmarks aren't useless. They're insufficient. Treating them as the sole measure of progress is dangerous.

We need to move from "how well does it perform on this arbitrary test" to "does it solve the actual problem?"

Success metrics should be:

**Tied to Real Outcomes**
Not "accuracy on benchmark X" but "does this reduce customer support ticket resolution time by Y%?" Measure what matters to the people who will actually use the system. Everything else is [vanity metrics](https://en.wikipedia.org/wiki/Vanity_metric).

**Iteratively Refined**
Your first attempt at defining success metrics will be wrong. Do you have a process for learning from deployment and refining your metrics? Models evolve. Use cases evolve. User expectations evolve. Your [evaluation framework](https://en.wikipedia.org/wiki/Evaluation) needs to evolve too.

**Honest About Limitations**
Every evaluation has blind spots. Every metric has failure modes. Every benchmark can be [gamed](https://en.wikipedia.org/wiki/Goodhart%27s_law). The question isn't "can this be gamed?" but "are we honest about how it can be gamed, and are we actively working to address those failure modes?"

Statistical rigor matters. That position paper demonstrates that [Central Limit Theorem](https://en.wikipedia.org/wiki/Central_limit_theorem)-based [confidence intervals](https://en.wikipedia.org/wiki/Confidence_interval) - the standard approach for reporting uncertainty - systematically fail for smaller, specialized benchmarks. They dramatically underestimate uncertainty, giving us [error bars](https://en.wikipedia.org/wiki/Error_bar) that are too small and confidence we shouldn't have.

Most eval results are reported without error bars at all. We're making high-stakes decisions based on measurements with unknown and potentially massive [uncertainty](https://en.wikipedia.org/wiki/Uncertainty_quantification).

That's not science. That's [astrology](https://en.wikipedia.org/wiki/Astrology) with better math.

## Learning from Other Engineering Disciplines

[Aerospace](https://en.wikipedia.org/wiki/Aerospace_engineering). [Pharmaceutical development](https://en.wikipedia.org/wiki/Drug_development). [Transportation safety](https://en.wikipedia.org/wiki/Transportation_safety). These industries have mature [safety evaluation practices](https://en.wikipedia.org/wiki/Safety_engineering) because people die when you get it wrong. While AI might not (yet) have the same immediate life-or-death consequences in all applications, the stakes are still enormously high.

The [evaluation science paper](https://arxiv.org/abs/2503.05336) draws lessons from these fields:

1. Evaluation metrics must be applicable to real-world performance - not just lab conditions
2. Metrics must be [iteratively refined](https://en.wikipedia.org/wiki/Iterative_and_incremental_development) based on actual deployment experience
3. Evaluation systems must evolve as capabilities and risks change

None of this is revolutionary. It's just rigorous [engineering practice](https://en.wikipedia.org/wiki/Engineering) applied to a new domain.

But it requires something uncomfortable: Admitting we don't have all the answers. Accepting that our current measurements are rough approximations. Being willing to invest in evaluation infrastructure with the same vigor we invest in [model training](https://en.wikipedia.org/wiki/Training,_validation,_and_test_data_sets).

## Why This Actually Matters

The evals we choose shape the systems we build. Optimize for benchmark performance, get systems that are really good at benchmarks. Optimize for real-world utility, get systems that are actually useful.

If we're measuring the wrong things, we're optimizing for the wrong outcomes. And right now, we're measuring a LOT of wrong things.

These systems are being deployed at scale, making decisions about people's lives, work, and futures. The gap between our measurements and actual performance has real consequences.

## What Needs to Change

The AI industry needs better evaluation practices. Not [evaluation-as-marketing](https://en.wikipedia.org/wiki/Marketing). Not evaluation-as-checkbox. Actual rigorous measurement.

This means:

- Investing in evaluation infrastructure
- Publishing not just scores but methodologies, limitations, and failure modes
- Developing industry-wide standards for [statistical rigor](https://en.wikipedia.org/wiki/Statistical_inference)
- Creating [feedback loops](https://en.wikipedia.org/wiki/Feedback) between deployment and evaluation
- Building systems that continuously monitor real-world performance

It means being willing to say "we don't know" more often than "we're [state-of-the-art](https://en.wikipedia.org/wiki/State_of_the_art)."

Until we can define success in ways that connect to real-world outcomes, that are honest about limitations, that evolve with our understanding, we're just building expensive systems that are really good at passing tests.

The world doesn't need another test-taker.

---

*Want to learn how intelligent data pipelines can reduce your AI costs?* [***Check out Expanso***](https://expanso.io/). Or don't. Who am I to tell you what to do.*

**NOTE: I'm currently writing a book based on what I have seen about the real-world challenges of data preparation for machine learning, focusing on operational, compliance, and cost. [I'd love to hear your thoughts](https://github.com/aronchick/Project-Zen-and-the-Art-of-Data-Maintenance)!**