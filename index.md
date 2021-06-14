---
title: Home
layout: home
---

# Welcome to the website of **GitTables**!

- [About GitTables](#about-gittables)
    - [The team behind GitTables](#the-team-behind-gittables)
    - [Why GitTables](#why-gittables)
    - [The corpus](#the-corpus)
- [Downloads](#downloads)
    - [Corpus downloads](#corpus-downloads)
    - [Ontology downloads](#ontology-downloads)
- [License](#license)
- [Citation](#citation)
- [News](#news)

## About GitTables

GitTables is a corpus of currently 1.7M relational tables extracted from CSV files in GitHub. Our continuing curation aims at growing the corpus to at least 20M tables. Table columns in GitTables have been annotated with more than 2K different semantic types from Schema.org and DBpedia. Our column annotations consist of semantic types, hierarchical relations, range types and descriptions.

The high-level pipeline in Figure 1 illustrates how GitTables was created.

<p align="center">
    <img src="images/GitTables_pipeline.png" width="500" height="200"/>
    <figcaption style="text-align:center">Figure 1: high-level pipeline of the process of constructing GitTables.</figcaption>
</p>


### The team behind GitTables
- [Madelon Hulsebos](https://madelonhulsebos.github.io), Sigma Computing and University of Amsterdam,
- [Çağatay Demiralp](https://hci.stanford.edu/~cagatay/), Sigma Computing,
- [Paul Groth](http://pgroth.com), University of Amsterdam.

Questions or suggestions? Please contact m.hulsebos < at > uva.nl.


### Why GitTables

Existing table corpora primarily contain tables extracted from HTML pages, limiting the capability to represent offline database tables. To train and evaluate high-capacity models for applications beyond the Web, additional resources are needed with tables that resemble relational database tables. We built GitTables to facilitate that need.


### The corpus

The tables in GitTables were extracted from CSV files. On average the tables have 25 columns and 209 rows.
We annotated table columns with real-world concepts that the columns refer to. The labels for these column annotations (referred to as semantic types) were extracted from the DBpedia and Schema.org ontologies. We used two different annotation methods:
- Syntactic: string-based matching between column names and the semantic types,
- Semantic: embedding semantic types and column names using a pretrained FastText model trained on the Common Crawl corpus. The annotation corresponds to the most similar semantic type.

Figure 2 presents the distribution of semantic types of the tables per annotation method and ontology.

<p align="center">
    <img src="images/column_types_distributions_total.png" width="600" height="300"/>
    <figcaption style="text-align:center">Figure 2: distribution of top 25 semantic types resulting from different annotation methods and ontologies.</figcaption>
</p>

Each table stored in a Parquet file, and consists of:
- The table itself with columns, rows, cell values and a header with the original column names.
- The table metadata:
    - URL to the original CSV file,
    - Column annotations from different annotation methods and ontologies,
    - Table ID,
    - Table dimensions,
    - Data types inferred with Pandas,
    - Table topic annotation derived from column annotations.



## Downloads

GitTables is hosted on Zenodo with DOI: **10.5281/zenodo.4943312**. To facilitate different use-cases, we publish different versions of GitTables. To ensure usage, extension and replication of GitTables on the longer term, we publish the ontologies used for annotation as well. 

### Corpus downloads

The GitHub Search API requires queries to include a keyword, which we refer to as a 'topic'. For example, you can search code files related to the topic 'thing'. This returns all CSV files that contain the string 'thing'. We have kept this 'topic' structure in place, hence each zip file consists of the tables retrieved for that topic.

- GitTables: the entire corpus of 20M tables with metadata (X GB). TBC.
- GitTables 1.7M: the corpus of 1.7M tables used for the analysis in the associated paper (25.5 GB). This dataset can be found on Zenodo [here](https://zenodo.org/record/4943312#.YMcUlzYzZ4I).


### Ontology downloads
The tables have been annotated with snapshots of DBpedia and Schema.org. These ontologies are provided in the form of a pickle file. Each pickle contains a pickled Pandas DataFrame that can be read through Pandas.

- DBpedia ontology: direct download through [this link](data/dbpedia_20210528.pkl) (509 KB).
- Schema.org ontology: direct download through [this link](data/schema_20210528.pkl) (619 KB).


## License
GitTables is licensed under the [Creative Commons Attributions 4.0 International license](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0). The table data might however be licensed under different licenses as inherited from the GitHub repositories that the CSVs were retrieved from.


## Citation
The paper describes the construction and analysis of GitTables in more detail and can be downloaded [here](https://google.com).
If you use GitTables, please cite our paper:

```
@article{GitTables,
   title={GitTables: A Large-Scale Corpus of Relational Tables},
   author={Hulsebos, Madelon and Demiralp, Çağatay and Groth, Paul},
   journal={arXiv preprint arXiv:XXXX.YYYYYY},
   year={2021}
}
```


## News
