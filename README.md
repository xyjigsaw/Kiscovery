# Kiscovery
Exploring and Verbalizing Academic Ideas by Concept Co-occurrence

This is the official repository for the paper "Exploring and Verbalizing Academic Ideas by Concept Co-occurrence" by Yi Xu, Shuqian Sheng, Bo Xue, Luoyi Fu, Xinbing Wang, and Chenghu Zhou. The paper proposes a framework based on concept co-occurrence for academic idea inspiration, which has been integrated into a research assistant system DeepReport. The system can assist researchers in expediting the process of discovering new ideas.

DeepReport can be accessed at [It is expected to be released in mid-2023](https://github.com/xyjigsaw/Kiscovery).

## Statistics

The evolving concept co-occurrence graph and co-occurrence citation quintuple datasets used in this study are available for download in [Huggingface](https://huggingface.co/Reacubeth).

### Evolving Concept Co-occurrence Graph

To train our model for temporal link prediction, we first collect 240 essential and common queries from 19 disciplines and one special topic (COVID-19). Then, we enter these queries into the paper database to fetch the most relevant papers between 2000 and 2021 with Elasticsearch, a modern text retrieval engine that stores and retrieves papers. Afterward, we use information extraction tools including [AutoPhrase](https://github.com/shangjingbo1226/AutoPhrase) to identify concepts. Only high-quality concepts that appear in our database will be preserved. Finally, we construct 240 evolving concept co-occurrence graphs, each containing 22 snapshots according to the co-occurrence relationship. The statistics of the concept co-occurrence graphs are provided in Appendix I.

[Download from Huggingface](https://huggingface.co/datasets/Reacubeth/ConceptGraph)

Download with git, and you should install git-lfs first

```bash
sudo apt-get install git-lfs
# OR
brew install git-lfs

git lfs install
git clone https://huggingface.co/datasets/Reacubeth/ConceptGraph
```

### Co-occurrence Citation Quintuple

We construct and release a dataset of co-occurrence citation quintuples, which is used to train text generation model for idea verbalization. The process of identifying and processing concepts is similar to constructing the concept co-occurrence graph. Heuristic rules are adopted to filter redundant and noisy sentences, further improving the quality of the quintuples used for idea generation. More details of co-occurrence citation quintuples can be found in Appendix B, C, and J.

<img src="https://github.com/xyjigsaw/Kiscovery/raw/master/Quintuple.png" alt="Co-occurrence Citation Quintuple" width="500" align="bottom" />


In mid-2023, our DeepReport system underwent a major update, encompassing both data and model improvements. On the data front, we introduced a new version of the quintuple data (V202306), resulting in enhanced quality and a larger-scale dataset. The statistical summary of the new quintuple data (V202306) is presented as follows:

| Discipline            | Quintuple | Concept | Concept Pair | Total $p$ | Total $p_1$ \& $p_2$ |
| --------------------- | --------- | ------- | ------------ | --------- | -------------------- |
| Art                   | 7,510     | 2,671   | 5,845        | 2,770     | 7,060                |
| History               | 5,287     | 2,198   | 4,654        | 2,348     | 5,764                |
| Philosophy            | 45,752    | 4,773   | 25,935       | 16,896    | 29,942               |
| Sociology             | 16,017    | 4,054   | 12,796       | 7,066     | 16,416               |
| Political Science     | 67,975    | 6,105   | 42,411       | 26,198    | 53,933               |
| Business              | 205,297   | 9,608   | 99,329       | 62,332    | 112,736              |
| Geography             | 191,958   | 12,029  | 118,563      | 42,317    | 112,909              |
| Engineering           | 506,635   | 16,992  | 249,935      | 137,164   | 273,894              |
| Geology               | 365,183   | 13,795  | 190,002      | 98,991    | 222,358              |
| Medicine              | 168,697   | 13,014  | 114,104      | 42,535    | 138,973              |
| Economics             | 227,530   | 9,461   | 113,527      | 68,607    | 131,387              |
| Physics               | 267,532   | 10,831  | 133,079      | 84,824    | 176,741              |
| Biology               | 224,722   | 15,119  | 145,088      | 59,210    | 189,281              |
| Mathematics           | 312,670   | 17,751  | 190,734      | 95,951    | 218,697              |
| Psychology            | 476,342   | 9,512   | 194,038      | 115,725   | 212,180              |
| Computer Science      | 531,654   | 16,591  | 244,567      | 151,809   | 238,091              |
| Environmental Science | 583,466   | 11,002  | 226,671      | 94,474    | 201,330              |
| Materials Science     | 573,032   | 17,098  | 249,251      | 145,068   | 313,657              |
| Chemistry             | 565,307   | 13,858  | 231,062      | 108,637   | 286,593              |
| **Total**             | 5,342,566 | 206,462 | 2,591,591    | 1,362,922 | 2,941,942            |


[Download from Huggingface](https://huggingface.co/datasets/Reacubeth/Quintuple)

Download with git
```bash
sudo apt-get install git-lfs
# OR
brew install git-lfs

git lfs install
git clone https://huggingface.co/datasets/Reacubeth/Co-occurrenceCitationQuintuple
```

## Ethics Statement
The datasets used in our research are collected through open-source approaches. The whole process is conducted legally, following ethical requirements. As for the Turing Test in our study, all participants are well informed about the purpose of experiments and the usage of test data, and we would not leak out or invade their privacy.

We see opportunities for researchers to apply the system to idea discovery, especially for interdisciplinary jobs. We encourage users to explore different combinations of subjects with the help of our system, making the most of its knowledge storage and thus maximizing the exploration ability of the system.

The main focus of the system is to provide a possible direction for future research, but the effect of human researchers will never be neglected. 

The massive data from various disciplines behind the system makes it capable of viewing the knowledge of an area in a multi-dimensional perspective and thus helps promote the development of novel interdisciplinary. However, considering the risks of misinformation generated by NLP tools, the verbalization only contains possible insights into new ideas. Researchers must thoroughly consider whether an idea is feasible or leads to adverse societal effects.

## Acknowledgements
We would like to express our deepest gratitude to the scientists involved in the Deep-time Digital Earth program, whose contributions have been incredibly valuable. Additionally, we extend our thanks to Zhongmou He, Jia Guo, Zijun Di, Shengling Zhu, Yanpeng Li, Qi Li, Jiaxin Ding and Tao Shi from the IIOT Research Center at Shanghai Jiao Tong University for their unwavering support during the development of our system. This work was supported by NSF China (No.42050105, 62020106005, 62061146002, 61960206002), Shanghai Pilot Program for Basic Research - Shanghai Jiao Tong University.


## Citation

If you use our work in your research or publication, please cite us as follows:

```
@inproceedings{xu2023exploring,
  title={Exploring and Verbalizing Academic Ideas by Concept Co-occurrence},
  author={Xu, Yi and Sheng, Shuqian and Xue, Bo and Fu, Luoyi and Wang, Xinbing and Zhou, Chenghu},
  booktitle={Proceedings of the 61st Annual Meeting of the Association for Computational Linguistics (ACL)},
  year={2023}
}
```

Please let us know if you have any questions or feedback. Thank you for your interest in our work!
