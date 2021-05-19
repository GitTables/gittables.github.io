---
title: Home
layout: home
---

# Welcome to the website of **GitTables**!

- [About GitTables](#about-gittables)
- [License](#license)
- [Paper](#paper)
- [The team behind GitTables](#the-team-behind-gittables)
- [News](#news)

## About GitTables

This table collection consists of tables retrieved from CSV files from GitHub and annotated by properties and classes from the DBpedia and Schema.org ontologies.

#### Tables
The full GitTables collection consists of XXM tables.
These tables have on average X columns and Y rows.

Each table consists of:
- Columns: reflects the measured attribute.
- Rows: assumed to represent a measured entity.
- Header: denoting the semantic references of each column.
- Values: reflecting an attribute's value of an entity.

Figure 1 illustrates the distribution of domains of the tables, as well as the columns inside those tables.

<Figure 1 placeholder>

#### Metadata
The table-specific metadata consists of the following:
- URL to the original CSV file on GitHub.
- DBpedia column annotations: annotations (syntactic and semantic), label descriptions, domains, expected data types.
- Schema.org annotations: annotations (syntactic and semantic), label descriptions, domains/classes, expected data types.

#### File structure
The GitHub Search API requires a 'topic' string to be included in the query. For example, you can search code files related to the topic "thing". This will return all CSV files that contain the string "thing". We have kept this file structure in place, which yields the following file structure:

```
├── topic/
│   ├── tables/
│   │   └── <table_1>.parquet <-- Parquet file with the table and metadata.
│   └── metadata.txt          <-- Number of URLs returned by the original query.
│   └── queries.txt           <-- Segmented queries used to extract the CSVs.
```


## License
GitTables is licensed under the MIT license. The table data might however be licensed under different licenses as inherited from the GitHub repository that the CSVs were retrieved from.


## Paper
The paper describes the construction and analysis of GitTables in more detail.

```
[1] Anonymous, Anonymous, Anonymous. (2021, ...). GitTables: a large-scale annotated table collection from GitHub.
```


## The team behind GitTables

This table collection has been established by:
- Anonymous at Anonymous.
- Anonymous at Anonymous.
- Anonymous at Anonymous.


## News
