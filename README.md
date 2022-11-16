# 📖 The DBLP Discovery Dataset (D3)

[![arXiv](https://img.shields.io/badge/arXiv-2204.13384-b31b1b.svg)](https://arxiv.org/abs/2204.13384)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.7069915.svg)](https://doi.org/10.5281/zenodo.7069915)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

This repository provides metadata to papers from [DBLP](dblp.org) (> 5.9m articles, > 3.8m authors as of September 2022) crawled with the [cs-insights-crawler](https://github.com/gipplab/cs-insights-crawler).

> As of version 2.1 of the dataset and version 1.3.0 of the crawler, the dataset adds the [Computer Science Ontology](https://github.com/jpwahle/lrec22-d3-dataset/issues/1) with information about sub-fields.

> As of version 2.0 of the dataset and version 1.0.2 of the crawler, the dataset uses [SemanticScholar](https://semanticscholar.org) data. We will release a blog post soon about this update and how it affects porting from version 1.0.

The goal is to keep this corpus monthly updated and provide a comprehensive repository of the full DBLP collection.

This repository provides the following exports: 
1. 📖 All paper entries with metadata as jsonl: **size 2.7G** (gz) [download here](https://zenodo.org/record/6477785).
2. 📖 All paper entries with metadata as csv: **size 2.5G** (gz) [download here](https://zenodo.org/record/6477785).
3. 🙋 All author entries with metadata as jsonl: **size 188M** (gz) [download here](https://zenodo.org/record/6477785).
4. 🙋 All author entries with metadata as csv: **size 168M** (gz) [download here](https://zenodo.org/record/6477785).

```python
>>> import pandas as pd
>>> pd.read_csv('papers.csv', delimiter="\t")

                                                title                                            authors                  externalids.DBLP                                           abstract
0   The U-City Paradigm: Opportunities and Risks f...    [{'authorId': '2194162', 'name': 'F. Rotondo'}]             journals/fi/Rotondo12  Volunteered Geographic Information (VGI) tools...
1   FPGA-based design and implementation of an app...  [{'authorId': '12653318', 'name': 'Server Kasa...                 conf/fpt/KasapR12  In this paper, we introduce a field-programmab...
2   Influence of PEEK Coating on Hip Implant Stres...  [{'authorId': '1409483450', 'name': 'Jesica An...  journals/cmmm/Anguiano-Sanchez16  Stress shielding is a well-known failure facto...
3   RF signal generator using time domain harmonic...  [{'authorId': '2053358173', 'name': 'Kazuo Nak...      journals/ieiceee/NakanoAIM12  This paper proposes an RF signal generator usi...
4   On the number of cycles of length k in a maxim...  [{'authorId': '144779600', 'name': 'S. Hakimi'...            journals/jgt/HakimiS79  Let G be a maximal planar graph with p vertice...
..                                                ...                                                ...                               ...                                                ...
95  User-Relative Names for Globally Connected Per...  [{'authorId': '144067653', 'name': 'B. Ford'},...      journals/corr/abs-cs-0603076  Personal devices such as mobile phones, digita...
96  Using sentence connectors for evaluating MT ou...  [{'authorId': '2397323', 'name': 'E. M. Visser...      journals/corr/cmp-lg-9608019  This paper elaborates on the design of a machi...
97  Analysis of Fixed Outage Transmission Schemes:...  [{'authorId': '2111193263', 'name': 'Peng Wu'}...       journals/corr/abs-0710-1595  This paper studies the performance of transmis...
98  Real Time Models of the Asynchronous Circuits:...       [{'authorId': '2058949', 'name': 'S. Vlad'}]      journals/corr/abs-cs-0412090  The chapter from the book introduces the delay...
99                                Approximate Sorting  [{'authorId': '1695806', 'name': 'J. Giesen'},...          journals/fuin/GiesenSS09  We show that any comparison based, randomized ...
```


The code to crawl this dataset was migrated to the [CS-Insights Project](https://github.com/gipplab/cs-insights-main) and now lives [here](https://github.com/gipplab/cs-insights-crawler).

We are hoping that this corpus can be helpful for analysis relevant to the computer science community. 

**Please cite/star 🌟 this page if you use this corpus**


## 💻 Features

The exports contain the following features:

### Papers

| Feature | Description |
| --- | --- |
| `corpusid` | The unique identifier of the paper. |
| `externalids` | The same paper in other repositories (e.g., DOI, ACL). |
| `title` | The title of the paper. |
| `authors` | The authors of the paper with their `authorid` and `name`. |
| `venue` | The venue of the paper. |
| `year` | The year of the paper publication. |
| `publicationdate` | A more precise publication date of the paper. |
| `abstract` | The abstract of the paper. |
| `outgoingcitations` | The number of references of the paper. |
| `ingoingcitations` | The number of citations of the paper. |
| `isopenaccess` | Whether the paper is open access. |
| `influentialcitationcount` | The number of influential citations of the paper according to SemanticScholar. |
| `s2fieldsofstudy` | The fields of study of the paper according to SemanticScholar. |
| `publicationtypes` | The publication types of the paper. |
| `journal` | The journal of the paper. |
| `updated` | The last time the paper was updated. |
| `s2url` | A url to the paper in SemanticScholar. |

### Authors

| Feature | Description |
| --- | --- |
| `authorid` | The unique identifier of the author. |
| `externalids` | The same author in other repositories (e.g., ACL, PubMed). This can include `ORCID` |
| `name` | The name of the author. |
| `affiliations` | The affiliations of the author. |
| `homepage` | The homepage of the author. |
| `papercount` | The number of papers the author has written. |
| `citationcount` | The number of citations the author has received. |
| `hindex` | The h-index of the author. |
| `updated` | The last time the author was updated. |
| `email` | The email of the author. |
| `s2url` | A url to the author in SemanticScholar. |

## 📖 Citation

If you use the dataset in any way, please cite:

```bib
@inproceedings{Wahle2022c,
  title        = {D3: A Massive Dataset of Scholarly Metadata for Analyzing the State of Computer Science Research},
  author       = {Wahle, Jan Philip and Ruas, Terry and Mohammad, Saif M. and Gipp, Bela},
  year         = {2022},
  month        = {July},
  booktitle    = {Proceedings of The 13th Language Resources and Evaluation Conference},
  publisher    = {European Language Resources Association},
  address      = {Marseille, France},
  doi          = {},
}
```

Also make sure to cite the following papers if you use SemanticScholar data:

```bib
@inproceedings{ammar-etal-2018-construction,
    title = "Construction of the Literature Graph in Semantic Scholar",
    author = "Ammar, Waleed  and
      Groeneveld, Dirk  and
      Bhagavatula, Chandra  and
      Beltagy, Iz",
    booktitle = "Proceedings of the 2018 Conference of the North {A}merican Chapter of the Association for Computational Linguistics: Human Language Technologies, Volume 3 (Industry Papers)",
    month = jun,
    year = "2018",
    address = "New Orleans - Louisiana",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/N18-3011",
    doi = "10.18653/v1/N18-3011",
    pages = "84--91",
}
```

```bib
@inproceedings{lo-wang-2020-s2orc,
    title = "{S}2{ORC}: The Semantic Scholar Open Research Corpus",
    author = "Lo, Kyle  and Wang, Lucy Lu  and Neumann, Mark  and Kinney, Rodney  and Weld, Daniel",
    booktitle = "Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics",
    month = jul,
    year = "2020",
    address = "Online",
    publisher = "Association for Computational Linguistics",
    url = "https://www.aclweb.org/anthology/2020.acl-main.447",
    doi = "10.18653/v1/2020.acl-main.447",
    pages = "4969--4983"
}
```

## 🧑‍⚖️ License

The DBLP Discovery Dataset is released under the CC BY-NC 4.0. By using this corpus, you are agreeing to its usage terms.


## 🙏 Acknowledgements
We adapted this readme from the awesome [ACL Anthology Corpus](https://github.com/shauryr/ACL-anthology-corpus).
We thank Semantic Scholar for the metadata they provided for this work.
