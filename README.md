# Collaborative Filtering Based Paper Recommendations

# Setup

Install required packages:
```
pip3 install numpy, scipy, scikit-learn
pip3 install notebook
```

To run the notebooks:
```
jupyter notebook
```

In order to run the notebooks out-of-order (e.g. run predicition-only or avoid generating the utility matrix), 
you may download the intermediate files from [google drive](https://drive.google.com/drive/folders/1g_GRlf5AKt2HpX1nnbKh7XctuFST7aCl?usp=sharing).
The folder contains the following files:

```shell
├── dblp.v12.json # original DBLP Citation Network Dataset
├── eval_data.pkl # evaluation dataset
├── name2id.pkl # dict mapping user name to an user id in the DBLP dataset to (e.g. "Yann LeCun" -> 2053214915)
├── id2name.pkl # reverse of name2id (e.g. 2053214915 -> "Yann LeCun")
├── title2id.pkl # dict mapping paper title to a paper id in the DBLP dataset (e.g. "Deep Residual Learning for Image Recognition" -> 2949650786)
├── id2title.pkl # reverse of title2id (e.g. 2949650786 ->  "Deep Residual Learning for Image Recognition")
├── items_encoder.pkl # sklearn encoder transforming paper id to a column in utility matrix (and reverse)
├── users_encoder.pkl # sklearn encoder transforming user id to a row in utility matrix (and reverse)
└── utility_matrix.pkl # ready utility matrix in COO format parsed from the DBLP dataset
```

# Running the code

1. To jump straight to end-to-end recommendations _(user name in, recommneded titles out)_ see: `07_end_to_end_recommendations.ipynb`
2. To read the data from the `DBLP Citation Network Dataset`, see `02_dblp.ipynb`. The dataset can be downloaded from [here](https://originalstatic.aminer.cn/misc/dblp.v12.7z).
3. The code for generating the sparse utility matrix from the is in `03_sparse_utility_matrix_generation.ipynb`
4. The code for generating id<->title and id<->username lookups is available in `06_id_lookup.ipynb`
5. The test set is generated in `09_test_set_generation.ipynb` and the evaluation for user-based CF and item-based CF is in `10_evaluation_user_based.ipynb` and `11_evaluation_item_based.ipynb` respectively.