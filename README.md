<div align="center">
  <img src="icon.png" alt="SWRC/HCC Fitter" width="160" />

  # SWRC/HCC Fitter

  **A desktop tool for fitting soil water-retention (SWRC) and hydraulic-
  conductivity (HCC) curves — 45 models, model comparison, bootstrap
  confidence intervals, in a clean HYPROP-style interface.**

  *Capillary + non-capillary (adsorptive/film) soil hydraulic properties
  over the full moisture range, after Weber et al. (2019) and
  Peters–Durner–Iden (2024).*

</div>

---

## What's in the box

**5 basic functions × 3 pore-system modes × 3 variants = 45 models.**

| | Variant | Reference | Notes |
|---|---|---|---|
| ⚫ | **original**  | classic | capillary-only retention + Mualem conductivity |
| 🟢 | **Brunswick** | Weber et al. 2019 (WRR) | modular framework — integral-derived non-capillary saturation + film conductivity |
| 🔵 | **PDI**       | Peters, Durner & Iden 2024 (VZJ) | smoothed piecewise-linear non-capillary saturation, `ha` from S_c |

**Basic functions:** van Genuchten (m = 1−1/n) · van Genuchten (m, n free) ·
Brooks–Corey · Kosugi · Fredlund–Xing — each in **unimodal / bimodal /
trimodal**. Brunswick & PDI force θ → 0 at oven dryness (pF 6.8).

**Engine:** pure NumPy + SciPy (`differential_evolution`) — fast, no heavy ML
stack. **UI:** Dash in an embedded Qt desktop window (no browser needed).

### Features
- **Model-selection matrix** with a uni/bi/tri-modal toggle.
- **Model comparison** — overlay any set of models on one plot, with a sortable
  **leaderboard** (θ-NSE, K-NSE, AICc; lower AICc = better fit).
- **Bootstrap confidence** — 2.5 / 97.5 % parameter intervals and shaded 95 %
  curve bands.
- **Statistics** — RMSE, AICc, water content @ 6 / 33 / 1500 kPa, plant-available water.
- **Rich interactive plots** — Retention Θ(h), K(h), K(Θ); hover readouts,
  scroll-zoom, 4× high-res PNG export.
- CSV upload (one combined file or separate SWRC/HCC) · fitted-curve export.

---

## Install

1. Download **`SWRC-HCC-Fitter-setup.exe`** from the
   [latest release](../../releases/latest) (or this repo).
2. Run it — published by **PEN-PTF**. Follow the wizard (license → location →
   install). When Windows asks to install the **Microsoft Visual C++ runtime**,
   click **Yes** (one-time, needed by Qt).
3. The installer bundles **uv** and the **VC++ runtime**, then uses uv to fetch a
   private Python 3.12 + the scientific stack (Dash, Plotly, NumPy, pandas,
   SciPy, PySide6). **Needs internet on first install; allow a couple of
   minutes.** Afterwards it launches instantly and offline.
4. Start **SWRC-HCC Fitter** from the Start Menu or Desktop shortcut.

> The runtime is provisioned by uv at install time rather than shipped, keeping
> the download lean. Code is compiled to bytecode modules.

---

## Data format

One combined CSV **or** two CSVs. Columns are mapped to roles in the UI
(auto-guessed): `pF (ret.)`, `θ`, `pF (cond.)`, `K`, and an optional
`sample_id`. A sample may have only SWRC or only HCC; whichever is present is
fitted.

---

## License

MIT — see [LICENSE](LICENSE).
