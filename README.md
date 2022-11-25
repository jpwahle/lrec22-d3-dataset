# 📖 The DBLP Discovery Dataset (D3)

[![arXiv](https://img.shields.io/badge/arXiv-2204.13384-b31b1b.svg)](https://arxiv.org/abs/2204.13384)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.7069915.svg)](https://doi.org/10.5281/zenodo.7069915)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
[![HuggingFace Dataset](https://img.shields.io/badge/🤗-Datasets-ffce1c.svg)](https://huggingface.co/datasets/jpwahle/dblp-discovery-dataset)

This repository provides metadata to papers from [DBLP](dblp.org) (> 5.9m articles, > 3.8m authors as of September 2022) crawled with the [cs-insights-crawler](https://github.com/gipplab/cs-insights-crawler).

> As of version 2.1 of the dataset and version 1.3.0 of the crawler, the dataset adds the [Computer Science Ontology](https://github.com/jpwahle/lrec22-d3-dataset/issues/1) with information about sub-fields. Also as of version 2.1 of the dataset, we support 🤗 [Hugging Face Datasets](https://huggingface.co/datasets/jpwahle/dblp-discovery-dataset/).

> As of version 2.0 of the dataset and version 1.0.2 of the crawler, the dataset uses [SemanticScholar](https://semanticscholar.org) data. We will release a blog post soon about this update and how it affects porting from version 1.0.

The goal is to keep this corpus monthly updated and provide a comprehensive repository of the full DBLP collection.

This repository provides the following exports: 
1. 📖 All paper entries with metadata as jsonl: **size 2.7G** (gz) [download here](https://zenodo.org/record/6477785).
2. 🙋 All author entries with metadata as jsonl: **size 188M** (gz) [download here](https://zenodo.org/record/6477785).

```python
>>> from datasets import load_dataset
>>> load_dataset("jpwahle/dblp-discovery-dataset, "papers")['train'][0]
{
 'corpusid': 26,
 'externalids': ['ACL',
  'DBLP',
  'ArXiv',
  'MAG',
  'CorpusId',
  'PubMed',
  'DOI',
  'PubMedCentral'],
 'title': 'FPGA-based design and implementation of an approximate polynomial matrix EVD algorithm',
 'authors': {'authorId': [12653318, 144237481],
  'name': ['Server Kasap', 'Soydan Redif']},
 'venue': '2012 International Conference on Field-Programmable Technology',
 'year': 2012,
 'publicationdate': '2012-12-01',
 'abstract': 'In this paper, we introduce a field-programmable gate array (FPGA) hardware architecture for the realization of an algorithm for computing the eigenvalue decomposition (EVD) of para-Hermitian polynomial matrices. Specifically, we develop a parallelized version of the second-order sequential best rotation (SBR2) algorithm for polynomial matrix EVD (PEVD). The proposed algorithm is an extension of the parallel Jacobi method to para-Hermitian polynomial matrices, as such it is the first architecture devoted to PEVD. Hardware implementation of the algorithm is achieved via a highly pipelined, non-systolic FPGA architecture. The proposed architecture is scalable in terms of the size of the input para-Hermitian matrix. We demonstrate the decomposition accuracy of the architecture through FPGA-in-the-loop hardware co-simulations. Results confirm that the proposed solution gives low execution times while reducing the number of resources required from the FPGA.',
 'referencecount': 16,
 'citationcount': 1,
 'isopenaccess': False,
 'influentialcitationcount': 0,
 's2fieldsofstudy': {'category': ['Computer Science', 'Computer Science'],
  'source': ['s2-fos-model', 'external']},
 'publicationtypes': ['JournalArticle', 'Conference'],
 'journal': "{'name': '2012 International Conference on Field-Programmable Technology', 'volume': None, 'pages': '135-140'}",
 'updated': '2022-02-13T16:00:07.412Z',
 'url': 'https://www.semanticscholar.org/paper/7011b84b03f1d992962c4a6c87459f7742bc3165'
}
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
| `referencecount` | The number of references of the paper. |
| `citationcount` | The number of citations of the paper. |
| `isopenaccess` | Whether the paper is open access. |
| `influentialcitationcount` | The number of influential citations of the paper according to SemanticScholar. |
| `s2fieldsofstudy` | The fields of study of the paper according to SemanticScholar. |
| `publicationtypes` | The publication types of the paper. |
| `journal` | The journal of the paper. |
| `updated` | The last time the paper was updated. |
| `url` | A url to the paper in SemanticScholar. |

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
