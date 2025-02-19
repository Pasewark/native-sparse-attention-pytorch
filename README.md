<img src="./fig2.png" width="450px"></img>

## Native Sparse Attention (wip)

Implementation of the sparse attention pattern proposed by the Deepseek team in their [Native Sparse Attention](https://arxiv.org/abs/2502.11089) paper

## Install

```bash
$ pip install native-sparse-attention-pytorch
```

## Usage

```python
import torch
from native_sparse_attention_pytorch import SparseAttention

attn = SparseAttention(
    dim = 512,
    dim_head = 64,
    heads = 8,
    sliding_window_size = 2,
    compress_block_size = 4,
    selection_block_size = 4,
    num_selected_blocks = 2
)

tokens = torch.randn(2, 31, 512)

attended = attn(tokens)

assert tokens.shape == attended.shape
```

## Example

Enwik8 language modeling

```bash
$ pip install .[examples]
```

Then

```bash
$ python train.py
```

## Citations

```bibtex
@inproceedings{Yuan2025NativeSA,
    title   = {Native Sparse Attention: Hardware-Aligned and Natively Trainable Sparse Attention},
    author  = {Jingyang Yuan and Huazuo Gao and Damai Dai and Junyu Luo and Liang Zhao and Zhengyan Zhang and Zhenda Xie and Y. X. Wei and Lean Wang and Zhiping Xiao and Yuqing Wang and Chong Ruan and Ming Zhang and Wenfeng Liang and Wangding Zeng},
    year    = {2025},
    url     = {https://api.semanticscholar.org/CorpusID:276408911}
}
```
