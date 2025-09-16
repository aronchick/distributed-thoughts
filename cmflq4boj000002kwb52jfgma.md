---
title: "WTF Do You Spend $300B On?: The Oracle-OpenAI Deal Decoded"
seoDescription: "Discover the challenges and expenses behind OpenAI's $300 billion Oracle deal, revealing a true AI cost breakdown: 80% data prep, 20% training"
datePublished: Mon Sep 15 2025 07:00:00 GMT+0000 (Coordinated Universal Time)
cuid: cmflq4boj000002kwb52jfgma
slug: wtf-do-you-spend-300b-on-the-oracle-openai-deal-decoded
tags: oracle, data, machine-learning, distributed-systems, openai, data-pipelines

---

OpenAI just signed a $300 billion deal with Oracle for AI infrastructure.

My first thought: What do you spend $300 billion on?

Seriously. Three hundred billion dollars. That’s more than the GDP of Finland. It’s 30 times OpenAI’s annual revenue. It’s enough to buy every single person in America a new iPhone.

So I did what any reasonable person would do. I grabbed a spreadsheet and started doing the math. And what I found is instructive (or terrifying) for any executive planning an AI initiative.

## Let’s Start With the GPU Math

When you hear “$300 billion for AI,” your brain immediately goes to GPUs. Those beautiful, expensive chips that make the magic happen and may or may not be a critical pillar of the US GDP. So let’s price this out.

OpenAI is getting 4.5 gigawatts of compute capacity from Oracle. In GPU terms, that’s roughly 2 million high-end processors. Let’s do the math:

```plaintext
    H100 GPUs (the good stuff): $30,000 each
    × 2 million GPUs
    = $60 billion
    
    Over 5 years = $12 billion per year
```

But wait, you need more than just GPUs. You need racks, networking, cooling, buildings. Let’s be generous and double it:

```plaintext
    GPUs + Infrastructure: $24 billion per year
    Oracle contract: $60 billion per year
    Missing money: $36 billion per year
    
    Over 5 years: $180 billion unaccounted for
```

**That’s a $180 billion gap.**

Where the hell is the rest going?

## The Uncomfortable Answer

I’ve been lucky enough to work in several hyperscale clouds, and the engineers who’ve built these systems always come back and tell you something along the lines of: “You think the GPUs are the expensive part? Oh, you sweet summer child.”

The truth sounds so bizarre, but it’s true: **The actual training is the cheap part.**

Before you can train a single parameter, you need to:

### 1\. Collect the Data (15% of compute = $9 billion/year)

* Crawl massive data sets. Multiple times a day.
    
* Parse, oh let’s be conservative, 3.5 petabytes of HTML, JavaScript, and garbage
    
* Store it all somewhere accessible
    

An SEO company I am friendly with once told me: “We spent $8 million just crawling our target domains. That was month one.”

### 2\. Deduplicate Everything (20% of compute = $12 billion/year)

The internet is 90% copies. The same article on 50 sites. The same Stack Overflow answer everywhere. You need to find near-duplicates across trillions of tokens.

But here’s the kicker: You can’t just check exact matches. “The quick brown fox” and “A quick, brown fox” need to be caught. Now do that for every possible pair in your trillion-token dataset.

**Computational complexity: O(n²)** **Actual cost: Your entire Q3 budget**

(Ok it’s not ACTUALLY your Q3 budget, but … it’s a lot.)

### 3\. Filter for Quality (25% of compute = $15 billion/year)

Run classification models on every single document:

* Is this text coherent?
    
* Is it factual?
    
* Is it toxic?
    
* Is it AI-generated? (AI to catch AI? Recursion stack overflow error.)
    
* Does it contain PII?
    
* Is it copyright-safe?
    

Each document needs MANY classification passes (let’s call it 5-10). At a trillion documents, that’s 10 trillion model inference calls before you’ve trained anything.

### 4\. The Experimentation Graveyard (20% of compute = $12 billion/year)

Now you’ve got all your data - ready to go! But wait… **Most training runs fail.**

* Wrong learning rate? $5 million down the drain
    
* Bad data mixture? Another $10 million gone
    
* Model diverged at hour 672? There goes $15 million
    
* Discovered a bug after training? Start over. $20 million.
    

Industry estimate: For every GPT-4 that ships, there were 10-20 failed attempts. If the final run cost $100 million, the failures cost $1-2 billion.

## The Shocking Final Tally

When you add it all up, here’s a back of the envelope where that $60 billion per year actually goes:

| **What Everyone Thinks** | **Cost** | **Reality** |
| --- | --- | --- |
| Training GPT-5, 6, 7 | $60B/year | Nope |
|  |  |  |
| **What It Actually Is** |  |  |
| Data collection & storage |  | $9B/year |
| Deduplication |  | $12B/year |
| Quality filtering |  | $15B/year |
| Failed experiments |  | $12B/year |
| **Actual model training** |  | **$12B/year** |

**Only 20% goes to actual training. The other 80% is data prep and failures.**

And YES I am probably wrong by about … 25%? But even if I’m off by a factor of 2, it’s still a HUGE portion of the budget.

## This Is Every Organization (Including Yours)

Before you feel superior about AI “waste,” let me tell you about every enterprise AI project I’ve seen (all values anonymized to protect the innocent :):

**Major Bank ML Initiative:**

* Total budget: $2 million
    
* Data preparation: $1.5 million
    
* Failed experiments: $400k
    
* Actual model training: $100k
    
* Models that made it to production: 1
    

**Retail Company’s “AI Transformation”:**

* Year 1 spend: $5 million
    
* Data lake setup: $2 million
    
* Data cleaning: $1.5 million
    
* “POCs” that went nowhere: $1 million
    
* Actual AI in production: $500k
    

**Transportation Giant’s “AI-Powered Logistics”:**

* $3 million just cleaning GPS data from their fleet
    
* $2.5 million merging incompatible routing systems
    
* $2 million on failed predictive maintenance attempts
    
* $2 million on smart routing POCs that never shipped
    
* Only $500k on the AI that’s actually optimizing routes
    

See the pattern? **Everyone spends 80% on data prep. Everyone.**

## Why Your AI Project Will Follow the Same Pattern

The uncomfortable truth is that this ratio—80% data prep, 20% actual AI—is physics, not inefficiency.

Here’s why your organization will hit the same wall:

### Your Data Is Garbage

* It’s in 47 different systems
    
* With 12 different schemas
    
* Half of it is duplicated
    
* A quarter is wrong
    
* Nobody knows where the good stuff is
    

### Your Experiments Will Fail

* Your first model won’t work
    
* Neither will your second
    
* Or your third
    
* The one that works will break in production
    
* You’ll start over
    

### You’ll Discover Hidden Costs

* “We need to label the data” - $
    
* “We need to clean the data” - $$
    
* “We need more data” -
    
* “We need different data” - $
    
* “We need to start over” - Everything
    

## What This Means for Your AI Project

### For Enterprises

Stop budgeting EXCLUSIVELYfor model training. Start budgeting for end-to-end pipelines. Whatever you’re allocating for AI, flip the ratio:

* Current plan: 80% models, 20% data
    
* Reality: 20% models, 80% data
    

### For Startups

You can’t compete with OpenAI’s compute budget. But here’s the secret: You don’t need to. They’re spending $45 billion on data prep because they’re training on “all human knowledge.” You can probably get by with a focused dataset and $50k.

### For Engineers

Job security! While everyone’s learning prompt engineering, the real demand is for people who can build data pipelines that don’t break when you throw petabytes at them.

## The $300 Billion Reality Check

The Oracle-OpenAI deal isn’t insane. It’s insanely honest.

For the first time, a major AI company is admitting what it really costs to build these systems. Not the sexy GPU costs. Not the brilliant model architectures. The grinding, exhausting, expensive reality of data preparation.

Every organization rushing to build AI is about to learn what OpenAI already knows:

* Your data is messier than you think
    
* Cleaning it costs more than training
    
* Most of your experiments will fail
    
* The infrastructure you need isn’t what you expect
    

## The Bottom Line

This deal reveals an uncomfortable truth: **We don’t ONLY have an AI problem. We have a data problem.**

In AI, the model is the celebrity, but data prep is the [“below the line”](https://en.wikipedia.org/wiki/Below-the-line_\(filmmaking\)) people who make the movie. And just like in Hollywood, the crew costs more than the star.

Oracle and OpenAI aren’t JUST building the future of AI. They’re building industrial-scale data refineries that occasionally produce intelligence as a byproduct.

And at $300 billion, they’re showing us what it really costs to turn the internet’s garbage into gold—unless you’re smart about where and how you process that data.

## There’s Another Way

This is exactly why we built [Expanso](https://expanso.io/). While OpenAI LIKELY spends $45 billion moving and cleaning data in centralized data centers a year (or more!), we’re building intelligent pipelines that process data where it lives.

Think about it: Why move petabytes to the cloud when you can:

* Process data at the edge, where it’s created
    
* Move only insights, not raw data
    
* Skip 80% of the deduplication (because you never centralized the duplicates)
    
* Reduce data prep costs by 10x through distributed processing
    

The question isn’t whether they need to spend that much. Money will always fill the hole. The question is whether there’s a more inefficient way to allocate the capital, and at Expanso we like to think there is.

The future isn’t about who can afford the biggest data center. It’s about who can be smartest about never needing one.

---

*What percentage of your AI budget goes to data prep? Are you seeing the same 80/20 split? Drop me a note—I’m collecting data on the real economics of AI, and I promise I’ll deduplicate it properly.*

### **In addition to being CEO of** [**Expanso**](https://expanso.io)**, I’m currently writing a book based on what I have seen about the real-world challenges of data preparation for machine learning, focusing on operational, compliance, and cost.** [**I’d love to hear your thoughts**](https://bac.al/iuWTbv8)**!**