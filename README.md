# 📖 The DBLP Discovery Dataset

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.6477785.svg)](https://doi.org/10.5281/zenodo.6477785)
[![arXiv](https://img.shields.io/badge/arXiv-2204.13384-b31b1b.svg)](https://arxiv.org/abs/2204.13384)

This repository provides metadata to papers from [DBLP](dblp.org) (>6.7m articles as of September 2022).

The goal is to keep this corpus monthly updated and provide a comprehensive repository of the full DBLP collection.

This repository provides the following exports: 
1. 📖 All extracted metadata of [GROBID](https://grobid.readthedocs.io), parsed with Semantic Scholar's [doc2json](https://github.com/allenai/s2orc-doc2json) parser: **size 45G**  [download here](https://zenodo.org/record/6477785)
2. 🏷️  Raw grobid extraction results on all the DBLP pdfs including references : **size 3.6G** [download here](https://zenodo.org/record/6477785)
3. 💾  Dataframe with metadata and full text of the collection for analysis : **size 503M** [download here](https://zenodo.org/record/6477785)


```python
>>> import pandas as pd
>>> pd.read_parquet('d3-full.csv')

          dblp_key           title        abstract         authors   ...
0         P83-1025  Discourse P...  This paper ...  This paper ...   ...
1         P93-1015  Parsing Fre...  There is a ...  There is a ...   ...
2         P82-1017  REFLECTIONS...                  Our society...   ...
3         C86-1129  A Lexical F...  This paper ...  This paper ...   ...
..             ...             ...             ...             ...   ...
96  2021.tacl-1...  On the Rela...  We use larg...  We use larg...   ...
97  2022.nlp4co...  Understandi...  Exemplar-ba...  Exemplar-ba...   ...
98  2022.nlp4co...  Stylistic R...  Personality...  Personality...   ...
99  2022.nlp4co...  Toward Know...  Conversatio...  Conversatio...   ...
```



The code to crawl this dataset was migrated to the [CS-Insights Project](https://github.com/gipplab/cs-insights-main) and now lives [here](https://github.com/gipplab/cs-insights-crawler).

We are hoping that this corpus can be helpful for analysis relevant to the computer science community. 

**Please cite/star 🌟 this page if you use this corpus**


  ### Citation
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

## License

The DBLP Discovery Dataset is released under the CC BY-NC 4.0. By using this corpus, you are agreeing to its usage terms.
