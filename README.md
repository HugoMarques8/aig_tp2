# TP2 Student Starter Pack

Files:

- `TP2_StarterPack_Students.ipynb`: Colab/VS Code starter notebook.
- `tp2-chosen/`: copy of the TP2 target images.
- `tp2-chosen.zip`: optional zip with the same target images.
- `students/outputs/`: local output folder placeholder.

The notebook reads targets from `tp2-chosen/` and saves generated outputs to `students/outputs/`.

## Requirements

- A Hugging Face account / access token is needed to download model weights on first run: the LCM generator (`SimianLuo/LCM_Dreamshaper_v7`) and the CLIP-Interrogator models it uses for seed prompts (BLIP + `ViT-L-14`). Log in with `huggingface-cli login` (or set `HF_TOKEN`).
- Ollama (with an account) is required for the prompt-refinement loop. Run `ollama serve` and pull the models: `ollama pull llama3.1:8b` (text) and `ollama pull llava` (vision).
- A CUDA GPU is recommended. Install the PyTorch build that matches your GPU's CUDA version (see "Local install" below) — using the wrong CUDA version will fall back to CPU or fail to load.

The LCM settings match the TP2 target generation setup:

- model: `SimianLuo/LCM_Dreamshaper_v7`
- seed: parsed from target filename
- inference steps: `8`
- guidance scale: `8.0`
- `lcm_origin_steps`: `50`
- resolution: `768x768`

If Colab raises an error such as:

```text
cannot import name '_Ink' from 'PIL._typing'
```

restart the runtime/kernel and rerun the notebook from the first cell. The install cell pins `Pillow<12` to avoid that Diffusers/Pillow compatibility issue.

The install cell also pins `pandas<3` to avoid dependency conflicts with packages commonly preinstalled in Colab, such as Gradio.

## Local install (uv)

This repo supports multiple CUDA-backed PyTorch installs via optional extras:

```bash
# CUDA 12.6
uv sync --extra cuda126

# CUDA 12.8
uv sync --extra cuda128
```
