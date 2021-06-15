---
title: Usage
layout: default
---

# Welcome to the website of **GitTables**!

- [Using GitTables](#using-gittables)
- [Replicating GitTables](#replicating-gittables)
- [Extending GitTables](#extending-gittables)

## Using GitTables

Each table is stored in a Parquet file which can be easily processed by different data processing libraries like Pandas, Spark, and Pyarrow. Each Parquet file consists of the table itself and its metadata.

The table and metadata can be extracted using Pyarrow as follows:

{% highlight python %}
from pyarrow import parquet as pq

table = pq.read_table("<filename>.parquet")
metadata = table.schema.metadata
{% endhighlight %}


## Replicating GitTables

The code used to extract, parse and annotate the tables from CSV files can be found in [this GitHub repository](https://github.com/gittables). For details on these procedures we recommend reading the paper. The table corpus itself is difficult to replicate exactly due to the dependency on the unstable GitHub Search API: a search query today yields different results than the same query tomorrow.

The analysis presented in the paper has been conducted on the GitTables 1.7M subset of GitTables, which consists of 1.7M tables. The GitHub repository provides Jupyter notebooks that were used for the analyses and experiments.


## Extending GitTables

< TBC >
