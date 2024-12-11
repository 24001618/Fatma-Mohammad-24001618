# Code For PaSeR
This repo aims to reproduce the results of the [Sentence Representation Learning with Generative Objective rather than Contrastive Objective](https://arxiv.org/pdf/2210.08474.pdf) paper. In this repo, I will provide the code used throughout my study.


## Dependency
pytorch=1.10.1, python=3.7.11

for other dependencies:

`pip install -r requirements.txt`

## Data
They provided both the raw data and the augmented data we used in our paper in `data/raw.csv` and `data/augmented.csv`. This data file is processed using the code from [EDA](https://github.com/jasonwei20/eda_nlp/). Then they preprocess `data/raw.csv` using synonym replacement with a ratio of 0.5.


## Training
`bash scripts/run_unsup_example.sh`.

## Evaluation
`bash eval.sh`

## Performance
Note from the repo of the research paper, that proves the possible instability of results: "The performance in the unsupervised setting is a little unstable. Different machines may lead to different results. In our experiments we use 24G RTX and 80G A100. Both machines lead to an average performance above 76.15."

| Device | STS12 | STS13 | STS14 | STS15 | STS16 | STSBenchmark | SICKRelatedness |  Avg. |
| :------: | :------: | :------: | :------: | :------: | :------: | :------:  | :------: | :------: |
| A100 | 70.75 | 83.53 | 72.78 | 83.69 | 77.64 |    79.27     |      65.37      | 76.15 |
| RTX | 70.21 | 83.88 | 73.06 | 83.87 | 77.60 | 79.19 | 65.31 | 76.16 |
