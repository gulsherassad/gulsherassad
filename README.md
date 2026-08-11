# Gulsher Assad
**CS student at UBC Okanagan** (BSc, expected Apr 2027) · Kelowna, BC

I build Python backends with a model doing something non-trivial behind them,
things like statistical forecasting, constrained optimization, and LLM-powered
systems, plus the API and frontend work that makes them usable by someone other
than me.

The part I care about most is evaluation. It's easy to build a model that looks
good on the data it was trained on, and easy to write code that passes the tests
you thought to write. Most of my time goes into the other half: walk-forward
backtests instead of in-sample accuracy, comparisons against a real baseline
rather than a flattering one, and coverage over the paths that fail quietly.

---

## Projects

### ✅ [task-manager-api](https://github.com/gulsherassad/task-manager-api)
A RESTful task-management API built with Java and Spring Boot, with full CRUD,
filtering, request validation, and a layered controller-service-repository architecture.
| | |
|---|---|
| **Stack** | Java, Spring Boot, Maven, Spring Data JPA, H2, JUnit |
| **Features** | Create, read, update, delete tasks; filter by status and priority; sort by due date |
| **Engineering** | Bean Validation at the API boundary, layered architecture, JUnit and MockMvc integration tests |

Built as a clean, production-shaped REST service to demonstrate backend
fundamentals in the Java and Spring ecosystem, endpoint design, JPA persistence,
input validation, and automated testing.

### 🐦 [querybird](https://github.com/gulsherassad/querybird)
Ask a database a question in plain English and it writes the SQL, runs it, and
gives you back both the query and the answer.

| | |
|---|---|
| **Execution accuracy** | 64.2% on the full 500-question BIRD Mini-Dev benchmark |
| **Scoring** | BIRD's official evaluator, not a comparison I wrote myself |
| **By difficulty** | 76% simple, 63% moderate, 50% challenging |

An LLM generates the SQL from the question and the database schema, and the query
runs against a read-only, SELECT-only connection with timeouts and row caps so
nothing it writes can modify data. The accuracy came from looking at failures
rather than guessing. A harness categorized all 500 outputs and found that around
99% of the failures were queries that ran fine but returned the wrong answer,
not queries that errored out, which told me the fix was better prompting rather
than retry logic. The README has the full experiment log, including a change I
tried, measured as worse, and reverted.

`Python` · `FastAPI` · `SQLite` · `LLM (Anthropic)` · `JavaScript` · `pytest`

### ⚽ [epl-predictor](https://github.com/gulsherassad/epl-predictor) — [live demo](https://epl-predictor-xmqs.onrender.com)

Premier League match forecaster combining an Elo rating system with a Poisson goals model, blended and served through a FastAPI backend.

| | |
|---|---|
| **1X2 accuracy** | 53.9% across a 1,711-match walk-forward backtest |
| **Baseline** | ~9 points above always-picking-home, approaching betting-market accuracy |
| **Outputs** | Win/draw/loss probabilities, per-fixture expected goals, full scoreline distributions |

Elo ratings update sequentially through five seasons of results while a Poisson model estimates attack and defence strength per team, and the two are blended and renormalized. Backtesting is strictly walk-forward, so each prediction uses only matches played before it and the reported accuracy isn't inflated by leakage.

The README publishes the full model comparison, Elo-only and Poisson-only included, along with where the model loses to the market.

`Python` · `FastAPI` · `scikit-learn` · `pandas` · `pytest` · `Render`

### 🥗 [macro_optimizer](https://github.com/gulsherassad/macro_optimizer)
Meal planning as a constrained optimization problem: minimize calories subject
to a protein floor, a calorie ceiling, and optional carb and fat ranges.

- Solver formulated with **PuLP** and kept entirely separate from the API layer,
  so optimization logic can be tested without touching HTTP
- **Infeasible targets are a real outcome, not an error.** The API returns a
  structured explanation of which constraints conflict instead of failing
- Extends to full-day planning by solving each meal independently, so one
  impossible meal doesn't sink the whole day
- **75 tests** across solver correctness, API integration, and UI behaviour, at
  98% statement coverage on backend source modules
- Schema changes managed through Alembic migrations, and saved plans persist as
  solved snapshots so past results stay accurate when food data changes

`Python` · `FastAPI` · `PuLP` · `PostgreSQL` · `Alembic` · `React` · `Docker` · `pytest` · `Vitest`

### 🎬 [movie-review-platform](https://github.com/gulsherassad/movie-review-platform)
Full-stack movie review platform built by a team of four for COSC 310
(Software Engineering) at UBCO.

I owned the review and comment modules end to end, covering creation, editing,
deletion, and threaded comments, building the REST endpoints in FastAPI with
Pydantic models enforcing validation at the boundary. The service runs as two
containers orchestrated with Docker Compose.

`Python` · `FastAPI` · `Next.js` · `TypeScript` · `Docker`

---

## Working with

| | |
|---|---|
| **Languages** | Python, JavaScript, TypeScript, Java, SQL |
| **Backend** | FastAPI, Pydantic, PostgreSQL, Alembic, Uvicorn |
| **Data & ML** | pandas, NumPy, scikit-learn, PuLP, PyTorch, LLMs (Anthropic API) |
| **Frontend** | React, Next.js |
| **Tooling** | Git, Docker, pytest, Vitest, Render |
---

## Background
Currently working through the IBM AI Engineering Professional Certificate, mostly
for the PyTorch and Keras material. Interested in roles where the work involves
modelling something real and being honest about how well it worked.

## Reach me
[Email](mailto:gulsherassad1@gmail.com) ·
[LinkedIn](https://www.linkedin.com/in/gulshera/) ·
