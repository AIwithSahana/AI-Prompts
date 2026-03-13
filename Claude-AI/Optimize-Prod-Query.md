# PROMPT
---------

```
Production Database Query Optimization Prompt
I’m facing a performance issue in our production database.
Database Type & Version: [PostgreSQL/MySQL/MongoDB/etc.]
Deployment Environment: [Cloud provider / On-prem]
Table Size: [approx row count]
Traffic Pattern: [reads/sec, writes/sec, peak usage]
Problem Statement:
This query is taking [X seconds/ms] in production.
Query:
[paste query]
Existing Indexes:
[list indexes]
Table Schema:
[columns + types]
Execution Plan (if available):
[paste EXPLAIN output]
Please help me with:
1.	Root cause of slowness (scan type, missing index, join issue, etc.)
2.	Specific index recommendations (and why)
3.	Query rewrite suggestions
4.	Tradeoffs (read vs write performance impact)
5.	Risks in production when applying changes
6.	Step-by-step safe rollout strategy
7.	Long-term scaling recommendations
Provide production-safe guidance, not generic advice.
```

---------

### For More Details Read: [Slow Queries Killing Your App?](https://techworldwithsahana.substack.com/p/slow-queries-killing-your-app)
