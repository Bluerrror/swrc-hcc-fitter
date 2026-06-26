<div align="center">

<img src="icon.png" alt="SWRC/HCC Fitter" width="140" />

# SWRC/HCC Fitter

### Fit soil water‑retention & hydraulic‑conductivity curves — beautifully.

A polished desktop app for **soil hydraulic property** estimation across the
full moisture range: **108 retention models × 6 conductivity models**, three
fit objectives, two kinds of uncertainty, colour‑coded model comparison, and a
clean HYPROP‑style interface — all in an embedded window, no browser required.

<p>
<a href="https://PTF.bluerror.com/"><img src="https://img.shields.io/badge/▶_use_it_online-no_install-2e8b57?style=for-the-badge&logo=firefoxbrowser&logoColor=white" alt="Use it online"></a>
&nbsp;
<a href="../../releases/latest"><img src="https://img.shields.io/badge/download-installer-1f4e79?style=for-the-badge&logo=windows" alt="Download"></a>
</p>

<b>▶ Try it right now in your browser — no install: <a href="https://PTF.bluerror.com/">PTF.bluerror.com</a></b>

<b>📖 Full user manual with worked examples: <a href="https://bluerror.com/manual.html">bluerror.com/manual.html</a></b>

<img src="https://img.shields.io/badge/retention_models-108-2e86c1">
<img src="https://img.shields.io/badge/conductivity_models-6-2e86c1">
<img src="https://img.shields.io/badge/objectives-nRMSE_·_NSE_·_NLL-8e44ad">
<img src="https://img.shields.io/badge/platform-Windows%20x64-555">
<img src="https://img.shields.io/badge/engine-NumPy%20%2B%20SciPy-1e8449">
<img src="https://img.shields.io/badge/license-MIT-orange">

</div>

---

## ✨ Highlights

- 🧮 **108 retention models** — 12 basic functions × {uni·bi·tri‑modal} × {original·Brunswick·PDI}
- 💧 **6 conductivity models** — 4 capillary‑bundle (Mualem/Burdine/AS/CCG) + Gardner exponential & power, each usable with any retention curve
- 🎯 **Three fit objectives** — **nRMSE**, **NSE**, or Gaussian **NLL** (puts θ and K on one scale)
- 📈 **Two uncertainty modes** — **bootstrap** CIs/bands, *or* **likelihood (NLL)** uncertainty with calibrated or user‑given σ
- 🌈 **Model comparison** — `Ctrl`+click models to overlay; each curve a distinct colour with its own matching 95 % band
- 📊 **Statistical analysis panel** — RMSE · NSE · KGE · NLL per branch, AICc, σ, water content & PAW; switch between models via a dropdown
- 🔤 **Paper‑accurate symbols** — parameter labels follow each variant's source paper (θ_cs/θ_ncs for Brunswick, K_snc, τ_s … for PDI)
- 🖥️ **No browser, no Python needed** — embedded Qt window, one‑click installer
- 📂 **Smart file loading** — CSV, text, or Excel (`.xlsx`/`.xls`); auto-detects the delimiter (`,`/`;`/tab), decimal mark, the right Excel sheet, and where the data table starts (skips instrument metadata)
- 📤 **One‑click export** — fitted parameters and curves to CSV

---

## 🌱 Retention models

**12 basic functions × 3 pore‑system modes (unimodal · bimodal · trimodal) × 3 variants.**

| Variant | Reference | Non‑capillary (film/adsorptive) treatment |
|---|---|---|
| **original**  | classic capillary | none |
| **Brunswick** | Weber et al. 2019 *(WRR)* | integral‑derived non‑capillary saturation + film conductivity |
| **PDI**       | Peters, Durner & Iden 2024 *(VZJ)* | smoothed piecewise‑linear `S_nc`, air‑entry from `S_c` |

> Basic functions: **van Genuchten** (m = 1−1/n) · **van Genuchten** (m, n free) ·
> **van Genuchten (Vogel–Císlerová** air‑entry, 1988**)** · **Brooks–Corey** (1964) ·
> **Campbell** (1974) · **Kosugi** (1996) · **Fredlund–Xing** (constrained & m‑free) ·
> **Brutsaert** (1966) · **Tani** (1982) · **Russo** (1988) ·
> **Dexter** double‑exponential (2008).
> Brunswick & PDI force θ → 0 at oven dryness (pF 6.8), and use each paper's own
> parameter notation in the UI.

## 💧 Conductivity models

Capillary‑bundle models compared in **Peters, Iden & Durner (2023, HESS)** — each
combinable with **every** retention curve:

| Model | Reference | Form |
|---|---|---|
| **Mualem** ⭐ | Mualem 1976 | `q=1, r=2` *(recommended)* |
| **Burdine** | Burdine 1953 | `q=2, r=1` |
| **Alexander–Skaggs** | Alexander & Skaggs 1986 | `q=1, r=1` |
| **Childs–Collis‑George** | Childs & Collis‑George 1950 | moment integral |
| **Gardner (exponential)** | Gardner 1958 | `K = Ks·exp(−kg·h)` |
| **Gardner (power)** | Gardner 1958 | `K = Ks/[1+(h/hk)^pk]` |

---

## 🎯 Fit objective & uncertainty

Choose the objective that scores the θ(h) and K(h) branches together:

| Objective | What it does | Uncertainty |
|---|---|---|
| **nRMSE** | range‑normalised RMSE, so θ and K weigh equally | bootstrap |
| **NSE**   | variance‑normalised (Nash–Sutcliffe) | bootstrap |
| **NLL**   | Gaussian negative log‑likelihood; jointly calibrates the mean (SSE) and noise **σ** | likelihood band |

- **Bootstrap** (nRMSE/NSE): resamples the data and refits to get 2.5–97.5 %
  parameter intervals and shaded curve bands. Set the number of refits (0 = off).
- **Likelihood / NLL**: replaces bootstrap with a Gauss–Newton covariance and
  Monte‑Carlo curve bands. σ can be **calibrated** (σ̂ = RMSE, the Gaussian MLE)
  or **fixed** to your own σθ/σK to control the θ‑vs‑K weighting. Every overlaid
  model gets its **own colour‑matched band**.

Reported metrics per branch: **RMSE · NSE · KGE · NLL**, plus **AICc** for model
selection and water‑content / plant‑available‑water summaries at standard suctions.

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

Upload **CSV, text, or Excel** files — one combined file **or** separate retention/conductivity files. The reader auto-detects the delimiter (comma, semicolon, or tab), the decimal mark (e.g. European `;` + `,`), the best worksheet in an Excel workbook, and the data block even when there are metadata/preamble rows above it. Then map columns to roles in the UI (auto‑guessed):
`pF (ret.)`, `θ`, `pF (cond.)`, `K`, and an optional `sample_id` (pick one sample
to fit). A sample may have only SWRC or only HCC — whichever is present is fitted.
Hover the **ⓘ** badge on any panel for an in‑app explanation.

---

## 📜 References

- **Weber et al. (2019)**, *Water Resources Research* — modular (Brunswick) framework.
- **Peters, Durner & Iden (2024)**, *Vadose Zone Journal* — the PDI model system.
- **Peters, Iden & Durner (2023)**, *HESS* — comparison of capillary‑bundle conductivity models.

## 🔗 Links

- 👤 **GitHub — [Bluerrror](https://github.com/Bluerrror)**
- ⚙️ **Forward‑model engine — [pyspsh](https://github.com/Bluerrror/pyspsh)**
- 🎓 **[Soil Science Section, University of Kassel](https://www.uni-kassel.de/fb11agrar/en/fachgebiete-einrichtungen/bodenkunde/home.html)**

Built on the **pyspsh** soil‑physics forward model, with the numerical fitting
re‑implemented in pure **NumPy + SciPy** (`differential_evolution`) for speed.

Released under the **MIT License** — see [LICENSE](LICENSE).
