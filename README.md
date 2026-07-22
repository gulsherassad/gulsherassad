# Gulsher Assad

**CS student at UBC Okanagan** (BSc, expected Apr 2027) · Kelowna, BC

I build Python backends with a model doing something non-trivial behind them —
statistical forecasting, constrained optimization — plus the API and frontend
work that makes them usable by someone other than me.

The part I care about most is evaluation. It's easy to build a model that looks
good on the data it was trained on, and easy to write code that passes the tests
you thought to write. Most of my time goes into the other half: walk-forward
backtests instead of in-sample accuracy, comparisons against a real baseline
rather than a flattering one, and coverage over the paths that fail quietly.

---

## Projects

### ⚽ [epl-predictor](https://github.com/gulsherassad/epl-predictor) — [live demo](https://epl-predictor-xmqs.onrender.com)

Premier League match forecaster combining an Elo rating system with a Poisson
goals model, blended and served through a FastAPI backend.

| | |
|---|---|
| **1X2 accuracy** | 54.9% across a 1,420-match walk-forward backtest |
| **Baseline** | ~10 points above always-picking-home; roughly level with betting-market accuracy |
| **Outputs** | Win/draw/loss probabilities, per-fixture expected goals, full scoreline distributions |

Elo ratings update sequentially through five seasons of results while a Poisson
model estimates attack and defence strength per team; the two are blended and
renormalized. Backtesting is strictly walk-forward — each prediction uses only
matches played before it — so the reported accuracy isn't inflated by leakage.
The README publishes the full model comparison, Elo-only and Poisson-only
included, along with where the model loses to the market.

`Python` · `FastAPI` · `scikit-learn` · `pandas` · `pytest` · `Render`

### 🥗 [macro_optimizer](https://github.com/gulsherassad/macro_optimizer)

Meal planning as a constrained optimization problem: minimize calories subject
to a protein floor, a calorie ceiling, and optional carb and fat ranges.

- Solver formulated with **PuLP** and kept entirely separate from the API layer,
  so optimization logic can be tested without touching HTTP
- **Infeasible targets are a real outcome, not an error** — the API returns a
  structured explanation of which constraints conflict instead of failing
- Extends to full-day planning by solving each meal independently, so one
  impossible meal doesn't sink the whole day
- **75 tests** across solver correctness, API integration, and UI behaviour, at
  98% statement coverage on backend source modules
- Schema changes managed through Alembic migrations; saved plans persist as
  solved snapshots so past results stay accurate when food data changes

`Python` · `FastAPI` · `PuLP` · `PostgreSQL` · `Alembic` · `React` · `Docker` · `pytest` · `Vitest`

### 🎬 [movie-review-platform](https://github.com/gulsherassad/movie-review-platform)

Full-stack movie review platform built by a team of four for COSC 310
(Software Engineering) at UBCO.

I owned the review and comment modules end to end — creation, editing, deletion,
and threaded comments — building the REST endpoints in FastAPI with Pydantic
models enforcing validation at the boundary. The service runs as two
containers orchestrated with Docker Compose.

`Python` · `FastAPI` · `Next.js` · `TypeScript` · `Docker`

---

## Working with

| | |
|---|---|
| **Languages** | Python, JavaScript, TypeScript, Java, SQL |
| **Backend** | FastAPI, Pydantic, PostgreSQL, Alembic, Uvicorn |
| **Data & ML** | pandas, NumPy, scikit-learn, PuLP, PyTorch |
| **Frontend** | React, Next.js |
| **Tooling** | Git, Docker, pytest, Vitest, Render |

---

## Background

Before Kelowna I lived in Zambia and Côte d'Ivoire, finishing the IB Diploma at
the International Community School of Abidjan. Currently working through the IBM
AI Engineering Professional Certificate, mostly for the PyTorch and Keras
material.

Interested in roles where the work involves modelling something real and being
honest about how well it worked.

## Reach me

[Email](mailto:gulsherassad1@gmail.com) ·
[LinkedIn](https://www.linkedin.com/in/gulshera/) ·
[GitHub](https://github.com/gulsherassad)
