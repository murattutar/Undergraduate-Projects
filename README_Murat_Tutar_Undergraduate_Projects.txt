README — Undergraduate Projects Portfolio (B.Sc. Industrial Engineering)
======================================================================

Author
------
Murat Tutar

Undergraduate Background
------------------------
- Boğaziçi University (Bogazici University), Department of Industrial Engineering
- B.Sc. graduation: 2024
- Academic focus: operations research, simulation, forecasting, data mining/ML, and applied optimization
- Core toolkit used across projects: Python, R, C/C++, Arena Simulation, linear/integer programming (PuLP),
  and object-oriented design


Repository Contents (high level)
--------------------------------
This repository contains selected coursework projects, homework deliverables, and the senior graduation
(capstone) report. Files are grouped by project below (PDF reports and ZIP code bundles).


Project Summaries
=================

1) IE 492 Graduation Project — Conversational Schedule Explainer (Capstone)
---------------------------------------------------------------------------
File: "Interpretable AI in explaining a Staff Schedule.pdf"
(Report title: "Conversational Schedule Explainer with ChatGPT")

What it is:
- A capstone project focused on transparency in workforce scheduling decisions.
- The system combines:
  (i) an optimization-based scheduling backend (Gurobi model), and
  (ii) a natural-language “explanation layer” (ChatGPT API) that answers employee questions about the schedule.

Problem motivation:
- In service environments with fluctuating demand, schedules can feel opaque to employees.
- Employees often ask: “Why do I work this shift?”, “Can I swap shifts?”, “Can I leave early?”, “What happens if…?”
- The project builds a conversational interface that explains constraints/objectives and supports structured requests.

Key deliverables / system design:
- Question taxonomy to cover realistic interactions:
  - FAQ-style questions: “How many hours do I work this week?”, “When is my break?”, etc.
  - Query questions: questions about schedule properties / constraint implications.
  - Request questions: “Can you move my shift?”, “Can I work fewer nights?”, feasibility checks + re-optimization.
  - Reasoning questions: “Why was I assigned X instead of Y?”, explanation of trade-offs and constraints.
- Backend functions connect the schedule model to explanations:
  - Uses constraint/objective information to justify assignments.
  - For feasible “request” changes, applies modifications and resolves the model.
  - Returns structured outputs (what changed, feasibility, expected impacts) translated into human language.
- UI focus:
  - Emphasis on usability and “employee-friendly” communication (not just technical optimality).
  - Designed to reduce administrative burden for managers and increase employee engagement.

What it demonstrates:
- End-to-end system thinking: optimization model + interface + natural language explanation.
- Practical explainability: mapping model logic (constraints, objective, feasibility) into understandable answers.
- A strong bridge between OR and human-centered AI.


2) Email Classification (R) — Decision Trees & Random Forests
------------------------------------------------------------
File: "Classification of Emails Using R.pdf"

What it is:
- A supervised learning / data mining project in R where the objective is to classify emails.
- The emphasis is on tree-based methods and performance comparison.

Key components:
- Data preparation and train/test split (and/or cross-validation, depending on the course setup).
- Baseline decision tree model:
  - Model fitting, interpretation of splits, and diagnosing overfitting.
  - Pruning / complexity control to improve generalization.
- Random forest model:
  - Ensemble learning to improve robustness vs a single tree.
  - Tuning key parameters (e.g., number of trees / sampled features) and evaluating results.

Outputs and evaluation (typical for the report):
- Confusion matrix + error metrics (accuracy and class-specific errors).
- Discussion of model trade-offs: interpretability (tree) vs performance (forest).


3) Forecasting Gasoline & Diesel Sales — Time Series Modeling
------------------------------------------------------------
File: "Forecasting Gasoline and Diesel Sales.pdf"

What it is:
- A forecasting report focused on predicting sales for two fuel products (gasoline and diesel).
- The report emphasizes classical time-series workflow: exploration → stationarity/seasonality checks →
  model fitting → model comparison → final forecast.

Key components:
- Exploratory analysis:
  - Trend and seasonality inspection, outlier checks, and transformations when needed.
- Model candidates (typical course scope):
  - Decomposition / seasonal baselines
  - Exponential smoothing family
  - ARIMA/SARIMA-style models (and diagnostics such as residual checks)
  - Regression-based alternatives using time/seasonality features
- Model comparison:
  - Uses a validation approach (holdout window or rolling evaluation) and compares forecast errors.
  - Selects a final model with a justification (accuracy + stability + interpretability).

Outputs:
- Final forecasts for both product series and a short managerial interpretation of expected movement/drivers.


4) Estimating AGV Requirements for a Manufacturing System
---------------------------------------------------------
File: "Estimating AGV Requirements for a Manufacturing System.pdf"

What it is:
- A manufacturing systems / material handling analysis to estimate the number of Automated Guided Vehicles (AGVs)
  required to support a given production and transport workload.

Key components:
- Formalizes the internal transport problem (loads, routes, travel times, pickup/drop-off, service times).
- Compares multiple estimation approaches (the report contrasts methods and discusses their assumptions).
- Produces a recommendation for the AGV fleet size based on:
  - utilization implications,
  - congestion/queueing risk,
  - robustness to variability and workload peaks.

Outputs:
- A reasoned recommendation (not just a single number) and a discussion of which method is most reliable
  under realistic shop-floor conditions.


5) Aggregate Production Planning with Python PuLP (LP/MIP)
----------------------------------------------------------
File: "Python PuLP - Production Planning.pdf"

What it is:
- An aggregate production planning optimization model implemented in Python using PuLP.

Problem setting:
- Two product types (“basic” and “pro” caravans) with different labor requirements and inventory costs.
- Multi-period planning with demand that varies by month.

Decision variables (as described in the report):
- Production quantities by product and month
- Inventory levels
- Workforce level + overtime
- Hiring and firing decisions

Objective and constraints:
- Minimize total cost while meeting demand (production + inventory + labor + overtime + hiring/firing).
- Inter-period inventory balance, capacity / labor constraints, and policy constraints.

Extensions / what-if analysis:
- Additional scenario models (e.g., alternative labor options, rental/storage costs) and cost comparison.
- Managerial interpretation of the resulting production/inventory strategy:
  - produce ahead of peak demand months,
  - manage workforce carefully due to hiring/firing costs,
  - use overtime strategically, etc.

What it demonstrates:
- Translating a planning problem into a clean optimization model.
- Interpreting solutions as actionable production/workforce policies.


6) Discrete-Event Queue Simulation (Manual + C++ Implementation)
---------------------------------------------------------------
File: "Queue Simulation - Discrete Event Scheduling.pdf"

What it is:
- A two-server queueing system simulated via discrete-event scheduling.
- The report includes both (i) the event-trace calculations and (ii) a programmed implementation.

Key components:
- Stochastic inputs (as shown in the report):
  - Interarrival times drawn from a uniform distribution
  - Server 1 service times drawn from a uniform distribution
  - Server 2 service times drawn from a discrete distribution
- Constructs the Future Event List (arrivals, departures) and updates state variables:
  - queue length, server busy/idle indicators, waiting times
- Implementation:
  - Reproduces the table-driven simulation logic in code (C++), validating that results match the manual trace.

Outputs:
- Customer-level timeline table and system performance measures (waiting time, queue evolution, utilization proxies).


7) Queue Simulation in Arena (Multi-Replication Experiment)
-----------------------------------------------------------
File: "Queue Simulation with ARENA.pdf"

What it is:
- A queueing simulation built in Arena, focusing on model construction, experimentation, and performance reporting.

Key components:
- Model block diagram + experiment configuration.
- Multiple replications and summary statistics.
- Output metrics include:
  - average time in queue,
  - average queue length,
  - server utilization,
  - and additional counters for special events tracked in the system.

What it demonstrates:
- Practical simulation workflow in a commercial DES tool: model → replications → confidence/half-width reporting.


8) Object-Oriented Game Design & Implementation (Code Bundle)
-------------------------------------------------------------
File: "Object Oriented Game Design and Implementation.zip"

What it is:
- A programming project emphasizing object-oriented design principles:
  encapsulation, inheritance/polymorphism, and clean class structure.

Typical deliverables inside:
- Source code implementing a small game/application with OOP architecture.
- Separation of concerns (game logic vs. UI/IO) and reusable components.

What it demonstrates:
- Designing a non-trivial codebase with maintainable structure (not a single-script solution).


9) Unconstrained Optimization — Gradient Descent (Code Bundle)
--------------------------------------------------------------
File: "Unconstrained Mathematical Optimisation - Gradient Descent.zip"

What it is:
- An implementation-focused optimization project around gradient descent for unconstrained problems.

Typical components inside:
- Gradient descent algorithm with:
  - step-size/learning-rate choice (possibly fixed or adaptive),
  - stopping criteria (tolerance on gradient norm / improvement),
  - test functions and performance tracking (iterations, convergence behavior).

What it demonstrates:
- Numerical optimization fundamentals and practical implementation details (convergence, stability, tuning).


Notes for Readers / Recruiters
------------------------------
- These projects reflect a consistent focus on “model → implementation → interpretation”:
  building quantitative models, implementing them in code/tools, and translating results into decisions.
- The capstone (IE 492) is the most end-to-end project, combining optimization + an explainability layer
  + interface design for a real operational use case.

