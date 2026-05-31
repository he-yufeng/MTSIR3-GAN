# TimesNet — baseline (vendored from Time-Series-Library)

TimesNet imputation baseline used for comparison against MTSIR3-GAN. The code in
this directory is a **subset of THUML's Time-Series-Library** (the `models/`
folder ships ~30 architectures from that library, of which TimesNet is used
here).

## Layout

| Path | What it is |
|------|------------|
| `run.py` | Experiment entry point (`--task_name imputation`) |
| `models/` | Model zoo from Time-Series-Library (TimesNet, Autoformer, …) |
| `data_provider/` | Dataset loaders |
| `exp/` | Experiment runners |
| `layers/`, `utils/` | Building blocks and helpers |

## Usage

```bash
python run.py --task_name imputation --data PSM --root_path ./datasets/PSM/ \
              --data_path train.csv --model_id PSM_mask_0.25 --model TimesNet \
              --mask_rate 0.25 --enc_in 25 --dec_in 25 --c_out 25 \
              --batch_size 16 --learning_rate 0.001 --train_epochs 10
```

## Provenance & license ⚠️

Vendored from **THUML Time-Series-Library**
(<https://github.com/thuml/Time-Series-Library>), released under the **MIT
License**. The TimesNet method is:

> Wu, Hu, Liu, Zhou, Wang, Long. *"TimesNet: Temporal 2D-Variation Modeling for
> General Time Series Analysis,"* ICLR 2023.

This directory retains its upstream MIT license and authorship; it is included
here unmodified (or lightly adapted) only as a baseline. Cite the paper and the
library if you reuse it.
