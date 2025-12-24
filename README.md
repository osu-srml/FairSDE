# FairSDE: Achieving Fairness Without Harm via Selective Demographic Experts

This repo contains a PyTorch implementation of FairSDE for our paper [Achieving Fairness Without Harm via Selective Demographic Experts](https://arxiv.org/abs/2511.06293).

## Project Structure

```
FairSDE/
├── train.py          # Main training script
├── model.py          # Model architectures 
├── dataset.py        # Dataset loaders for all supported datasets
├── util.py           # Utilities (metrics, optimization, logging)
├── data/             # Data, split, and preprocessing
├── LICENSE
└── README.md
```

## Datasets

We don't provide datasets download here since some of them are licensed.

| Dataset | Task | Sensitive Attributes |
|---------|------|---------------------|
| MIMIC-CXR | Chest X-ray diagnosis | Race, Gender |
| HAM10000 | Skin lesion classification | Gender, Age |
| Harvard-GF | Glaucoma detection | Race, Gender |
| CelebA | Face attributes (”straight hair” and ”smiling”) | Gender |
| UTKFace | Ethnicity/Gender prediction | Gender, Ethnicity |

## Start

### 1. Prepare Data

Download datasets from their original websites and follow the comments in ```FairSDE/dataset.py```

### 2. Training

Example:

```bash
python train.py \
    --dataset ham \  # Dataset name (ham, mimiccxr, celeba, utk, eye)
    --data_path ./data \   #Path to data directory
    --lr 0.05 \  # Learning rate, tune for each dataset and method
    --epochs 60 \ 
    --bs 256 \
    --lambda1 0.1 \  # L_disc
    --lambda2 1 \  # L_virt
    --lambda3 1 \  # L_div
    --seed 7 \
    --sa race
```
## Citing

```bibtex
@inproceedings{tan2025achieving,
  title={Achieving Fairness Without Harm via Selective Demographic Experts},
  author={Tan, Xuwei and Wang, Yuanlong and Pham, Thai-Hoang and Zhang, Ping and Zhang, Xueru},
  booktitle={Proceedings of the AAAI Conference on Artificial Intelligence},
  year={2026}
}
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

If you have any questions, you can contact me via email at tanxuwei99@gmail.com. You can also open an issue here, but please note that this repo is managed by a public account, so I might not see it immediately.
