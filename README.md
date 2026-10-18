---
ZETHETA_INTERN_ID: [YOUR-INTERN-ID]
ZETHETA_PROJECT_CODE: Project 1D
ZETHETA_PROJECT_TITLE: Autonomous Portfolio Rebalancing Agent with Explainable Decisions
ZETHETA_ROLE: Agentic AI Engineer
ZETHETA_SUBMISSION_TYPE: github
ZETHETA_SUBMISSION_DATE: [YYYY-MM-DD]
ZETHETA_TECH_STACK: Python, Pandas, NumPy, Streamlit, Plotly, Pytest
---

# WealthPilot AI — Autonomous Portfolio Rebalancing Agent

A runnable educational prototype for portfolio drift monitoring, multi-trigger rebalancing recommendations, constraint-aware trade generation, audience-specific explanations, human override, audit logs, and strategy comparison.

> **Safety scope:** This is a simulated decision-support project. It does not connect to a broker, execute trades, provide personal investment advice, or validate current tax/regulatory treatment. All prices, portfolios, costs and tax rates are synthetic demonstration assumptions. Human approval is required before any real-world action.

## Features
- Five risk profiles based on the project brief.
- Drift calculation and configurable thresholds.
- Threshold, calendar and event trigger evaluation.
- Trade list generation using target-weight differences and whole-share rounding.
- Illustrative transaction-cost and tax-impact estimates.
- Client, advisor and compliance explanations.
- Compliance checks for allocation totals, long-only holdings, issuer caps and restricted assets.
- Human approve/reject/override controls, emergency kill switch, JSONL audit trail.
- Simple historical simulation comparing quarterly calendar rebalancing with threshold-based rebalancing.
- Streamlit dashboard and automated tests.

## Quick start (Windows)
1. Install Python 3.10 or newer.
2. Extract the ZIP.
3. Open Command Prompt / PowerShell in this folder.
4. Create and activate a virtual environment:
   ```powershell
   py -m venv .venv
   .venv\Scripts\activate
   ```
5. Install dependencies:
   ```powershell
   pip install -r requirements.txt
   ```
6. Start the dashboard:
   ```powershell
   streamlit run src/dashboard/app.py
   ```
7. Run tests in another terminal:
   ```powershell
   pytest -q
   ```

## Project structure
```text
config/                 Profile thresholds and default assumptions
data/                   Synthetic sample portfolio
docs/                   Architecture and project report
src/
  agents/               Rule-based specialist agents and orchestrator
  backtesting/           Strategy comparison simulator
  compliance/            Pre-trade checks and audit logging
  dashboard/app.py       Streamlit dashboard
  explainability/        Three-level explanations and counterfactual
  monitoring/            Drift calculator
  optimisation/          Trade generation and cost/tax estimates
  override/              Human approval and kill switch
  triggers/              Threshold/calendar/event trigger logic
tests/                   Automated unit tests
```

## Demo workflow
1. Select a synthetic portfolio or use the generated sample.
2. Review current and target allocation and drift.
3. Evaluate triggers and generate a proposed trade list.
4. Review estimated costs, illustrative tax impact and compliance checks.
5. Read client, advisor and compliance explanations.
6. Approve/reject/override the proposal. Actions are logged locally to `data/audit_log.jsonl`.
7. Run the backtest to compare illustrative strategy outcomes.

## Important implementation notes
- The core logic is deterministic and runs without an API key. This makes the project reproducible and easy to assess.
- The specialist agents are lightweight Python modules, not autonomous LLMs. This avoids fabricated financial calculations and makes decisions auditable. An LLM provider can be added later behind a controlled explanation interface.
- Backtest outputs are synthetic and should not be presented as real historical performance.
- For a real deployment, use licensed market data, validated tax-lot data, security-level constraints, independent compliance review, monitoring, and broker sandbox integration before considering execution.

## Configuration
Edit `config/risk_categories.json` to change target weights and drift bands. Edit `config/settings.json` for demo cost assumptions and safety settings.

## GitHub submission checklist
- Replace `[YOUR-INTERN-ID]` and submission date in README frontmatter.
- Keep repository private if required by the programme.
- Never commit secrets or real client data.
- Run `pytest -q` and capture the results.
- Record a dashboard demo and add your own screenshots.
- Do not claim test coverage or performance improvements until measured locally.
