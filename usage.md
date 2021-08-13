---
title: Usage
layout: default
---

# Welcome to the website of **GitTables**!

- [Processing table files](#processing-table-files)
- [Responsible use](#responsible-use)
- [Replicating GitTables](#replicating-gittables)
- [Extending GitTables](#extending-gittables)


## Processing table files

Each table is stored in a Parquet file which can be easily processed by different data processing libraries like Pandas, Spark, and Pyarrow. Each Parquet file consists of the table itself and its metadata.

The table and metadata can be extracted using Pyarrow as follows:

{% highlight python %}
from pyarrow import parquet as pq

table = pq.read_table("<filename>.parquet")
metadata = table.schema.metadata
{% endhighlight %}


## Responsible use

To minimize the risk of spreading undesired content, we anonymized columns that were found to contain personal identifiable information. We also removed tables with content detected to stem from social media platforms Twitter, Facebook and Reddit, which could contain harmful content. In case you find any remaining personal or harmful content in GitTables, please report it to us using [the contact form](/#contact).

It is also important to assess derived artefacts on the presence of any negative bias before deploying or publishing them. In case additional biases are observed we would like to be notified so that we can communicate this to other users of GitTables.


## Replicating GitTables

The code used to extract, parse and annotate the tables from CSV files can be found in [this GitHub repository](https://github.com/madelonhulsebos/gittables). For details on these procedures we recommend reading the paper. The table corpus itself is difficult to replicate exactly due to the dependency on the unstable GitHub Search API: a search query today yields different results than the same query tomorrow.

The analysis presented in the paper has been conducted on the GitTables 1.7M subset of GitTables, which consists of 1.7M tables. The GitHub repository provides Jupyter notebooks that were used for the analyses and experiments. 

To understand the quality of the column annotations obtained by the GitTables annotation pipeline versus the human-labeled annotations, we annotated the human-labeled T2Dv2 benchmark using the DBpedia ontology and our annotation pipelines. For the semantic pipieline and syntactic pipeline we find the same annotation as T2Dv2 in 54% and 61% of the table columns. We manually reviewed the deviating annotations for both pipelines and find that the GitTables annotations (based on the DBpedia ontology as on 28-05-2021) are more accurate in many cases. Our manual reviews (n=3) can be downloaded through [this link](downloads/GitTables_T2Dv2_incorrect_annotation_review.xlsx).


## Extending GitTables

< TBC >
