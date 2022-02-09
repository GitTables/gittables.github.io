---
title: Home
layout: default
---

# GitTables: a large-scale corpus of relational tables.

<p align="center">
    <img src="images/GitTables_pipeline.png" width="600" height="200"/>
    <figcaption style="text-align:center">Figure 1: high-level overview of how GitTables is constructed.</figcaption>
</p>

<!-- On this page:
- [Quick links](#quick-links)
- [About GitTables](#about-gittables)
- [Downloads](#downloads)
- [License](#license)
- [Citation](#citation)
- [Contact](#contact) -->

## Quick Links

 <!-- prettier-ignore -->
[dataset download](https://zenodo.org/record/4943312#.YMcUlzYzZ4I){:target="_blank"} | [paper](https://arxiv.org/pdf/2106.07258){:target="_blank"} | [github repository](https://github.com/madelonhulsebos/gittables){:target="_blank"} | [video presentation](https://www.youtube.com/watch?v=jEBKcmdIFzw){:target="_blank"}


## Quick Facts

GitTables is a large-scale corpus of relational tables extracted from CSV files in GitHub, that facilitates learning table representation models and applications in e.g. data management, data analysis, etc.

| Statistic                                   | Value                             |
|----------------------------------------------------|-----------------------------------|
| # tables                                           | 1.7M                              |
| average # columns                                  | 25                                |
| average # rows                                     | 209                               |
| # annotated tables (at least 1 column annotation)  | 1.0M (DBpedia), 1.5M (Schema.org) |
| # unique semantic types                            | 1218 (DBpedia), 924 (Schema.org)  |


## About GitTables

We aim at growing GitTables to at least 10M tables. Table columns in GitTables have been annotated with >2K different semantic types from [Schema.org](https://schema.org/){:target="_blank"} and [DBpedia](https://www.dbpedia.org/resources/ontology/){:target="_blank"}. Column annotations consist of semantic types, hierarchical relations, atomic data types and descriptions.

Figure 1 illustrates our approach to creating GitTables, on a high level.


### Why GitTables

Existing large-scale table corpora (like [WebTables](http://webdatacommons.org/webtables/){:target="_blank"}) contain tables extracted from HTML pages, limiting the capability to represent offline tables. These table corpora also lack semantic annotations, like semantic column types.

To train and evaluate table representation models for applications beyond the Web, e.g. data management, additional resources are needed with tables that resemble relational database tables. We built GitTables to facilitate that need.

Example use-cases that GitTables can facilitate that may use table representation models:

- Data search, integration, and validation.
- Data visualization and analysis recommendation.
- Schema autocompletion for e.g. database or knowledge base design.
- Query optimization.


### The dataset

On average the tables have 25 columns and 209 rows.
Each table is associated with table metadata, in the form of the original URL, license, and dimensions.

We also annotated table columns with real-world concepts, semantic types, that the columns refer to. These labels were extracted from the DBpedia and Schema.org ontologies.

We used two different annotation methods:
- Syntactic: string-based matching between column names and the semantic types,
- Semantic: embedding semantic types and column names using a pretrained FastText model trained on the Common Crawl dataset. The annotation corresponds to the most similar semantic type.

Figure 2 presents the distribution of semantic types of the tables per annotation method and ontology.

<p align="center">
    <img src="images/column_types_distributions_total.png" width="600" height="300"/>
    <figcaption style="text-align:center">Figure 2: distribution of top 25 semantic types resulting from different annotation methods and ontologies.</figcaption>
</p>


## Downloads

GitTables is hosted on Zenodo with DOI: 10.5281/zenodo.4943312. To ensure usage, extension and replication of GitTables on the longer term we publish the code for extraction, curation, and annotation, as well as the ontologies used for annotation. 

### Dataset downloads

The [GitHub Search API](https://docs.github.com/en/search-github/searching-on-github/searching-code){:target="_blank"} requires queries to include a keyword, which we refer to as a topic (e.g. ``id``, ``object``, etc.). We kept this structure in place so each zip file download contains the tables retrieved for a topic.

- [GitTables 1.7M (25.5 GB)](https://zenodo.org/record/4943312#.YMcUlzYzZ4I){:target="_blank"}: the dataset of 1.7M tables used for the analysis in the associated paper.
- [GitTables semantic type detection dataset (3.6 MB)](https://zenodo.org/record/5706316#.YgPNpn3MJ4I){:target="_blank"}: a dataset of 1101 tables and associated labels used for benchmarking semantic column type detection.
- GitTables (TBC): the entire dataset of 10M tables with metadata.


### Ontology downloads
The tables have been annotated with snapshots of DBpedia and Schema.org. These ontologies are provided in the form of a pickle file. Each pickle contains a pickled Pandas DataFrame with the semantic types per ontology.

- [DBpedia ontology (509 KB)](downloads/dbpedia_20210528.pkl){:target="_blank"}.
- [Schema.org ontology (619 KB)](downloads/schema_20210528.pkl){:target="_blank"}.


## License
GitTables is licensed under the [Creative Commons Attributions 4.0 International license](https://creativecommons.org/licenses/by/4.0/){:target="_blank"} (CC BY 4.0). The table data might however be licensed under different licenses as inherited from the GitHub repositories that the CSVs were retrieved from. 

A new version of GitTables will soon be released in which all tables have a license, and the license of each table is contained in the metadata. In the meantime, we suggest to use GitHub's License API to retrieve the license associated with a table (you can use the URL in the metadata to do so) to understand what restrictions apply to each table.


## Citation
[Our paper](https://arxiv.org/pdf/2106.07258.pdf){:target="_blank"} describes the construction, analysis and use-cases of GitTables in more detail.
If you use GitTables, please cite our paper:

```
@article{GitTables,
   title={GitTables: A Large-Scale Corpus of Relational Tables},
   author={Hulsebos, Madelon and Demiralp, Çağatay and Groth, Paul},
   journal={arXiv preprint arXiv:2106.07258},
   url={https://arxiv.org/abs/2106.07258},
   year={2021}
}
```


## Contact

GitTables is developed by:
- [Madelon Hulsebos](https://madelonhulsebos.github.io){:target="_blank"}, University of Amsterdam,
- [Çağatay Demiralp](https://hci.stanford.edu/~cagatay/){:target="_blank"}, Sigma Computing,
- [Paul Groth](http://pgroth.com){:target="_blank"}, University of Amsterdam.

Please consider reporting cases of personal or otherwise undesired tables in GitTables using the form below.
Feedback, suggestions and results from projects with GitTables are also very welcome!

<form
  action="https://formspree.io/f/xzbygjng"
  method="POST"
>
  <label>
    Your email:
    <br>
    <input type="email" name="_replyto">
  </label>
  <br>
  <label>
    Your message:
    <br>
    <textarea name="message"></textarea>
  </label>
  <br>
  <button type="submit">Send</button>
</form>

\\
Alternatively, you can send an email to {{site.email}}.
