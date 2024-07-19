# How to Build the Ultimate Hybrid Search with Qdrant

This repository contains the materials for the hands-on webinar "[How to Build the Ultimate Hybrid Search with 
Qdrant](https://www.youtube.com/watch?v=LAZOxqzceEU)". It is a step-by-step guide on how to utilize the new Query API, 
introduced in Qdrant 1.10, to build a search system that combines the different search to improve the search quality.

We will test various setups and measure the effectiveness of each of them. Building a proper search experience is a
complex task, and it's better to keep it data-driven, not just rely on the intuition.

## Prerequisites

Obviously a running Qdrant instance is the most important piece. You can run it either locally or simply register to
get a free tier on the [Qdrant Cloud](https://cloud.qdrant.io/). Eventually, you should have a URL pointing to your
instance, and an API key to authenticate your requests if you are using the cloud version.

Other than that, you need to have Python 3.10+ installed on your machine, and perfectly poetry to manage the 
dependencies. We will only use open source models which you can run even on a CPU. Installation of all the required
libraries is as simple as running the following command:

```shell
poetry install
```

## Dataset

BeIR is a heterogeneous benchmark containing diverse IR tasks. It consists of multiple datasets of different types
and sizes. We will use the `SciFact` dataset, which is designed for scientific fact-checking. The dataset contains 5.18k
documents and 1.11k queries. Hugging Face `datasets` library provides a simple interface to download everything we need.

## Getting Started

Building and evaluating a search system are two different tasks. We will start by indexing all the available documents
with three different methods, and then we'll play with combining them to build the best hybrid search possible. Thus, 
we will divide the process into two separate notebooks:

- `notebooks/01-qdrant-indexing.ipynb`: creating all the vectors and indexing them in Qdrant
- `notebooks/02-hybrid-search.ipynb`: combining the search results from different methods and evaluating them

Jupyter is installed as a dependency, and you can start the notebook server by running the following command:

```shell
jupyter notebook
```
