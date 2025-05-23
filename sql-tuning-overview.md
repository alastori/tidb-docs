---
title: SQL Tuning Overview
summary: SQL is a declarative language, meaning it describes the final result, not the steps to execute. TiDB optimizes execution and can execute parts of the query in any order. It's similar to GPS navigation, using statistics and live traffic data. Concepts include understanding query execution plans, SQL optimization, and controlling execution plans for better performance.
---

# SQL Tuning Overview

SQL is a declarative language. That is, an SQL statement describes _what the final result should look like_ and not a set of steps to execute in sequence. TiDB will optimize the execution, and is semantically permitted to execute parts of the query in any order provided that it correctly returns the final result as described.

A useful comparison to SQL optimization, is to describe what happens when you use GPS navigation. From your provided address, _2955 Campus Drive San Mateo CA 94403_, the GPS software plans the most time-efficient way to route you. It may make use of various statistics such as previous trips, meta data such as speed limits, and in modern cases, a live feed of traffic information. Several of these analogies translate to TiDB.

This section introduces several concepts about query execution:

- [Understanding the Query Execution Plan](/explain-overview.md) introduces how to use the `EXPLAIN` statement to understand how TiDB has decided to execute a statement.
- [SQL Optimization Process](/sql-optimization-concepts.md) introduces what optimizations TiDB is capable of using to improve query execution performance.
- [Control Execution Plans](/control-execution-plan.md) introduces ways to control the generation of the execution plan. This can be useful in cases where the execution plan decided by TiDB is suboptimal.
- [Index Advisor](/index-advisor.md) introduces how to let TiDB recommend indexes for you automatically based on your workload.