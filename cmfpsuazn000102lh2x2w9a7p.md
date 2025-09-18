---
title: "The Only Wrong Answer Is Centralize Everything: Lessons from the Data Frontier"
seoTitle: "Decentralization: Lessons from Data Exploration"
seoDescription: "Learn why centralized data models fail and explore distributed data strategies to enhance machine learning efficiency and reduce costs"
datePublished: Mon Aug 11 2025 07:00:00 GMT+0000 (Coordinated Universal Time)
cuid: cmfpsuazn000102lh2x2w9a7p
slug: the-only-wrong-answer-is-centralize-everything-lessons-from-the-data-frontier
tags: data-science, machine-learning, kubernetes, data-architecture, data-engineering, mlops, kubeflow

---

In the early days of [Kubeflow](https://www.kubeflow.org/), a customer shared a problem that perfectly captured where the entire ML industry was stuck.

Their data lived on-premises; their TPUs were in a [GCP datacenter](https://cloud.google.com/tpu). Every time they wanted to train a model, the process began with a `gsutil cp` command. The copy job would run for 6+ hours, overload their network, and rack up thousands in monthly [egress fees](https://cloud.google.com/vpc/network-pricing#egress-pricing). By the time the data finally arrived, it was already stale.

The model wasn't the hard part. The hard part was getting the data and the compute in the same room.

## The Industry's Misplaced Focus

This experience wasn't an anomaly. It was a perfect snapshot of the industry. For years, we've been collectively focused on the most visible parts of machine learning while ignoring the foundational bottleneck.

We obsess over:

* **Model Architectures**: Debating the merits of [Transformers](https://arxiv.org/abs/1706.03762) versus other models
    
* **Hyperparameter Tuning**: Squeezing out another fraction of a percentage of accuracy using tools like [Optuna](https://optuna.org/) or [Ray Tune](https://docs.ray.io/en/latest/tune/index.html)
    
* **Massive Scale**: Building ever-larger models like [GPT-4](https://openai.com/research/gpt-4) or [Llama 3](https://llama.meta.com/), believing more parameters will magically unlock more intelligence
    

This is like designing a Formula 1 engine and then trying to run it on unrefined crude oil. The most sophisticated model in the world is useless if its training data is slow, messy, or inaccessible. The work isn't just in the engine; it's in the refinery. And just as oil refineries are distributed near extraction sites, compute needs to be distributed near data sources.

## Why Data Lakes Failed to Deliver

The conventional wisdom for the last decade was to centralize everything. "Build a [data lake](https://aws.amazon.com/big-data/datalakes-and-analytics/what-is-a-data-lake/)!" was the rallying cry. Copy all your data into one massive repository using tools like [AWS S3](https://aws.amazon.com/s3/), [Azure Data Lake](https://azure.microsoft.com/en-us/solutions/data-lake/), or [Google Cloud Storage](https://cloud.google.com/storage), and all your problems will be solved.

It's a great theory for a boardroom, but a fantasy in practice. Data has gravity. It's heavy, expensive to move, and rooted in place by business and regulatory realities. Attempting to centralize it creates a set of predictable failures:

* **Massive Egress Costs**: The exact `gsutil cp` problem, but now institutionalized and scaled up—thousands of dollars monthly just to move data between [cloud regions](https://cloud.google.com/compute/docs/regions-zones)
    
* **Data Staleness**: The data is often out-of-date by the time it lands, making real-time applications impossible
    
* **Operational Complexity**: The [ETL pipelines](https://www.databricks.com/glossary/etl-pipeline) required to feed the lake become brittle, complex monsters that require dedicated teams to maintain
    

We learned to break apart monolithic applications into [microservices](https://martinfowler.com/articles/microservices.html). Yet, we're still trying to build monolithic data stores.

## The Kubernetes Model: Orchestration Over Centralization

We've solved this kind of problem before. A decade ago, running distributed applications was chaos until orchestrators like [Kubernetes](https://kubernetes.io/) provided a control plane to manage the complexity. We learned to build reliable systems from unreliable components, as described in Google's [Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/) principles.

It's time we apply the same principles to data. The goal should not be to move petabytes of data to a central computer. The goal should be to move the compute to the data, wherever it lives.

This is the core idea behind "Compute over Data." It means running your training job where your data lives—whether that's an edge device, on-prem server, or specific cloud region—rather than copying terabytes to a central location. It's about building a new kind of data orchestration designed for a distributed, multi-cloud world, similar to what projects like [Apache Spark](https://spark.apache.org/) attempted but with true edge-to-cloud capabilities.

## The Path Forward: Key Pillars We're Tackling

At [Expanso](https://expanso.io), we've been tackling these key pillars of the data logistics challenge:

### Data Gravity as a Law of Physics

Moving data is the most expensive operation in distributed systems. A single training run can cost thousands just in transfer fees—before you've even started computing. We've seen customers reduce their data movement costs by 70% by processing data where it lives, following principles outlined in [Data Gravity Index reports](https://www.digitaldatainsights.com/resource/data-gravity-index-dgi/).

### From ETL to ELT and Beyond

Modern data processing needs to evolve past the copy-transform-load paradigm. We're building systems that can filter, aggregate, and process data at the source, only moving the refined results. Think of it as [edge computing](https://www.ibm.com/cloud/what-is-edge-computing) for your data pipeline.

### What Data Orchestration Actually Means

True data orchestration means:

* **Discovery**: Knowing what data exists across your distributed infrastructure using modern [data catalog](https://www.alation.com/blog/what-is-a-data-catalog/) approaches
    
* **Governance**: Maintaining security and compliance without centralization, following frameworks like [GDPR](https://gdpr.eu/) and [CCPA](https://oag.ca.gov/privacy/ccpa)
    
* **Processing**: Running compute where data lives, not the other way around
    
* **Coordination**: Managing distributed jobs as easily as local ones
    

At Expanso, we believe solving the data logistics problem is the single biggest unlock for ML. The industry has spent a decade perfecting the engine—now it's time to fix the fuel supply.

## The Bottom Line

The future of ML isn't in bigger models or better algorithms alone. It's in fundamentally rethinking how we handle data. Just as Kubernetes taught us that orchestration beats centralization for compute, we need to learn the same lesson for data.

The principles are being validated across the industry—from [Snowflake's](https://www.snowflake.com/) approach to data sharing without movement, to [Databricks' Unity Catalog](https://www.databricks.com/product/unity-catalog) for distributed governance, to emerging standards like [Apache Iceberg](https://iceberg.apache.org/) for distributed table formats.

Stop admiring the problem. Start fixing the foundation.

**What data movement costs or delays are blocking your ML initiatives today?** We're interested in your perspective—comment below.

---

*David Aronchick is CEO and co-founder of* [*Expanso*](https://expanso.io)*, building the future of distributed data processing. Previously, he led product management for* [*Kubernetes*](https://kubernetes.io/) *and* [*Kubeflow*](https://www.kubeflow.org/) *at Google, and Open Source Machine Learning Strategy at* [*Azure*](http://azure.microsoft.com)*.*

**NOTE: I'm currently writing a book based on what I have seen about the real-world challenges of data preparation for machine learning, focusing on operational, compliance, and cost.** [**I'd love to hear your thoughts**](https://github.com/aronchick/Project-Zen-and-the-Art-of-Data-Maintenance)**!**