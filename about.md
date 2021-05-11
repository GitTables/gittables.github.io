---
layout: page
title: About
permalink: /about/
---

## GitTables

This table collection consists of tables retrieved from CSV files from GitHub and annotated by properties and classes from the DBpedia and Schema.org ontologies.

#### File structure
The GitHub Search API requires a 'topic' string to be included in the query. For example, you can search code files related to the topic "thing". This will return all CSV files that contain the string "thing". We have kept this file structure in place. This results in the following structure:

```
├── topic/
│   ├── parquet_files/
│   │   └── <table_1>.parquet <-- Parquet file with the table and metadata.
│   └── metadata.txt          <-- Number of URLs returned by the original query.
│   └── queries.txt           <-- Segmented queries used to extract the CSVs.
```

#### Tables
A table consists of:
- Columns: reflects the measured attribute.
- Rows: assumed to represent a measured entity.
- Header: denoting the semantic references of each column.
- Values: reflecting measurements of the entity and.

#### Metadata
The table-specific metadata consists of the following:
- URL to the original CSV file on GitHub.
- DBpedia column annotations: annotations, label descriptions, domains, expected data types.
- Schema.org annotations: annotations, descriptions, domains/classes, expected data types.


## Reference
The paper describes the construction and analysis of GitTables in more detail.

```
[1] Anonymous, Anonymous, Anonymous. (2021, ...). GitTables: a large-scale annotated table collection from GitHub. In Proceedings of .... (pp. ...-...).
```

## License
GitTables is licensed under the MIT license. The original CSV files might however be licensed under a different license as inherited from the GitHub repository that they were retrieved from.


## The team behind GitTables

This table collection has been established by:
- Anonymous at Anonymous.
- Anonymous at Anonymous.
- Anonymous at Anonymous.


