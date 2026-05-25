# Local Setup

This repo has broad dependency bounds, so use the checked-in constraints file
instead of installing `requirements.txt` directly.

On Apple Silicon:

```bash
brew install python@3.11
/opt/homebrew/bin/python3.11 -m venv .venv
.venv/bin/python -m pip install --upgrade pip setuptools wheel
.venv/bin/python -m pip install -c constraints-macos-arm64-py311.txt -r requirements.txt
.venv/bin/python -m pip install -e .
```

Use the environment with:

```bash
source .venv/bin/activate
```

This repository's inference/evaluation path is CUDA-oriented and `scripts/run.sh`
expects `nvidia-smi`. The environment above is suitable for local development,
imports, evaluation utilities, and editing on macOS, but full model evaluation
requires an NVIDIA CUDA machine.
