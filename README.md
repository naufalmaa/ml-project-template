# ml-project-template

Copier template behind every repo in Naufal MA's traditional-ML portfolio.
It encodes one lifecycle (8 stages + 2 habits) so every project tells its story the same way.

## Use

```bash
# from ml-things/ (inside WSL2)
uvx copier copy --trust ml-project-template oil-well-event-early-warning
cd oil-well-event-early-warning
make setup        # uv sync + pre-commit install
make help         # list every target
```

Pull later template improvements into an existing project:

```bash
cd <project> && uvx copier update --trust
```

## What you get

| Path | Lifecycle stage |
|---|---|
| `docs/01-problem-framing.md` | 1 · Problem framing & success metrics |
| `docs/data-card.md`, `src/<pkg>/data/download.py` | 2 · Data acquisition (checksum-verified) |
| `notebooks/01-eda.ipynb`, `src/<pkg>/data/schema.py` | 3 · EDA & data-quality contract |
| `docs/02-split-and-leakage.md`, `tests/test_leakage.py` | 4 · Split strategy & leakage audit |
| `src/<pkg>/models/baseline.py` | 5 · Baseline |
| `src/<pkg>/features/`, `src/<pkg>/models/train.py` | 6 · Features & modeling |
| `src/<pkg>/evaluation/`, `notebooks/03-error-analysis.ipynb` | 7 · Evaluation, error analysis, tuning |
| `docs/model-card.md`, `docs/case-study.md` | 8a · Communication |
| `docker/`, `docs/runbook.md` (added when needed) | 8b · Deployment & monitoring |
| `CLAUDE.md`, `.claude/skills/` | Which Claude skills to use at each stage |
| `scripts/publish_assets.py` | Copy figures + case study to the portfolio website |

Habits across all stages: **reproducibility** (seeded, config-driven, `make` targets, MLflow) and **iteration** (record each loop in `docs/decisions/`).
