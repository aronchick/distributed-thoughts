---
title: "Ghosts vs. Animals"
seoTitle: "Ghosts vs. Animals Showdown"
seoDescription: "Explore the debate between AI approaches: "ghosts" vs. "animals". Discover differing views on intelligence, ethics, and future AI development paths"
datePublished: Thu Oct 02 2025 19:00:12 GMT+0000 (Coordinated Universal Time)
cuid: cmg9s5kfm000002la447aa1jn
slug: ghosts-vs-animals
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1759383574811/57f679cf-b20b-4c28-addb-7eaa887f26b5.png
tags: artificial-intelligence, machine-learning, computer-science, training, llm

---

[Andrej Karpathy](https://x.com/karpathy/status/1973435013875314729) just dropped what might be the most honest take I've seen from inside the frontier LLM labs in years. And it's fascinating because it's essentially this: "Yeah, the guy who wrote our Bible just told us we're doing it wrong. Awkward."

The "Bible" in question? Rich Sutton's ["The Bitter Lesson"](http://www.incompleteideas.net/IncIdeas/BitterLesson.html) - the 2019 essay that's become such gospel in AI research circles that people literally ask if ideas are sufficiently "bitter lesson pilled" before pursuing them. It's the kind of paper that [OpenAI engineers were reportedly told to memorize](https://www.macloo.com/ai/2024/03/11/the-bitter-lesson-of-ai-is-not-too-bitter/).

The awkward part? [Sutton himself doesn't think LLMs are bitter lesson pilled at all](https://www.dwarkesh.com/p/richard-sutton).

Well, perhaps you'd expect it from the guy who wrote the original article, but still.... heh.

## What's Actually Happening Here

Let me back up. **The Bitter Lesson in 30 seconds:**

The biggest lesson from 70 years of AI research is that general methods that leverage computation beat human-engineered solutions. Always. Every time we've bet on human cleverness over compute, compute won. [Chess](http://www.incompleteideas.net/IncIdeas/BitterLesson.html). Go. Computer vision. Translation. All of it.

**Why LLM researchers loved it:**

"Put compute on the x-axis, watch number go up and to the right" became the operating principle. [Scaling laws](https://arxiv.org/abs/2001.08361) as scripture. Just add more GPUs, more data, more parameters. The algorithm is simple - the bitter lesson is that simple works.

**Sutton's problem with LLMs:**

They're trained on fundamentally HUMAN data that is both: 1) human generated and 2) finite.

What do you do when you run out? How do you prevent human bias from contaminating everything?

(And look, we ARE running out - just ask anyone fighting [the copyright battles](https://www.theverge.com/2023/9/20/23882140/fair-use-ai-copyright-training-data-openai-stability-anthropic) over scraping more human text to train on.)

## The Actual Debate

In [Dwarkesh Patel's recent podcast](https://www.dwarkesh.com/p/richard-sutton), Sutton isn't just criticizing LLMs - he has a completely different architecture in mind. He's a "classicist" going back to Alan Turing's original vision of a "child machine."

**Sutton's vision:**
- No giant pretraining stage of imitating internet webpages
- No supervised finetuning (doesn't exist in animal kingdom - animals observe but aren't "teleoperated")
- Just interaction with a world via reinforcement learning
- Always learning at test time, not trained once and deployed
- Reward functions that are intrinsically motivated: "fun", "curiosity", prediction quality
- **"If we understood a squirrel, we'd be almost done"**

**Current LLM approach:**
- Massive pretraining on human text
- Supervised finetuning with human curators
- [RLHF](https://arxiv.org/abs/2203.02155) with human preference data
- Deploy and serve, no test-time learning
- Rewards tuned by human engineers

These aren't subtle differences. These are fundamentally incompatible philosophies about what intelligence IS.

## Where Karpathy Gets Real

And this is where I just love Karpathy's intellectual honesty. He doesn't bullshit. He essentially says: "Look, Sutton's right that we're not platonically bitter lesson pilled. But here's why we might not be wrong."

**The cold start problem:**

A baby zebra runs within minutes of birth. This isn't [tabula rasa](https://en.wikipedia.org/wiki/Tabula_rasa) learning. This is billions of parameters with initialization encoded in DNA, trained via evolution's "outer loop" optimization.

If you initialized an RL policy from scratch, it would spasm muscles randomly and get nowhere.

**"Pretraining is our crappy evolution."**

This might be Karpathy's most important line. We're not going to re-run evolution. But we DO have mountains of internet documents. Yes, it's supervised learning that's ~absent in the animal kingdom. But it's a way to gather soft constraints over billions of parameters so we're not starting from scratch.

## The Money Quote

**"Today's frontier LLM research is not about building animals. It is about summoning ghosts."**

Ghosts are:
- Muddled by humanity
- Thoroughly engineered by it
- Imperfect replicas, statistical distillations of humanity's documents
- Not platonically bitter lesson pilled, but "practically" bitter lesson pilled
- Perhaps just a different point in the space of possible intelligences

**So the analogy is:** "ghosts:animals :: planes:birds"

## So What Does This Mean for Us?

OK, I need to be honest here. I am absolutely the LEAST qualified person to adjudicate this debate between Sutton (literally wrote [THE textbook](https://mitpress.mit.edu/9780262039246/reinforcement-learning/) on reinforcement learning AND just won the Turing Award) and Karpathy (who oversaw the models being used by ~50% of the internet). But I'm going to anyway.

### 1. The Origin of "Intelligence" Matters

The choice between "animals" and "ghosts" isn't just technical, it's philosophical and ethical.

The animal approach says: "Intelligence emerges from interaction with environment"  
The ghost approach says: "Intelligence emerges from distilling human knowledge"

These have RADICALLY different implications for:

- **Alignment:** Ghosts inherit human biases; animals develop their own values
- **Controllability:** Ghosts are more predictable; animals might surprise us  
- **Resource requirements:** Ghosts need human data; animals need environments to explore
- **Failure modes:** Ghosts hallucinate human-like nonsense; animals might develop non-human goals

### 2. Source of the Data that Informs The Models Matters (Inate vs Learned)

We just committed [$500 BILLION to AI data centers](https://openai.com/index/five-new-stargate-sites/). That entire infrastructure is optimized for the GHOST approach - massive batch training on static datasets.

If Sutton's right about the animal approach being correct, we're building the wrong infrastructure at truly staggering scale.

Think about that. Half a trillion dollars betting on ghosts.

### 3. The Bitter Lesson is Woefully Misunderstood

The bitter lesson says "computation beats human cleverness."

But, much in the way that Quantum Mechanics should never be interpreted by non-physicists, people focusing on scaling compute have missed something important. LLMs are ALL human cleverness:
- Human-written training data
- Human-curated finetuning  
- Human preference judgments in RLHF
- Human-designed benchmarks

We've built the most computationally intensive systems in history to... imitate humans at scale.

That's not the bitter lesson. That's the expensive lesson.

## Where I Actually Land

Here's the thing though - I think Karpathy's "ghosts:animals :: planes:birds" framing is actually perfect.

We didn't figure out flight by copying birds. We built planes. They work completely differently. They have COMPLETELY different failure modes (planes don't get tired; birds don't fall from the sky if the engine fails). But they both accomplish "I want to get some place by air".

Maybe ghosts and animals are just different substrates for intelligence.

And honestly? For the applications we're actually building RIGHT NOW - code generation, writing assistance, customer service, content creation - ghosts might be exactly right.

You WANT human-like outputs for human-facing tasks. You WANT something that's read all of [Stack Overflow](https://stackoverflow.com/) when debugging code. You WANT statistical distillation of human knowledge for tasks humans invented.

**Where Sutton's approach matters:**

- Robotics (need real-world interaction)
- Actual AGI (whatever that means)
- Systems that operate in domains without human data
- Scenarios where human bias is actively harmful

But for "help me write this email" or "explain this error message"? Ghosts are great.

## The Uncomfortable Truths

The problem isn't that we're building ghosts instead of animals. The problem is that we're:

1. **Pretending ghosts are animals** - Marketing LLMs as "artificial general intelligence" when they're highly specialized human-imitators

2. **Not being honest about limitations** - Ghosts inherit ALL of humanity's biases, contradictions, and failures of reasoning

3. **Optimizing for the wrong metrics** - Benchmark scores on human-designed tests don't measure intelligence, they measure human-mimicry quality

4. **Missing the resource implications** - The ghost approach is FUNDAMENTALLY data-limited. We're running out of internet to train on. Then what?

5. **Building infrastructure that locks us in** - $500B in ghost-optimized data centers makes it REALLY HARD to pivot to animal approaches later

## The Way Forward

**What we should actually do:**

### Short term (ghosts are fine):
- Be honest about what we're building and its limitations
- Stop calling everything AGI
- Recognize ghosts excel at human-imitation tasks  
- Build better verification systems (because ghosts hallucinate)

### Medium term (explore both):
- Fund research on animal approaches in parallel
- Build infrastructure flexible enough for both paradigms
- Create benchmarks that actually measure INTELLIGENCE not human-mimicry
- Study where ghosts fail catastrophically vs. where animals would

### Long term (TBD):
- Maybe ghosts and animals converge (Karpathy's "finetuning ghosts toward animals")
- Maybe they diverge and we have multiple intelligence substrates
- Maybe Sutton's right and ghosts are a dead end
- Maybe we discover something completely different

**The crucial part:** Maintain "entropy of thought" (Karpathy's phrase). Don't let ghosts become THE only approach just because they're working well now.

## The Closing

Look, here's what I know for sure: We're at a genuinely fascinating moment in AI research where the guy who wrote the field's most influential essay is saying ["you're all doing it wrong"](https://www.dwarkesh.com/p/richard-sutton) and the guy training the most capable models is saying ["yeah, you might be right, but also here's why we're doing it anyway."](https://x.com/karpathy/status/1973435013875314729)

That's HEALTHY. That's what science is supposed to look like.

The problem isn't that we're building ghosts. The problem is if we forget that animals are possible. Or that something else entirely might be better.

Because here's the real bitter lesson: **The history of AI is littered with approaches that worked great until they didn't.**

[Expert systems](https://en.wikipedia.org/wiki/Expert_system). Neural networks (the first time). [Statistical machine translation](https://aclanthology.org/J03-1002/). Deep learning on small data. Every single time, we thought we'd figured it out. Every single time, we hit a wall and needed a paradigm shift.

Ghosts are working NOW. They're incredible. I use them every day. I used them to copy edit the very thing you're reading!

But Sutton's been right before. Like, [Turing Award-level](https://awards.acm.org/about/2024-turing) right. Maybe we should at least keep listening, even while we're summoning our ghosts.

The choice between ghosts and animals is a choice about what kind of intelligence we want to create, what kind of world we want to build, and what kind of future we're willing to bet on.

Choose wisely. Or better yet, don't choose at all - pursue both and see what emerges.

---

*Thanks to [Andrej Karpathy](https://karpathy.ai/) for the thoughtful analysis that sparked this post, and to [Dwarkesh Patel](https://www.dwarkesh.com/) for conducting the interview that started this whole conversation.*

---

*Want to learn how intelligent data pipelines can reduce your AI costs?* [***Check out Expanso***](https://expanso.io/). Or don't. Who am I to tell you what to do.*

**NOTE: I'm currently writing a book based on what I have seen about the real-world challenges of data preparation for machine learning, focusing on operational, compliance, and cost. [I'd love to hear your thoughts](https://github.com/aronchick/Project-Zen-and-the-Art-of-Data-Maintenance)!**