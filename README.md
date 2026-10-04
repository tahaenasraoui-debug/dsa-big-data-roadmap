# DSA & Big Data Roadmap

![Status](https://img.shields.io/badge/status-in%20progress-orange.svg) ![License](https://img.shields.io/badge/license-MIT-green.svg) ![language](https://img.shields.io/badge/language-python-blue.svg) ![focus](https://img.shields.io/badge/focus-algorithms%20%2B%20data%20systems-informational.svg)

From core algorithms to pipelines that process datasets larger than memory. Interview-grade DSA first, then the data systems layer: storage formats, batch, and streaming.

## Table of Contents

1. [Workflow Overview](#workflow-overview)
2. [Prerequisites](#prerequisites)
3. [Phase 1: Fundamentals](#phase-1-fundamentals)
4. [Phase 2: Pattern Practice](#phase-2-pattern-practice)
5. [Phase 3: Algorithmic Rigor](#phase-3-algorithmic-rigor)
6. [Phase 4: Data Systems Foundations](#phase-4-data-systems-foundations)
7. [Phase 5: Big Data Tooling](#phase-5-big-data-tooling)
8. [Capstone Projects](#capstone-projects)
9. [Repository Layout](#repository-layout)
10. [Engineering Rules](#engineering-rules)
11. [Exit Criteria](#exit-criteria)

---

## Workflow Overview

```
 Complexity --> Core structures --> Pattern practice --> Rigor (DP, graphs)
                                                              |
 Data modeling <-- SQL + columnar <-- Batch (Spark) <-- Streaming (Kafka)
 (DDIA)            (DuckDB/Parquet)   (partitioning)     (windows, state)
```

## Prerequisites

- [ ] Python basics 
- [ ] Comfortable in a Linux shell
- [ ] Basic SQL syntax (SELECT, JOIN, GROUP BY)

## Phase 1: Fundamentals

Goal: Know the cost of every operation you write, and implement the core structures yourself.

| Resource | Type | Why |
|----------|------|-----|
| [Problem Solving with Algorithms and Data Structures using Python](https://runestone.academy/ns/books/published/pythonds3/index.html) | Free book | Python-first fundamentals |
| [Grokking Algorithms, 2nd Ed](https://www.manning.com/books/grokking-algorithms-second-edition) | BookInterview-grade algorithms, then data systems: Parquet, DuckDB, Spark, and Kafka pipelines. Typed, tested, with capstone ETL and streaming projects. | Fast visual first pass |
| [VisuAlgo](https://visualgo.net/) | Interactive | Watch structures execute step by step |
| [Python TimeComplexity wiki](https://wiki.python.org/moin/TimeComplexity) | Reference | Cost of list, dict, set, deque operations |

- [ ] Runestone: complexity, recursion, sorting, searching
- [ ] Grokking Algorithms: all chapters
- [ ] Memorize built-in container costs

**Deliverables**
- [ ] `src/dsa/structures/` with linked list, stack, queue, hash map, heap
- [ ] Tests for each in `tests/dsa/`

## Phase 2: Pattern Practice

Goal: Build speed on the recurring problem patterns.

| Resource | Type | Why |
|----------|------|-----|
| [NeetCode Roadmap](https://neetcode.io/roadmap) | Curated path | Pattern ordering |
| [NeetCode 150](https://neetcode.io/practice) | Problem list | Core practice set |
| [LeetCode](https://leetcode.com/) | Platform | Volume and weekly contests |
| [TheAlgorithms/Python](https://github.com/TheAlgorithms/Python) | GitHub repo | Reference implementations to compare, not copy |

- [ ] Arrays, hashing, two pointers, sliding window, stack, binary search
- [ ] Linked lists, trees, tries, heaps, backtracking
- [ ] Graphs, 1-D and 2-D DP, greedy, intervals
- [ ] Re-solve failed problems on days 3, 7, and 21

**Deliverables**
- [ ] NeetCode 150 complete
- [ ] 100 extra medium problems in `src/dsa/problems/`
- [ ] `docs/dsa_log.md` with complexity notes

## Phase 3: Algorithmic Rigor

Goal: Move from pattern matching to proofs and harder techniques.

| Resource | Type | Why |
|----------|------|-----|
| [Algorithms (Jeff Erickson)](https://jeffe.cs.illinois.edu/teaching/algorithms/) | Free book | Recursion, DP, graphs, proofs |
| [Introduction to Algorithms, CLRS](https://mitpress.mit.edu/9780262046305/introduction-to-algorithms/) | Reference textbook | Selective chapters only |
| [Competitive Programmer's Handbook](https://cses.fi/book/book.pdf) | Free PDF | Compact advanced techniques |
| [CSES Problem Set](https://cses.fi/problemset/) | Problem set | Classic problems with hidden tests |
| [Cracking the Coding Interview](https://www.crackingthecodinginterview.com/) | Book | Interview communication |

- [ ] Erickson: recursion, DP, shortest paths
- [ ] CLRS: amortized analysis, graph algorithms, NP-completeness
- [ ] CSES: Introductory, Sorting and Searching, Dynamic Programming sections
- [ ] 10 timed contests and 5 mock interviews

**Deliverables**
- [ ] 20 hard problems solved
- [ ] Written proof sketch for 5 algorithms in `docs/proofs.md`

## Phase 4: Data Systems Foundations

Goal: Understand how data is stored, indexed, and queried before touching distributed tools.

| Resource | Type | Why |
|----------|------|-----|
| [Designing Data-Intensive Applications](https://dataintensive.net/) | Book | Storage engines, replication, partitioning, streams |
| [Use The Index, Luke](https://use-the-index-luke.com/) | Free book | How B-tree indexes and query plans work |
| [SQLBolt](https://sqlbolt.com/) | Interactive | Fast SQL practice |
| [DuckDB Documentation](https://duckdb.org/docs/) | Docs | Local analytical SQL on Parquet |
| [Apache Parquet Documentation](https://parquet.apache.org/docs/) | Docs | Columnar format internals |
| [Mining of Massive Datasets](https://www.mmds.org/) | Free book | Hashing, LSH, Bloom filters, streaming algorithms |

- [ ] DDIA: Part I (storage and retrieval, encoding, data models)
- [ ] Read query plans with `EXPLAIN` on a real dataset
- [ ] Convert a CSV dataset to Parquet and compare size and query time
- [ ] MMDS: frequent itemsets, locality-sensitive hashing, stream mining

**Deliverables**
- [ ] `notebooks/indexing_benchmark.ipynb`
- [ ] `src/pipelines/bloom_filter.py` and MinHash/LSH with tests

## Phase 5: Big Data Tooling

Goal: Process data that does not fit in memory, in batch and as a stream.

| Resource | Type | Why |
|----------|------|-----|
| [Spark Quick Start](https://spark.apache.org/docs/latest/quick-start.html) | Docs | DataFrames and SQL on Spark |
| [Learning Spark, 2nd Ed](https://www.databricks.com/resources/ebook/learning-spark-book) | Free book | Spark internals and tuning |
| [Kafka Introduction](https://kafka.apache.org/intro) | Docs | Event streaming concepts |
| [Apache Airflow Documentation](https://airflow.apache.org/docs/) | Docs | Workflow orchestration |
| [dbt Documentation](https://docs.getdbt.com/docs/introduction) | Docs | Tested SQL transformations |
| [Data Engineering Zoomcamp](https://github.com/DataTalksClub/data-engineering-zoomcamp) | Repo | Project reference, not a course to binge |

- [ ] DDIA: Part III (batch and stream processing)
- [ ] Spark: partitions, shuffles, joins, caching
- [ ] Kafka: topics, partitions, consumer groups
- [ ] Orchestrate a daily pipeline with Airflow

**Deliverables**
- [ ] Spark job on 10 GB or more with a documented tuning log
- [ ] Kafka producer and windowed-aggregate consumer
- [ ] `docs/pipeline_design.md` with failure modes

## Capstone Projects

- [ ] Batch pipeline: ingest the [NYC TLC trip data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page) to Parquet, query with DuckDB, benchmark against pandas and Spark
- [ ] Streaming pipeline: replay events into Kafka, compute rolling aggregates, write to a queryable store
- [ ] Orchestrate both with Airflow and test transformations with dbt
- [ ] Write a design doc that justifies each tool choice and states when it would break

## Repository Layout

```
dsa-big-data/
├── README.md
├── pyproject.toml
├── docker-compose.yml        # Kafka, Spark, Airflow, Postgres
├── src/
│   ├── dsa/
│   │   ├── structures/
│   │   └── problems/         # one folder per topic
│   └── pipelines/
│       ├── batch/
│       └── streaming/
├── notebooks/
├── tests/
├── data/                     # gitignored
└── docs/
    ├── dsa_log.md
    ├── proofs.md
    └── pipeline_design.md
```

## Engineering Rules

These are strict. A phase is not complete until its deliverables follow all of them.

### 1. Daily 1:3 Theory-to-Building Ratio

- [ ] For every 1 hour of reading or watching, spend 3 hours building, solving, or running labs
- [ ] Log hours in `docs/log.md` at the end of each session
- [ ] No new chapter until the previous one has working code or a written lab report

### 2. Git Branch Hygiene

- [ ] `main` is always green and never receives direct commits
- [ ] One branch per deliverable: `phase-N/short-description`
- [ ] Small commits with imperative messages; squash-merge via PR after checks pass
- [ ] Delete branches after merge

### 3. Quality Gates

- [ ] `mypy --strict src/` passes before every PR
- [ ] `pytest --cov=src --cov-fail-under=80` passes
- [ ] `ruff check .` and `ruff format --check .` pass

### 4. Branch-Specific Rules

- [ ] Every solved problem has type hints, a complexity note in the docstring, and an edge-case test
- [ ] Never paste a solution you cannot rewrite from memory the next day
- [ ] Pipelines must be idempotent: rerunning a job never duplicates data
- [ ] Large datasets stay out of Git; document download steps instead

## Exit Criteria

- [ ] Solve most unseen LeetCode mediums in under 25 minutes
- [ ] Explain why a given query is slow using its query plan
- [ ] Run a Spark job and a Kafka consumer you designed, and explain their failure modes
- [ ] Choose between batch and streaming for a stated requirement and defend it
