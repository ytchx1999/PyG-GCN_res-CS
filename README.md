# PyG-GCN_res-CS
This is an improvement of the [(GCN_res + 8 layers)](https://github.com/ytchx1999/ogbn_arxiv_GCN_res) model, using the C&amp;S method.

### ogbn-arxiv

+ Check out the model：[(GCN_res + 8 layers)](https://github.com/ytchx1999/ogbn_arxiv_GCN_res)

+ Check out the C&S method：[C&S](https://arxiv.org/abs/2010.13993)

#### Improvement Strategy：

+ add C&S method

#### Environmental Requirements

+ pytorch == 1.7.1
+ pytorch_geometric == 1.6.3
+ ogb == 1.2.4

#### Experiment Setup：

The model is 8 layers, 10 runs which conclude 500 epochs.

```bash
python gcn_res_cs.py
```

#### Detailed Hyperparameter:

```bash
num_layers = 8
hidden_dim = 128
dropout = 0.5
lr = 0.01
runs = 10
epochs = 500
alpha = 0.2
beta = 0.7
num_correction_layers = 50
correction_alpha = 0.8
num_smoothing_layers = 50
smoothing_alpha = 0.8
scale = 1.
A1 = 'DAD'
A2 = 'DAD'
```

#### Result:

```bash
All runs:
Highest Train: 95.40 ± 0.02
Highest Valid: 74.23 ± 0.14
  Final Train: 95.40 ± 0.02
   Final Test: 72.97 ± 0.22
```

| Model         | Test Accuracy   | Valid Accuracy  | Parameters | Hardware         |
| ------------- | --------------- | --------------- | ---------- | ---------------- |
| GCN_res + C&S | 0.7297 ± 0.0022 | 0.7423 ± 0.0014 | 155824     | Tesla T4（16GB） |

