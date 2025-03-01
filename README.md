# Differentially Private Set Union for Vocabulary Release
This repository contains the code and dataset for the following paper:  
> **Differentially Private Set Union with Applications to Vocabulary
Generation**<br>
> Sivakanth Gopi, Pankaj Gulhane, Janardhan Kulkarni, Judy Hanwen Shen,
Milad Shokouhi, and Sergey Yekhanin<br>
> https://arxiv.org/abs/2002.09745

Published as 

> Sivakanth Gopi, Pankaj Gulhane, Janardhan Kulkarni, Judy Hanwen Shen, Milad Shokouhi, and Sergey Yekhanin. 2021. "Differentially Private Set Union." *Journal of Privacy and Confidentiality* Vol 11(3). https://doi.org/10.29012/jpc.780

Archived as 

> Sivakanth Gopi, Pankaj Gulhane, Janardhan Kulkarni, Judy Hanwen Shen, Milad Shokouhi, and Sergey Yekhanin. 2021. "Code for: Differentially Private Set Union." Zenodo. https://doi.org/10.5281/zenodo.5789857  [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5789857.svg)](https://doi.org/10.5281/zenodo.5789857)





> **Abstract:** *We study the basic operation of set union in the global model of differential privacy. In this problem, we are given a universe U of items, possibly of infinite size, and a database D of users. Each user i contributes a subset W_i of items. We want an (epsilon, delta)-differentially private Algorithm which outputs a subset S (a union of subsets W_i) such that the size of S is as large as possible. The problem arises in countless real world applications, and is particularly ubiquitous in natural language processing (NLP) applications. For example, discovering words, sentences, n-grams etc., from private text data belonging to users is an instance of the set union problem. In this paper we design new algorithms for this problem that significantly outperform the best known algorithms.*

## Prerequisites

```
python >= 3.6
numpy >= 1.14.3
pandas >= 0.22.0 
scipy >= 1.0.1
tqdm >= 4.23.4
```

## Dataset
For your own input file, the file must contain an "author" and a "clean_text" column where the clean text has been 
preprocessed and tokenized. For an example, sample_data.csv. Please note sample_data.csv contains random text from wikitext-2 and has too few entries to release ngrams. Please use solely as a reference for data formatting.  

## Example: Generating a Histogram

```[
python gen_histogram.py --save_histogram --dataset sample_data.csv
```
This generates and saves a histogram with the Policy Gaussian algorithm and outputs the number of unigrams released. 

```
python gen_histogram.py --alg policy --noise laplace --ngram 2 --trials 3 --dataset sample_data.csv
```
To change which algorithm is used specify the --alg and --noise parameter. 
To change the n of ngrams in the histogram use: --ngrams . For multiple shuffles 
of the dataset, use the --trials parameter. 

## Acknowledgments
This work was done during an AI Residency at Microsoft Research.  

