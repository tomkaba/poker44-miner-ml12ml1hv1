# Poker44-gen12ml1hv1

Minimal release repository for model gen12ml1hv1.

This repo is a standalone miner variant extracted from the main subnet codebase,
with only ml1h scoring logic enabled.

## Quick start

```bash
git clone https://github.com/tomkaba/poker44-miner-ml12ml1hv1.git
cd poker44-miner-ml12ml1hv1
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
pip install -e .
```

Model artifact is tracked directly in git (no Git LFS required for this repo).

```bash
# regular clone is enough; no extra artifact pull step is required
```

## Run Miner

```bash
python neurons/miner.py
```

or legacy wrapper:

```bash
./start_miner.sh HOTKEY_ID[,HOTKEY_ID2,...]
```

## Implementation

- Scorer: score_chunk_ml1h_with_route() in poker44/miner_heuristics.py
- Artifacts: model + scaler stored under weights/
- Entry point: neurons/miner.py

Manifest implementation SHA256 is computed from:

- neurons/miner.py
- poker44/miner_heuristics.py
- model artifact file under weights/
- scaler artifact file under weights/
