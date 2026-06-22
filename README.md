<div align="center">

<img src="icon.png" alt="SWRC/HCC Fitter" width="150" />

# SWRC/HCC Fitter

### Fit soil water‑retention & hydraulic‑conductivity curves — beautifully.

A polished desktop app for **soil hydraulic property** estimation across the
full moisture range: **45 retention models × 4 conductivity models**, model
comparison, bootstrap confidence bands, and a clean HYPROP‑style interface.

<p>
<a href="../../releases/latest"><img src="https://img.shields.io/badge/download-installer-1f4e79?style=for-the-badge&logo=windows" alt="Download"></a>
</p>

<img src="https://img.shields.io/badge/retention_models-45-2e86c1">
<img src="https://img.shields.io/badge/conductivity_models-4-2e86c1">
<img src="https://img.shields.io/badge/platform-Windows%20x64-555">
<img src="https://img.shields.io/badge/engine-NumPy%20%2B%20SciPy-1e8449">
<img src="https://img.shields.io/badge/license-MIT-orange">

</div>

---

## ✨ Highlights

- 🧮 **45 retention models** — 5 basic functions × {uni·bi·tri‑modal} × {original·Brunswick·PDI}
- 💧 **4 conductivity models** — pick any with any retention curve
- 📊 **Model comparison** — overlay curves + sortable leaderboard (NSE, AICc)
- 🎯 **Bootstrap uncertainty** — parameter CIs + shaded 95 % curve bands
- 🖥️ **No browser, no Python needed** — embedded Qt window, one‑click installer
- 📤 **One‑click export** — fitted parameters and curves to CSV

---

## 🌱 Retention models

**5 basic functions × 3 pore‑system modes (unimodal · bimodal · trimodal) × 3 variants.**

| Variant | Reference | Non‑capillary (film/adsorptive) treatment |
|---|---|---|
| **original**  | classic capillary | none |
| **Brunswick** | Weber et al. 2019 *(WRR)* | integral‑derived non‑capillary saturation + film conductivity |
| **PDI**       | Peters, Durner & Iden 2024 *(VZJ)* | smoothed piecewise‑linear `S_nc`, air‑entry from `S_c` |

> Basic functions: **van Genuchten** (m = 1−1/n) · **van Genuchten** (m, n free) ·
> **Brooks–Corey** · **Kosugi** · **Fredlund–Xing**.
> Brunswick & PDI force θ → 0 at oven dryness (pF 6.8).

## 💧 Conductivity models

Capillary‑bundle models compared in **Peters, Iden & Durner (2023, HESS)** — each
combinable with **every** retention curve:

| Model | Reference | Form |
|---|---|---|
| **Mualem** ⭐ | Mualem 1976 | `q=1, r=2` *(recommended)* |
| **Burdine** | Burdine 1953 | `q=2, r=1` |
| **Alexander–Skaggs** | Alexander & Skaggs 1986 | `q=1, r=1` |
| **Childs–Collis‑George** | Childs & Collis‑George 1950 | moment integral |

---

## 🚀 Install

1. **[Download `SWRC-HCC-Fitter-setup.exe`](../../releases/latest)** and run it
   *(published by **PEN‑PTF**)*.
2. Follow the wizard. Click **Yes** when Windows offers to install the
   **Microsoft Visual C++ runtime** (one‑time, required by Qt).
3. The installer ships **uv** + the VC++ runtime, then uv fetches a private
   Python 3.12 + scientific stack (Dash, Plotly, NumPy, pandas, SciPy, PySide6).
   ⏳ *Needs internet on first install — a couple of minutes; instant & offline after.*
4. Launch **SWRC‑HCC Fitter** from the Start Menu or Desktop.

---

## 📂 Data format

One combined CSV **or** two CSVs. Map columns to roles in the UI (auto‑guessed):
`pF (ret.)`, `θ`, `pF (cond.)`, `K`, and an optional `sample_id`.
A sample may have only SWRC or only HCC — whichever is present is fitted.

---

## 📜 References & License

- Weber et al. (2019), *Water Resources Research* — modular (Brunswick) framework.
- Peters, Durner & Iden (2024), *Vadose Zone Journal* — PDI model system.
- Peters, Iden & Durner (2023), *HESS* — comparison of capillary‑bundle conductivity models.

Released under the **MIT License** — see [LICENSE](LICENSE).
