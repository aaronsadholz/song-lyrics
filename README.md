# Song lyrics project

Exploratory Data Analysis and Visualization, Columbia University, Spring 2018.

## Project overview

WIP

## Folder structure

* `data/` - Data is dumped here, not included in the repository
* `process/` - Scripts for downloading and processing the data (Python 3)
    - `process/pkg/` - Small Python package with utility functions
    - `process/download/` - Getting the raw data
    - `process/clean/` - Cleaning the raw data
    - `process/transform/` - Code for generating various song vector representations
    - `process/cluster/` - Clustering songs
* `experiments/` - Notebooks/scripts that we used to explore the data
* `viz/` - Visualizations (R)

## Data

We are using the [Million Song Dataset](https://labrosa.ee.columbia.edu/millionsong/), specifically the [musiXmatch dataset](https://labrosa.ee.columbia.edu/millionsong/musixmatch) which contains lyics data for 237,662 tracks.

## Quickstart

TODO: environment setup

## 1. Get raw data

```shell
git clone https://github.com/edublancas/song-lyrics
cd song-lyrics

# this will create a new data/ folder in the current
# working directory raw data will be stored in data/raw
./process/download/get_data

```


## 2. Process data

```shell
# install the python package
pip install -e process/pkg

# parse txt files and convert them to json
mkdir data/clean
./process/clean/txt2json data/raw/mxm_dataset_train.txt \
    data/clean/mxm_dataset_train.json
./process/clean/txt2json data/raw/mxm_dataset_test.txt \
    data/clean/mxm_dataset_test.json

# join the two json files

# convert json data to bag of words representation
mkdir data/transform
./process/transform/bag_of_words data/clean/mxm_dataset_test.json \
    data/transform/mxm_dataset_test.feather
```
