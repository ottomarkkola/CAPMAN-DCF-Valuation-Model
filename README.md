# CAPMAN-DCF-Valuation-Model
# CapMan (CAPMAN.HE) — FCFF DCF + Monte Carlo + Sensitivity

Decided to Value CapMan due to recieving it as a top ( ROE / P/B ) Long candidate from my previous Python Scatter

Excel-based valuation case for **CapMan Plc (CAPMAN.HE)** using a **FCFF DCF** model with a market-based WACC setup, plus **Monte Carlo simulation** and **WACC × terminal growth (g)** sensitivity.

## Snapshot
- **Implied value (central / average): ~€2.10 per share**
- **Current price (reference): ~€1.85 per share**
- Output includes a valuation distribution (median/mean, P5/P95) and histogram.

## Model (high-level)
### FCFF DCF
- `FCFF = NOPAT + D&A + CAPEX − ΔNWC`
- Terminal Value (Gordon growth):
  - `TV = FCFF_last * (1+g) / (WACC − g)`
- Enterprise Value:
  - `EV = PV(FCFF 2026–2032) + PV(TV)`
- Equity Value / Share:
  - `Fair Value = (EV − Net Debt) / Shares`

### WACC & capital structure
- **Cost of debt (Rd):** informed by CapMan’s issued bonds (yield / implied Rd approach)
- **Cost of equity (Re):** CAPM-based, combined with assumed capital structure to produce WACC

## Risk / uncertainty
### Monte Carlo
- Randomized key inputs (e.g., **WACC** and **terminal growth g**) to produce a **distribution of fair value per share**.
- Reported metrics: **median, average, P5/P95, min/max**.

### Sensitivity analysis
- Standard **WACC × g** data table for fair value per share.
