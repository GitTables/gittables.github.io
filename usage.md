---
title: Usage
layout: default
---

# Welcome to the website of **GitTables**!

- [Getting GitTables](#getting-gittables)
- [Using GitTables](#using-gittables)
- [Replication](#replication)

## Getting GitTables

The table collections is stored on XXX. To facilitate different use, we publish different versions of GitTables:
- _GitTables_: the entire collection of tables with metadata (500 GB). This can be downloaded [here](https://google.com).
- _GitTables - sample_: a random sample of 1,000 tables from GitTables (100 MB). This can be downloaded [here](https://google.com).
- _GitTables - analysis_: the 1M tables used for the analysis in the associated paper. This can be downloaded [here](https://google.com).
- _GitTables - gold standard_: 1M tables with a strict annotation method to ensure a high quality of annotations. This can be downloaded [here](https://google.com).


## Using GitTables

Each table is stored in a Parquet file which can be easily processed by different data processing libraries like Pandas, Spark, and Pyarrow. Each Parquet file consists of the table itself and its metadata.

The table and metadata can be extracted using Pyarrow as follows:

{% highlight python %}
from pyarrow import parquet as pq

table = pq.read_table("<filename>.parquet")
metadata = table.schema.metadata
{% endhighlight %}

For more examples please refer to the respective notebooks [here](https://github.com/).


## Replication

The code used to create and analyse the tables can be found in [this GitHub repository](https://github.com/gittables). For both replication tasks, we recommend reading the paper to read the detailed steps.

#### Collection
The collection of tables itself is difficult to replicate due to the dependency on the unstable GitHub Search API: a search query today yields different results than the same query tomorrow. All code to construct the search queries, extract the CSV files, parse and annotate the tables can be found in the GitHub repository.

#### Experiments
The analysis has been conducted on the _GitTables (analysis)_ subset of GitTables. This collection consists of 1M tables.
The use-case is build on the same subset of tables. A notebook with the interactive analysis of the table collection can be found in the GitHub repository.
