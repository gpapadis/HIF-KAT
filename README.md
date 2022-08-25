# HIF-KAT

Source code for ACL 2021 paper "[Interpretable and Low-Resource Entity Matching via Decoupling Feature Learning from Decision Making](https://aclanthology.org/2021.acl-long.215.pdf)".


## Environments

### External Resources

We provide our external resources, i.e., our **fasttext word embeddings** and our used **conda environment**.

```bash
wget https://dl.fbaipublicfiles.com/fasttext/vectors-wiki/wiki.en.zip
unzip wiki.en.zip
rm wiki.en.vec

wget https://zenodo.org/record/7020029/files/em2.tar.gz
tar -xf em2.tar.gz
```

### Embeddings

1. Download `fasttext.wiki.en.300d.bin` from the Tsinghua Cloud.
2. Create a new directory at `$HOME/.vector_cache/fasttext` (if not exist).
3. Place `fasttext.wiki.en.300d.bin` at `$HOME/.vector_cache/fasttext`
4. Check it by `ls -al ~/.vector_cache/fasttext/fasttext.wiki.en.300d.bin`, and you should get some output like this:

```
-rw-r--r-- 1 zijun zijun 8493673445 Jan 14 20:48 /home/zijun/.vector_cache/fasttext/fasttext.wiki.en.300d.bin
```

### Python Environments

We would recommend you to install Anaconda (or Miniconda) and create a new environment for our code by cloning from the Tsinghua Cloud.

1. Download our environment from the Tsinghua Cloud, and name it as `em2`
2. Create a new virtual environment: `conda create -n em --clone em2`.
3. Enter the new environment: `conda activate em`.


## About the Data

1. Go to the `dataset` directory: `cd dataset`
2. Run `1.bigtable-attrdrop-ind.py`, `2.mag-table.py`, `4.mag.py`, and `5.traditinal_feature.py` in sequence.

Note that we have already provided data for reproducing Table 3 and Table 4.
For reproducing Figure 3, you need to prepare the dataset by running our data preprocessing code with different `drop_rate` and `train_rate`.

### Structured Data

music: I-A_1

citation: D-S_1

citeacm: D-A_1

### Dirty Data

dmusic: I-A_2

dcitation: D-S_2

dciteacm: D-A_2

### Real Data

Due to commercial issues, we are not able to publish the Real dataset.

## Reproducing Table 3

```
cd 1-HRF-dt
bash run.sh

cd 1-HRF-gini
bash run.sh

cd 1-HRF-xgb
bash run.sh
```

The final results are recorded in the `logs` directory.

## Reproducing Table 4

```
cd 1-HRF-dt
bash run_full.sh

cd 1-HRF-gini
bash run_full.sh

cd 1-HRF-xgb
bash run_full.sh
```

The final results are recorded in the `logs` directory.

## Cite

If you use the code, please cite this paper:

Zijun Yao, Chengjiang Li, Tiansi Dong, Xin Lv, Jifan Yu, Lei Hou, Juanzi Li, Yichi Zhang, Zelin Dai. Interpretable and Low-Resource Entity Matching via Decoupling Feature Learning from Decision Making. *The Joint Conference of the 59th Annual Meeting of the Association for Computational Linguistics and the 11th International Joint Conference on Natural Language Processing (ACL-IJCNLP 2021)*.

via

```
@inproceedings{yao-etal-2021-interpretable,
    title = "Interpretable and Low-Resource Entity Matching via Decoupling Feature Learning from Decision Making",
    author = "Yao, Zijun  and Li, Chengjiang  and Dong, Tiansi  and Lv, Xin  and Yu, Jifan  and Hou, Lei  and Li, Juanzi  and Zhang, Yichi  and Dai, Zelin",
    booktitle = "ACL'21",
    year = "2021",
    url = "https://aclanthology.org/2021.acl-long.215",
}
```
