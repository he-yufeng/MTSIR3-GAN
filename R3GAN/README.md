# R3GAN — MTSIR3-GAN core (thesis implementation)

The original thesis model: **R3GAN adapted from image generation to multivariate
time series imputation (MTSI)**. Time series are reshaped into 2D patches and
imputed with a modernized, ResNet-style GAN trained with a regularized
relativistic loss (RpGAN + R₁ + R₂).

## Layout

| Path | What it is |
|------|------------|
| `train.py` | Training entry point (presets per dataset) |
| `gen_timeseries.py` | Generation / imputation from a trained checkpoint |
| `calc_metrics.py` | MAE/MSE/RMSE evaluation |
| `process_air_quality.py`, `dataset_tool.py` | Data preparation for MTSI |
| `R3GAN/` | Generator/Discriminator, resamplers, fused ops, trainer |
| `training/` | Training loop, losses, augmentation, dataset wrappers |
| `dnnlib/`, `torch_utils/`, `legacy.py`, `metrics/` | StyleGAN3 infrastructure |

## Usage

```bash
# Train on AirQuality
python train.py --outdir=./training_runs --data=../datasets/AirQuality/pm25_missing.txt \
                --gpus=1 --batch=64 --gamma=0.5 --preset=AirQuality_MTSI
```

See the [root README](../README.md) for the full workflow and results.

## Provenance & license ⚠️

This directory is **derived from third-party code** and is **not** covered by the
repository's root MIT license:

- The training infrastructure (`dnnlib/`, `torch_utils/`, `legacy.py`,
  `metrics/`, much of `train.py`) originates from **NVIDIA StyleGAN3**
  (<https://github.com/NVlabs/stylegan3>) and carries NVIDIA copyright headers.
  It is distributed under the **NVIDIA Source Code License** (research /
  **non-commercial** use only).
- The modern GAN baseline (`R3GAN/`) follows **R3GAN** — Huang, Gokaslan,
  Kuleshov, Tompkin, *"The GAN is dead; long live the GAN! A Modern GAN
  Baseline,"* NeurIPS 2024 (<https://github.com/brownvc/R3GAN>).

Original contributions here are the **1D / time-series-imputation adaptation**
(patching, MTSI data tooling, presets, evaluation). Respect the upstream
NVIDIA license for any reuse.
