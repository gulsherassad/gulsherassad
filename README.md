# Gulsher Assad

CS student at UBC Okanagan (BSc, expected Apr 2027), based in Kelowna, BC.

I build Python backends with a model doing something non-trivial behind them —
statistical forecasting and constrained optimization — along with the API and
frontend work that makes them usable by someone other than me. I care about
evaluating things honestly: walk-forward backtests instead of in-sample
accuracy, benchmarks against a real baseline, and tests that cover the parts
that would fail silently.

---

## Projects

### [epl-predictor](https://github.com/gulsherassad/epl-predictor) · [live](https://epl-predictor-xmqs.onrender.com)

Premier League match forecaster combining an Elo rating system with a Poisson
goals model, blended and served through FastAPI.

- 54.9% 1X2 accuracy across a 1,420-match walk-forward backtest, roughly level
  with betting-market accuracy and ~10 points above an always-pick-home baseline
- Per-fixture expected goals and full scoreline distributions, not just win
  probabilities
- Backtest methodology and per-model comparison published in the README, misses
  included

`Python` · `FastAPI` · `scikit-learn` · `pandas` · `Render`

### [macro_optimizer](https://github.com/gulsherassad/macro_optimizer)

Meal planning as a constrained optimization problem: minimize calories subject
to a protein floor, calorie ceiling, and optional carb/fat ranges, solved with
PuLP.

- Solver kept fully separate from the API layer so optimization logic is
  testable on its own
- Infeasible macro targets return structured explanations rather than errors,
  and the solver extends to full-day planning by solving each meal independently
- 75 tests across solver correctness, API integration, and UI behaviour, at 98%
  statement coverage on the backend

`Python` · `FastAPI` · `PuLP` · `PostgreSQL` · `React` · `Docker` · `Alembic`

### [ByteMe-Project](https://github.com/gulsherassad/ByteMe-Project)

Movie review platform built by a team of four for a software engineering course.
I owned the review and comment modules end to end — create, edit, delete, and
threaded comments.

`Python` · `FastAPI` · `Next.js` · `TypeScript` · `Docker`

---

## Working with

**Languages** Python, JavaScript, TypeScript, Java, SQL
**Backend** FastAPI, Pydantic, PostgreSQL, Alembic
**Data & ML** pandas, NumPy, scikit-learn, PuLP, PyTorch
**Frontend** React, Next.js
**Tooling** Git, Docker, pytest, Vitest

---

## Reach me

[Email](mailto:gulsherassad1@gmail.com) ·
[LinkedIn](https://linkedin.com/in/gulsherassad)
