# SSGAN — baseline

SSGAN (Semi-Supervised GAN) imputation baseline used for comparison against
MTSIR3-GAN.

## Layout

| Path | What it is |
|------|------------|
| `main.py` | Training / evaluation entry point |
| `data_loader.py` | Data loading and masking |
| `preprocess.py` | Dataset preprocessing |
| `models/` | Generator / discriminator definitions |
| `utils.py` | Helpers |

## Usage

```bash
python main.py --epochs=50 --batch_size=64 --model=Based_on_BRITS
```

## Provenance & license ⚠️

This is a **baseline implementation** of the method from:

> Miao, Wu, Wang, Gao, Mao, Yin. *"Generative Semi-supervised Learning for
> Multivariate Time Series Imputation,"* AAAI 2021.

It is included here only to reproduce a comparison baseline. Credit for the
method belongs to the original authors; this directory is **not** part of the
original work covered by the repository's root MIT license. If you reuse it,
cite the paper above.
