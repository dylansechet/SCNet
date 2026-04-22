# SCNet

This repository is a fork of the official implementation of [SCNet: Sparse Compression Network for Music Source Separation](https://arxiv.org/abs/2401.13276).

It moves dependency management to `uv` and fixes some instability issues during training.

---

## Installing

First, you need to install the requirements.

```bash
cd SCNet-main
uv sync
```

We use the accelerate package from Hugging Face for multi-gpu training.

```bash
uv run accelerate config
```

You need to modify the dataset path in the /conf/config.yaml. The dataset folder should contain the train and valid parts.

```bash
data:
  wav: /path/to/dataset
```

---

## Training

The training command is as follows. If you do not specify a path, the default path will be used.

```bash
uv run accelerate launch -m scnet.train --config_path path/to/config.yaml --save_path path/to/save/checkpoint/
```

