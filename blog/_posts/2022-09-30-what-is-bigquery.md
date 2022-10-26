---
layout: post
title:  "What is BigQuery?"
tags: bigquery data-warehouse gcp 
---

# What is BigQuery?

**Silent Reading Time**: 2 mins 5 secs

Checking the GCP documentation you would see:
>BigQuery is a fully managed enterprise data warehouse … BigQuery's serverless architecture lets you use SQL queries to answer your organisations biggest questions with zero infrastructure management. BigQuery's scalable, distributed analysis engine lets you query terabytes in seconds and petabytes in minutes. 
<!--more-->
>BigQuery maximises flexibility by separating the compute engine that analyses your data from your storage choices.

## What does that actually mean?
Well, BigQuery is a fully-managed, serverless warehouse; meaning users don’t need to worry about physical infrastructure, managing virtual machines, or worrying about scaling.  Google’s cloud services handle all that for you.  This enables scalable analysis over petabytes of data.

Users can access BigQuery via the web console, gcloud SDK, or a range of APIs and libraries for languages such as Python.

## What is BigQuery built with?
GCP, and Google itself, are built on three main building blocks:
- **Colossus** - a cluster-level file system, successor to the Google File System (GFS).  
- **Spanner** - a globally-consistent, scalable relational database.
- **Borg** - a scalable job scheduler that launches everything from compute to storage services. It was and continues to be a big influence on the design and development of Kubernetes.

BigQuery utilises Colossus for storage and Dremel as it’s query engine.  

Dremel is scalable, distributed query system developed at Google for interactively querying large datasets.  In fact, Dremel was the inspiration for Apache Drill, Apache Impala, and Dremio.

## When should I use BigQuery?
The use cases most suited for BigQuery are where you need to perform interactive ad-hoc queries of read-only datasets.  Typically BigQuery is used at the end of a data pipeline, once the data has been processed.

BigQuery is also "best" used for complex analysis - fully utilising the power of BigQuery's distributed architecture.  Conversely, small volumes of data or simple analytics can leave you waiting sometimes up to 8-10 seconds for what would normally be a sub-second query.  This is because…

## BigQuery is not a transactional database
While BigQuery can be access via API from NodeJS, PHP and other frameworks, the architecture means that it is not suitable for transactional queries.

## Why is BigQuery good for Big Data?
BigQuery stores data in a columnar format, achieving a high compression ratio and scan throughput. 

With this architecture, BigQuery works best when it has several petabytes of data to analyse. Similarly, due to it’s built-in cache, BigQuery works really well in cases where the data does not change often.

## Summary
In summary, BigQuery is an enterprise data warehouse bringing many built-in features and all the benefits of PaaS.

It can bring many benefits to the data landscape when use cases play to it's strengths.
