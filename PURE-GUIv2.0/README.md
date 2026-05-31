# PURE-GUIv2.0 — interactive imputation GUI

A Dash (Plotly) web interface for uploading time series, visualizing missing
patterns, running imputation (MTSIR3-GAN / SSGAN / TimesNet), and comparing
results.

## Run

```bash
cd PURE-GUIv2.0
python app_dad.py
# then open http://127.0.0.1:8050
```

## Layout

| Path | What it is |
|------|------------|
| `app_dad.py` | Dash app entry point |
| `pages/` | Data analysis, imputation, and visualization pages |
| `model_files/` | Pretrained weights (**not bundled** — see note) |
| `model_results/` | Cached predictions (**not bundled**) |
| `uploaded_files/` | User uploads / demo CSVs (**not bundled**) |

## Note on assets ⚠️

`model_files/`, `model_results/`, and `uploaded_files/` are **git-ignored** and
**not shipped** in the repository (they are large binaries). To use the GUI:

- Train a model (see [`R3GAN/`](../R3GAN/) or [`FMGAN/`](../FMGAN/)) and place the
  checkpoint under `model_files/`, **or** supply your own.
- Upload your own CSVs through the interface at runtime.

The imputation baselines invoked here (SSGAN, TimesNet) retain their upstream
licenses — see their folder READMEs.
