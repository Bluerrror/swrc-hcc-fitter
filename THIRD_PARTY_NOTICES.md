# Third-party notices, data licences and citations

**SWRC/HCC Fitter 3.0.x** (desktop app for Windows, Linux package, and the web version at <https://PTF.bluerror.com>)
Copyright © 2026 Shahab A. Shojaeezadeh. Released under the MIT License, see [LICENSE](LICENSE).
A copy of this file ships with every package: `THIRD_PARTY_NOTICES.md` in the Windows install folder,
in `/opt/swrc-hcc-fitter/` (or `~/.local/share/swrc-hcc-fitter/`) on Linux, and in `/app/` of the web server image.

The MIT License covers **only the original code of SWRC/HCC Fitter**. The soil databases, libraries,
runtimes and fonts listed below are the work of their own authors. They are used under their own licences,
which still apply when they are distributed with the app. Model equations and statistical methods are
credited to the papers that published them (section 4).

Last reviewed: 14 November 2026. Every licence below was checked against the source linked in the
"Verified at" column on that date. Entries that could not be checked against a primary source are marked
**unverified**.

---

## 1. Soil databases bundled with the app

The file `data/soildb.json.gz` holds measured soil samples from three public databases. They are offered
under *"No data? Try a database"*.

| Database | Samples in the app | Dataset (as published) | Licence | Verified at |
|---|---|---|---|---|
| Hohenbrink et al. | 569 | Hohenbrink, T. L., Jackisch, C., Durner, W., Germer, K., Iden, S. C., Kreiselmeier, J., Leuther, F., Metzger, J. C., Naseri, M., & Peters, A. (2023). *Soil hydraulic characteristics in a wide range of saturation and soil properties.* GFZ Data Services. <https://doi.org/10.5880/fidgeo.2023.012> | **CC BY 4.0** | DataCite record of the DOI (`rightsList`), <https://api.datacite.org/dois/10.5880/fidgeo.2023.012> |
| UNSODA 2.0 | 329 | Nemes, A., Schaap, M., Leij, F. J., & Wösten, J. H. M. (2015). *UNSODA 2.0: Unsaturated Soil Hydraulic Database. Database and program for indirect methods of estimating unsaturated hydraulic properties.* US Salinity Laboratory, ARS, USDA. Dataset. <https://doi.org/10.15482/USDA.ADC/1173246> | **U.S. Public Domain** (<https://www.usa.gov/publicdomain/label/1.0/>) | USDA Ag Data Commons record 24851832 (licence field), <https://agdatacommons.nal.usda.gov/articles/dataset/UNSODA_2_0_Unsaturated_Soil_Hydraulic_Database_Database_and_program_for_indirect_methods_of_estimating_unsaturated_hydraulic_properties/24851832>; also catalog.data.gov |
| EU-HYDI (public subset) | 2243 | Weynants, M. (2024). *melwey/euhydi_public: v1.1.0* (initial subset of EU-HYDI for public access). Zenodo. <https://doi.org/10.5281/zenodo.10987813> | **CC BY 4.0** (Zenodo record). The ESDAC page adds conditions, see the note below. | Zenodo record 10987813 (licence field); ESDAC: <https://esdac.jrc.ec.europa.eu/content/european-hydropedological-data-inventory-eu-hydi-database-0> |

**Changes made (as CC BY 4.0 requires us to state them).** For each sample the app keeps only the measured
water-retention points θ(h) and hydraulic-conductivity points K(h), the sand/silt/clay fractions and, where
given, the texture class. Suction heads are converted to pF (log₁₀ of the head in cm) and conductivities to
log₁₀(K in cm d⁻¹). Values are rounded to 6 decimals, and all other fields of the original databases are
left out. Every EU-HYDI sample in the app is part of the public subset v1.1.0. The original datasets are
not modified in any other way, and their authors do not endorse SWRC/HCC Fitter.

**EU-HYDI conditions.** The ESDAC page states that the intellectual property rights stay with the data
providers. Users must cite the data as **"ESDAC/EU-HYDI"** with a link to the ESDAC page, or cite the
EU-HYDI report, and must make proper reference to the source. The same page also says the data are given
"on condition that ... under no circumstances are these data passed to third parties", while the public
subset on Zenodo is released under CC BY 4.0.

**If you use a database soil in your work, please cite:**

- Hohenbrink, T. L., Jackisch, C., Durner, W., Germer, K., Iden, S. C., Kreiselmeier, J., et al. (2023). Soil water retention and hydraulic conductivity measured in a wide saturation range. *Earth System Science Data*, 15, 4417–4432. <https://doi.org/10.5194/essd-15-4417-2023>, and the dataset <https://doi.org/10.5880/fidgeo.2023.012>.
- Nemes, A., Schaap, M. G., Leij, F. J., & Wösten, J. H. M. (2001). Description of the unsaturated soil hydraulic database UNSODA version 2.0. *Journal of Hydrology*, 251(3–4), 151–162. <https://doi.org/10.1016/S0022-1694(01)00465-6>; Leij, F. J., Alves, W. J., van Genuchten, M. Th., & Williams, J. R. (1996). *The UNSODA Unsaturated Soil Hydraulic Database*. EPA/600/R-96/095, U.S. EPA; and the dataset <https://doi.org/10.15482/USDA.ADC/1173246>.
- Weynants, M., Montanarella, L., Tóth, G., et al. (2013). *European Hydropedological Data Inventory (EU-HYDI)*. EUR 26053 EN, Publications Office of the European Union. <https://doi.org/10.2788/5936>; the data as "ESDAC/EU-HYDI" (<https://esdac.jrc.ec.europa.eu/content/european-hydropedological-data-inventory-eu-hydi>); and the public subset <https://doi.org/10.5281/zenodo.10987813>.

The USDA texture presets of *Learner mode* (typical van Genuchten parameters per texture class) are the
class means of Carsel, R. F., & Parrish, R. S. (1988). Developing joint probability distributions of soil
water retention characteristics. *Water Resources Research*, 24(5), 755–769.
<https://doi.org/10.1029/WR024i005p00755>.

---

## 2. Software components distributed with the app

| Component | Version | Where it is used | Licence | Verified at |
|---|---|---|---|---|
| plotly.js | 3.6.0 | all plots (`web/plotly.min.js`) | MIT, © 2012-2026 Plotly, Inc. (file header) | header of the bundled file; <https://github.com/plotly/plotly.js/blob/master/LICENSE> |
| ↳ modules bundled inside plotly.js, e.g. MapLibre GL JS (with code from mapbox-gl-js ≤ 1.13, glfx.js, d3-color) | as bundled | map traces (not used by the app) | BSD-3-Clause / MIT (MapLibre); other bundled modules: **unverified** individually | <https://github.com/maplibre/maplibre-gl-js/blob/main/LICENSE.txt> |
| KaTeX | 0.16.11 | equation rendering (`web/katex/`) | MIT, © 2013-2020 Khan Academy and other contributors | <https://github.com/KaTeX/KaTeX/blob/main/LICENSE> |
| KaTeX fonts | bundled with KaTeX 0.16.11 | `web/katex/fonts/*.woff2` | MIT, © 2018 Khan Academy | <https://github.com/KaTeX/katex-fonts/blob/master/LICENSE> |
| .NET 8 runtime and libraries (self-contained) | 8.0 | desktop and web executables | MIT, © .NET Foundation and Contributors, plus the notices in the runtime's THIRD-PARTY-NOTICES | <https://github.com/dotnet/runtime/blob/main/LICENSE.TXT>, <https://github.com/dotnet/runtime/blob/main/THIRD-PARTY-NOTICES.TXT> |
| ASP.NET Core | 8.0 | web server (`swrc-fitter-web`) | MIT, © .NET Foundation and Contributors | <https://github.com/dotnet/aspnetcore/blob/main/LICENSE.txt> |
| WPF for .NET (incl. `*_cor3.dll` native parts) | 8.0 | Windows desktop window | MIT, © .NET Foundation and Contributors | <https://github.com/dotnet/wpf/blob/main/LICENSE.TXT> |
| ExcelDataReader | 3.7.0 | reading .xls/.xlsx files | MIT, © 2014-2026 ExcelDataReader contributors | NuGet package metadata (`<license>MIT`); <https://github.com/ExcelDataReader/ExcelDataReader/blob/develop/LICENSE> |
| System.Text.Encoding.CodePages | 8.0.0 | legacy Excel encodings | MIT, © .NET Foundation and Contributors | LICENSE.TXT inside the NuGet package; <https://github.com/dotnet/runtime/blob/main/LICENSE.TXT> |
| Microsoft.Web.WebView2 SDK (`Microsoft.Web.WebView2.*.dll`, `WebView2Loader.dll`) | 1.0.2210.55 | Windows desktop window | BSD-3-Clause-style licence, © Microsoft Corporation (text below), plus the package's NOTICE.txt | LICENSE.txt and NOTICE.txt inside the NuGet package |
| Microsoft Edge WebView2 Runtime, Evergreen Bootstrapper (`MicrosoftEdgeWebview2Setup.exe`) | current | run by the Windows installer only if WebView2 is missing | Microsoft software. Microsoft's documentation allows packaging the bootstrapper with an app. The Runtime itself is not shipped and is installed under Microsoft's own terms. | <https://learn.microsoft.com/en-us/microsoft-edge/webview2/concepts/distribution> |
| GNU Fortran runtime (libgfortran), GNU OpenMP (libgomp), libgcc | GCC 16.1.0 (Windows, statically linked in `swrc.dll`); system packages `libgfortran5`/`libgomp1` on Linux (not shipped) | Fortran kernel | GPL-3.0-or-later **with the GCC Runtime Library Exception 3.1** (text below), © Free Software Foundation, Inc. | <https://github.com/gcc-mirror/gcc/blob/master/COPYING.RUNTIME>; licence header of `libgfortran/runtime/main.c` |
| MinGW-w64 runtime (CRT start-up code, gdtoa, math parts) | winlibs GCC 16.1.0 UCRT build (Brecht Sanders) | statically linked in the Windows `swrc.dll` | ZPL 2.1 and the notices of `COPYING.MinGW-w64-runtime.txt` (text below) | <https://github.com/mingw-w64/mingw-w64/blob/master/COPYING.MinGW-w64-runtime/COPYING.MinGW-w64-runtime.txt> |
| winpthreads (MinGW-w64) | as above | statically linked in the Windows `swrc.dll` (OpenMP threads) | MIT, © 2011 mingw-w64 project | <https://github.com/mingw-w64/mingw-w64/blob/master/mingw-w64-libraries/winpthreads/COPYING> |
| Inter typeface | variable font, latin and latin-ext subsets (`web/fonts/Inter-latin.woff2`, `web/fonts/Inter-latin-ext.woff2`) | interface and report text, **bundled and served by the app itself** (no request to Google Fonts) | SIL Open Font License 1.1, © 2016 The Inter Project Authors | <https://github.com/rsms/inter/blob/master/LICENSE.txt> |

**Algorithms re-implemented in the app's own code**

| Algorithm | Where | Source and terms | Verified at |
|---|---|---|---|
| xoshiro256** and splitmix64 random number generators (Blackman & Vigna, 2018) | Fortran kernel | public domain dedication by the authors | <https://prng.di.unimi.it/xoshiro256starstar.c> |
| Shapiro–Wilk W test, Algorithm AS R94 (Royston, 1995, *Applied Statistics* 44(4), 547; <https://doi.org/10.2307/2986146>) | `Stats.cs` | Algorithm published by the Royal Statistical Society, transcribed on StatLib. StatLib states no licence: **unverified** | <https://lib.stat.cmu.edu/apstat/r94> |
| Inverse normal CDF (P. J. Acklam's rational approximation) | `Stats.cs` | published coefficients. Terms: **unverified** (the author's page is offline) | n/a |
| Complementary error function `erfc` (used for the Shapiro–Wilk p-value), ported from fdlibm 5.3 `s_erf.c` (Sun Microsystems, 1993) | `Stats.cs` | fdlibm licence: use, copy, modify and distribute freely, provided the notice is preserved (notice kept in the source and reproduced in Appendix A) | <https://netlib.org/fdlibm/s_erf.c> |
| Logarithm and exponential polynomial coefficients of the vectorised `pow` (fdlibm 5.3 `e_log.c` Lg1–Lg7, `e_exp.c` P1–P5, ln2_hi/ln2_lo/invln2) | Fortran kernel | fdlibm licence as above (notice kept in the source and reproduced in Appendix A) | <https://netlib.org/fdlibm/e_log.c>, <https://netlib.org/fdlibm/e_exp.c> |
| Differential evolution (Storn & Price, 1997) | Fortran kernel | method from the cited paper, own implementation | n/a |

**Not included:** the GCC Quad-Precision Math Library (libquadmath, LGPL-2.1-or-later). Up to version 3.0.2
parts of it were statically linked into the Windows `swrc.dll` through libgfortran. Since 3.0.3 the kernel
is linked without it: libgfortran's only reference to it (formatted output of 128-bit reals, which the
kernel never does) is satisfied by a two-line stub in the app's own code (`kernel/no_quadmath.c`), and
the build fails if any libquadmath code is linked. Up to 3.0.2 the complementary error function in
`Stats.cs` came from *Numerical Recipes*; since 3.0.3 it is the fdlibm port listed above.

**Not used:** the app loads no map tiles and no web analytics. Emoji symbols in the interface are drawn by
the operating system's own emoji font, which the app does not include. The app icon (`icon.png`,
`icon.ico`, `favicon.ico`) belongs to the SWRC/HCC Fitter project.

---

## 3. Licence texts

The full texts below are reproduced as the licences require. Long licences that are published separately
are linked: GNU GPL v3 <https://www.gnu.org/licenses/gpl-3.0.txt>, Creative Commons Attribution 4.0
<https://creativecommons.org/licenses/by/4.0/legalcode>.

The full texts follow at the end of this file, in Appendix A.

---

## 4. Models, equations and methods

The equations are mathematical methods, and SWRC/HCC Fitter implements them in its own code. No licence
is involved, but each is credited to the paper that published it. Please cite the relevant papers when you
publish results obtained with a model.

**Basic retention functions** (each one uni-, bi- or tri-modal following Durner 1994)

- van Genuchten, M. Th. (1980). A closed-form equation for predicting the hydraulic conductivity of unsaturated soils. *Soil Science Society of America Journal*, 44(5), 892–898. <https://doi.org/10.2136/sssaj1980.03615995004400050002x>
- Vogel, T., & Císlerová, M. (1988). On the reliability of unsaturated hydraulic conductivity calculated from the moisture retention curve. *Transport in Porous Media*, 3(1), 1–15. <https://doi.org/10.1007/BF00222683>
- Brooks, R. H., & Corey, A. T. (1964). *Hydraulic properties of porous media*. Hydrology Paper 3, Colorado State University, Fort Collins.
- Campbell, G. S. (1974). A simple method for determining unsaturated conductivity from moisture retention data. *Soil Science*, 117(6), 311–314. <https://doi.org/10.1097/00010694-197406000-00001>
- Kosugi, K. (1996). Lognormal distribution model for unsaturated soil hydraulic properties. *Water Resources Research*, 32(9), 2697–2703. <https://doi.org/10.1029/96WR01776>
- Fredlund, D. G., & Xing, A. (1994). Equations for the soil-water characteristic curve. *Canadian Geotechnical Journal*, 31(4), 521–532. <https://doi.org/10.1139/t94-061>
- Durner, W. (1994). Hydraulic conductivity estimation for soils with heterogeneous pore structure. *Water Resources Research*, 30(2), 211–223. <https://doi.org/10.1029/93WR02676>

**Full-range variants**

- Brunswick: Weber, T. K. D., Durner, W., Streck, T., & Diamantopoulos, E. (2019). A modular framework for modeling unsaturated soil hydraulic properties over the full moisture range. *Water Resources Research*, 55(6), 4994–5011. <https://doi.org/10.1029/2018WR024584>
- Brunswick film-conductivity base and discussion: Peters, A., & Iden, S. C. (2021). Comment on "A modular framework for modeling unsaturated soil hydraulic properties over the full moisture range" by Weber et al. *Water Resources Research*, 57(7), e2020WR028397. <https://doi.org/10.1029/2020WR028397>; Weber, T. K. D., Streck, T., & Diamantopoulos, E. (2025). Reply to the comment. *Water Resources Research*, 61(3), e2023WR036901. <https://doi.org/10.1029/2023WR036901>
- Brunswick parameter ranges: Weber, T. K. D., Finkel, M., da Conceição Gonçalves, M., Vereecken, H., & Diamantopoulos, E. (2020). Pedotransfer function for the Brunswick soil hydraulic property model and comparison to the van Genuchten-Mualem model. *Water Resources Research*, 56(9), e2019WR026820. <https://doi.org/10.1029/2019WR026820>
- PDI: Peters, A., Durner, W., & Iden, S. C. (2024). The PDI model system for parameterizing soil hydraulic properties. *Vadose Zone Journal*, 23(4), e20338. <https://doi.org/10.1002/vzj2.20338>; building on Peters, A. (2013). *Water Resources Research*, 49(10), 6765–6780. <https://doi.org/10.1002/wrcr.20548>; Iden, S. C., & Durner, W. (2014). *Water Resources Research*, 50(9), 7530–7534. <https://doi.org/10.1002/2014WR015937>; Peters, A. (2014). *Water Resources Research*, 50(9), 7535–7539. <https://doi.org/10.1002/2014WR016107>
- Maximum pore-size cutoff (6 cm): Iden, S. C., Peters, A., & Durner, W. (2015). Improving prediction of hydraulic conductivity by constraining capillary bundle models to a maximum pore size. *Advances in Water Resources*, 85, 86–92. <https://doi.org/10.1016/j.advwatres.2015.09.005>
- Film conductivity slope: Tokunaga, T. K. (2009). Hydraulic properties of adsorbed water films in unsaturated porous media. *Water Resources Research*, 45, W06415. <https://doi.org/10.1029/2009WR007734>
- Wang: Wang, Y., Ma, R., & Vereecken, H. (2025). A generalized framework to describe unimodal and bimodal soil hydraulic properties over full water saturation range. *Water Resources Research*, 61(2), e2024WR038450. <https://doi.org/10.1029/2024WR038450>

**Conductivity models**

- Mualem, Y. (1976). A new model for predicting the hydraulic conductivity of unsaturated porous media. *Water Resources Research*, 12(3), 513–522. <https://doi.org/10.1029/WR012i003p00513>
- Burdine, N. T. (1953). Relative permeability calculations from pore size distribution data. *Journal of Petroleum Technology*, 5(3), 71–78. <https://doi.org/10.2118/225-G>
- Alexander, L., & Skaggs, R. W. (1986). Predicting unsaturated hydraulic conductivity from the soil water characteristic. *Transactions of the ASAE*, 29(1), 176–184. <https://doi.org/10.13031/2013.30123>
- Childs, E. C., & Collis-George, N. (1950). The permeability of porous materials. *Proceedings of the Royal Society A*, 201(1066), 392–405. <https://doi.org/10.1098/rspa.1950.0068>
- Gardner, W. R. (1958). Some steady-state solutions of the unsaturated moisture flow equation with application to evaporation from a water table. *Soil Science*, 85(4), 228–232. <https://doi.org/10.1097/00010694-195804000-00006>
- Tortuosity defaults: Peters, A., Iden, S. C., & Durner, W. (2023). Prediction of absolute unsaturated hydraulic conductivity: comparison of four different capillary-bundle models. *Hydrology and Earth System Sciences*, 27, 4579–4593. <https://doi.org/10.5194/hess-27-4579-2023>
- Isothermal vapour conductivity: Saito, H., Šimůnek, J., & Mohanty, B. P. (2006). Numerical analysis of coupled water, vapor, and heat transport in the vadose zone. *Vadose Zone Journal*, 5(2), 784–800. <https://doi.org/10.2136/vzj2006.0007>

**Fitting and statistics**

- Storn, R., & Price, K. (1997). Differential evolution: a simple and efficient heuristic for global optimization over continuous spaces. *Journal of Global Optimization*, 11(4), 341–359. <https://doi.org/10.1023/A:1008202821328>
- Nash, J. E., & Sutcliffe, J. V. (1970). River flow forecasting through conceptual models part I: a discussion of principles. *Journal of Hydrology*, 10(3), 282–290. <https://doi.org/10.1016/0022-1694(70)90255-6>
- Gupta, H. V., Kling, H., Yilmaz, K. K., & Martinez, G. F. (2009). Decomposition of the mean squared error and NSE performance criteria (KGE). *Journal of Hydrology*, 377(1–2), 80–91. <https://doi.org/10.1016/j.jhydrol.2009.08.003>
- Hurvich, C. M., & Tsai, C.-L. (1989). Regression and time series model selection in small samples (AICc). *Biometrika*, 76(2), 297–307. <https://doi.org/10.1093/biomet/76.2.297>
- Shapiro, S. S., & Wilk, M. B. (1965). An analysis of variance test for normality (complete samples). *Biometrika*, 52(3–4), 591–611. <https://doi.org/10.1093/biomet/52.3-4.591>; Royston, P. (1995). Remark AS R94: A remark on Algorithm AS 181: The W-test for normality. *Applied Statistics*, 44(4), 547. <https://doi.org/10.2307/2986146>
- Blackman, D., & Vigna, S. (2021). Scrambled linear pseudorandom number generators. *ACM Transactions on Mathematical Software*, 47(4), 1–32. <https://doi.org/10.1145/3460772>

---

## Appendix A. Licence texts

### plotly.js — MIT License

```text
MIT License

Copyright (c) 2016-2024 Plotly Technologies Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```

The bundled file `web/plotly.min.js` carries the header: *plotly.js v3.6.0, Copyright 2012-2026, Plotly, Inc. All rights reserved. Licensed under the MIT license.*

### MapLibre GL JS (bundled inside plotly.js) — BSD-3-Clause and included notices

```text
Copyright (c) 2023, MapLibre contributors

All rights reserved.

Redistribution and use in source and binary forms, with or without modification,
are permitted provided that the following conditions are met:

    * Redistributions of source code must retain the above copyright notice,
      this list of conditions and the following disclaimer.
    * Redistributions in binary form must reproduce the above copyright notice,
      this list of conditions and the following disclaimer in the documentation
      and/or other materials provided with the distribution.
    * Neither the name of MapLibre GL JS nor the names of its contributors
      may be used to endorse or promote products derived from this software
      without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR
CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL,
EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR
PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF
LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING
NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.


-------------------------------------------------------------------------------

Contains code from mapbox-gl-js v1.13 and earlier

Version v1.13 of mapbox-gl-js and earlier are licensed under a BSD-3-Clause license

Copyright (c) 2020, Mapbox
Redistribution and use in source and binary forms, with or without modification,
are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice,
  this list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright notice,
  this list of conditions and the following disclaimer in the documentation
  and/or other materials provided with the distribution.
* Neither the name of Mapbox GL JS nor the names of its contributors
  may be used to endorse or promote products derived from this software
  without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR
CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL,
EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR
PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF
LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING
NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE,
EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.


-------------------------------------------------------------------------------

Contains code from glfx.js

Copyright (C) 2011 by Evan Wallace

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

--------------------------------------------------------------------------------

Contains a portion of d3-color https://github.com/d3/d3-color

Copyright 2010-2016 Mike Bostock
All rights reserved.

Redistribution and use in source and binary forms, with or without modification,
are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this
  list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice,
  this list of conditions and the following disclaimer in the documentation
  and/or other materials provided with the distribution.

* Neither the name of the author nor the names of contributors may be used to
  endorse or promote products derived from this software without specific prior
  written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR
ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON
ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

### KaTeX — MIT License

```text
The MIT License (MIT)

Copyright (c) 2013-2020 Khan Academy and other contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### KaTeX fonts — MIT License

```text
The MIT License (MIT)

Copyright (c) 2018 Khan Academy

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### .NET runtime — MIT License (same text and holder for ASP.NET Core, WPF and System.Text.Encoding.CodePages)

```text
The MIT License (MIT)

Copyright (c) .NET Foundation and Contributors

All rights reserved.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

The .NET runtime includes further third-party components; their notices are in <https://github.com/dotnet/runtime/blob/main/THIRD-PARTY-NOTICES.TXT>, <https://github.com/dotnet/aspnetcore/blob/main/THIRD-PARTY-NOTICES.txt> and <https://github.com/dotnet/wpf/blob/main/THIRD-PARTY-NOTICES.TXT>.

### ExcelDataReader — MIT License

```text
The MIT License (MIT)

Copyright (c) 2014-2026 ExcelDataReader contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### Microsoft.Web.WebView2 SDK — licence (LICENSE.txt of the NuGet package 1.0.2210.55)

```text
Copyright (C) Microsoft Corporation. All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are
met:

   * Redistributions of source code must retain the above copyright
notice, this list of conditions and the following disclaimer.
   * Redistributions in binary form must reproduce the above
copyright notice, this list of conditions and the following disclaimer
in the documentation and/or other materials provided with the
distribution.
   * The name of Microsoft Corporation, or the names of its contributors 
may not be used to endorse or promote products derived from this
software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

The WebView2 SDK also ships a NOTICE.txt with notices for components Microsoft includes (for example ANTLR, BSD-3-Clause). Microsoft provides that file with the NuGet package `Microsoft.Web.WebView2` 1.0.2210.55 (<https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.2210.55>).

### GCC Runtime Library Exception 3.1 (libgfortran, libgomp, libgcc)

```text
GCC RUNTIME LIBRARY EXCEPTION

Version 3.1, 31 March 2009

Copyright (C) 2009 Free Software Foundation, Inc. <http://fsf.org/>

Everyone is permitted to copy and distribute verbatim copies of this
license document, but changing it is not allowed.

This GCC Runtime Library Exception ("Exception") is an additional
permission under section 7 of the GNU General Public License, version
3 ("GPLv3"). It applies to a given file (the "Runtime Library") that
bears a notice placed by the copyright holder of the file stating that
the file is governed by GPLv3 along with this Exception.

When you use GCC to compile a program, GCC may combine portions of
certain GCC header files and runtime libraries with the compiled
program. The purpose of this Exception is to allow compilation of
non-GPL (including proprietary) programs to use, in this way, the
header files and runtime libraries covered by this Exception.

0. Definitions.

A file is an "Independent Module" if it either requires the Runtime
Library for execution after a Compilation Process, or makes use of an
interface provided by the Runtime Library, but is not otherwise based
on the Runtime Library.

"GCC" means a version of the GNU Compiler Collection, with or without
modifications, governed by version 3 (or a specified later version) of
the GNU General Public License (GPL) with the option of using any
subsequent versions published by the FSF.

"GPL-compatible Software" is software whose conditions of propagation,
modification and use would permit combination with GCC in accord with
the license of GCC.

"Target Code" refers to output from any compiler for a real or virtual
target processor architecture, in executable form or suitable for
input to an assembler, loader, linker and/or execution
phase. Notwithstanding that, Target Code does not include data in any
format that is used as a compiler intermediate representation, or used
for producing a compiler intermediate representation.

The "Compilation Process" transforms code entirely represented in
non-intermediate languages designed for human-written code, and/or in
Java Virtual Machine byte code, into Target Code. Thus, for example,
use of source code generators and preprocessors need not be considered
part of the Compilation Process, since the Compilation Process can be
understood as starting with the output of the generators or
preprocessors.

A Compilation Process is "Eligible" if it is done using GCC, alone or
with other GPL-compatible software, or if it is done without using any
work based on GCC. For example, using non-GPL-compatible Software to
optimize any GCC intermediate representations would not qualify as an
Eligible Compilation Process.

1. Grant of Additional Permission.

You have permission to propagate a work of Target Code formed by
combining the Runtime Library with Independent Modules, even if such
propagation would otherwise violate the terms of GPLv3, provided that
all Target Code was generated by Eligible Compilation Processes. You
may then convey such a combination under terms of your choice,
consistent with the licensing of the Independent Modules.

2. No Weakening of GCC Copyleft.

The availability of this Exception does not imply any general
presumption that third-party software is unaffected by the copyleft
requirements of the license of GCC.
```

libgfortran, libgomp and libgcc are licensed under the GNU General Public License v3 or later with this exception: <https://www.gnu.org/licenses/gpl-3.0.txt>. The source code of GCC 16.1.0, including these libraries, is available from <https://gcc.gnu.org/> and <https://github.com/gcc-mirror/gcc>.

### MinGW-w64 runtime licensing (statically linked in the Windows kernel `swrc.dll`)

```text
MinGW-w64 runtime licensing
***************************

This program or library was built using MinGW-w64 and statically
linked against the MinGW-w64 runtime. Some parts of the runtime
are under licenses which require that the copyright and license
notices are included when distributing the code in binary form.
These notices are listed below.


========================
Overall copyright notice
========================

Copyright (c) 2009, 2010, 2011, 2012, 2013 by the mingw-w64 project

This license has been certified as open source. It has also been designated
as GPL compatible by the Free Software Foundation (FSF).

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

   1. Redistributions in source code must retain the accompanying copyright
      notice, this list of conditions, and the following disclaimer.
   2. Redistributions in binary form must reproduce the accompanying
      copyright notice, this list of conditions, and the following disclaimer
      in the documentation and/or other materials provided with the
      distribution.
   3. Names of the copyright holders must not be used to endorse or promote
      products derived from this software without prior written permission
      from the copyright holders.
   4. The right to distribute this software or to use it for any purpose does
      not give you the right to use Servicemarks (sm) or Trademarks (tm) of
      the copyright holders.  Use of them is covered by separate agreement
      with the copyright holders.
   5. If any files are modified, you must cause the modified files to carry
      prominent notices stating that you changed the files and the date of
      any change.

Disclaimer

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS ``AS IS'' AND ANY EXPRESSED
OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES
OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
EVENT SHALL THE COPYRIGHT HOLDERS BE LIABLE FOR ANY DIRECT, INDIRECT,
INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA,
OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF
LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING
NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE,
EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

======================================== 
getopt, getopt_long, and getop_long_only
======================================== 

Copyright (c) 2002 Todd C. Miller <Todd.Miller@courtesan.com> 
 
Permission to use, copy, modify, and distribute this software for any 
purpose with or without fee is hereby granted, provided that the above 
copyright notice and this permission notice appear in all copies. 
 	 
THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.

Sponsored in part by the Defense Advanced Research Projects
Agency (DARPA) and Air Force Research Laboratory, Air Force
Materiel Command, USAF, under agreement number F39502-99-1-0512.

        *       *       *       *       *       *       * 

Copyright (c) 2000 The NetBSD Foundation, Inc.
All rights reserved.

This code is derived from software contributed to The NetBSD Foundation
by Dieter Baron and Thomas Klausner.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions
are met:
 1. Redistributions of source code must retain the above copyright
    notice, this list of conditions and the following disclaimer.
 2. Redistributions in binary form must reproduce the above copyright
    notice, this list of conditions and the following disclaimer in the
    documentation and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE NETBSD FOUNDATION, INC. AND CONTRIBUTORS
``AS IS'' AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED
TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR
PURPOSE ARE DISCLAIMED.  IN NO EVENT SHALL THE FOUNDATION OR CONTRIBUTORS
BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
POSSIBILITY OF SUCH DAMAGE.


===============================================================
gdtoa: Converting between IEEE floating point numbers and ASCII
===============================================================

The author of this software is David M. Gay.

Copyright (C) 1997, 1998, 1999, 2000, 2001 by Lucent Technologies
All Rights Reserved

Permission to use, copy, modify, and distribute this software and
its documentation for any purpose and without fee is hereby
granted, provided that the above copyright notice appear in all
copies and that both that the copyright notice and this
permission notice and warranty disclaimer appear in supporting
documentation, and that the name of Lucent or any of its entities
not be used in advertising or publicity pertaining to
distribution of the software without specific, written prior
permission.

LUCENT DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE,
INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS.
IN NO EVENT SHALL LUCENT OR ANY OF ITS ENTITIES BE LIABLE FOR ANY
SPECIAL, INDIRECT OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER
IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION,
ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF
THIS SOFTWARE.

        *       *       *       *       *       *       *

The author of this software is David M. Gay.

Copyright (C) 2005 by David M. Gay
All Rights Reserved

Permission to use, copy, modify, and distribute this software and its
documentation for any purpose and without fee is hereby granted,
provided that the above copyright notice appear in all copies and that
both that the copyright notice and this permission notice and warranty
disclaimer appear in supporting documentation, and that the name of
the author or any of his current or former employers not be used in
advertising or publicity pertaining to distribution of the software
without specific, written prior permission.

THE AUTHOR DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE,
INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS.  IN
NO EVENT SHALL THE AUTHOR OR ANY OF HIS CURRENT OR FORMER EMPLOYERS BE
LIABLE FOR ANY SPECIAL, INDIRECT OR CONSEQUENTIAL DAMAGES OR ANY
DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS,
WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION,
ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS
SOFTWARE.

        *       *       *       *       *       *       *

The author of this software is David M. Gay.

Copyright (C) 2004 by David M. Gay.
All Rights Reserved
Based on material in the rest of /netlib/fp/gdota.tar.gz,
which is copyright (C) 1998, 2000 by Lucent Technologies.

Permission to use, copy, modify, and distribute this software and
its documentation for any purpose and without fee is hereby
granted, provided that the above copyright notice appear in all
copies and that both that the copyright notice and this
permission notice and warranty disclaimer appear in supporting
documentation, and that the name of Lucent or any of its entities
not be used in advertising or publicity pertaining to
distribution of the software without specific, written prior
permission.

LUCENT DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE,
INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS.
IN NO EVENT SHALL LUCENT OR ANY OF ITS ENTITIES BE LIABLE FOR ANY
SPECIAL, INDIRECT OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER
IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION,
ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF
THIS SOFTWARE.


=========================
Parts of the math library
=========================

Copyright (C) 1993 by Sun Microsystems, Inc. All rights reserved.

Developed at SunSoft, a Sun Microsystems, Inc. business.
Permission to use, copy, modify, and distribute this
software is freely granted, provided that this notice
is preserved.

        *       *       *       *       *       *       *

Copyright (C) 1993 by Sun Microsystems, Inc. All rights reserved.

Developed at SunPro, a Sun Microsystems, Inc. business.
Permission to use, copy, modify, and distribute this
software is freely granted, provided that this notice
is preserved.

        *       *       *       *       *       *       *

FIXME: Cephes math lib
Copyright (C) 1984-1998 Stephen L. Moshier

It sounds vague, but as to be found at
<http://lists.debian.org/debian-legal/2004/12/msg00295.html>, it gives an
impression that the author could be willing to give an explicit
permission to distribute those files e.g. under a BSD style license. So
probably there is no problem here, although it could be good to get a
permission from the author and then add a license into the Cephes files
in MinGW runtime. At least on follow-up it is marked that debian sees the
version a-like BSD one. As MinGW.org (where those cephes parts are coming
from) distributes them now over 6 years, it should be fine.

=================================================
Some string, memory and time conversion functions
=================================================

Copyright © 2005-2020 Rich Felker, et al.

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

===================================
Headers and IDLs imported from Wine
===================================

Some header and IDL files were imported from the Wine project. These files
are prominent maked in source. Their copyright belongs to contributors and
they are distributed under LGPL license.

Disclaimer

This library is free software; you can redistribute it and/or
modify it under the terms of the GNU Lesser General Public
License as published by the Free Software Foundation; either
version 2.1 of the License, or (at your option) any later version.

This library is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
Lesser General Public License for more details.
```

### winpthreads — MIT License

```text
Copyright (c) 2011 mingw-w64 project

Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the "Software"),
to deal in the Software without restriction, including without limitation
the rights to use, copy, modify, merge, publish, distribute, sublicense,
and/or sell copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
DEALINGS IN THE SOFTWARE.


/*
 * Parts of this library are derived by:
 *
 * Posix Threads library for Microsoft Windows
 *
 * Use at own risk, there is no implied warranty to this code.
 * It uses undocumented features of Microsoft Windows that can change
 * at any time in the future.
 *
 * (C) 2010 Lockless Inc.
 * All rights reserved.
 *
 * Redistribution and use in source and binary forms, with or without modification,
 * are permitted provided that the following conditions are met:
 *
 *
 *  * Redistributions of source code must retain the above copyright notice,
 *    this list of conditions and the following disclaimer.
 *  * Redistributions in binary form must reproduce the above copyright notice,
 *    this list of conditions and the following disclaimer in the documentation
 *    and/or other materials provided with the distribution.
 *  * Neither the name of Lockless Inc. nor the names of its contributors may be
 *    used to endorse or promote products derived from this software without
 *    specific prior written permission.
 *
 * THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AN
 * ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
 * WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED.
 * IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT,
 * INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING,
 * BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
 * DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF
 * LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE
 * OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED
 * OF THE POSSIBILITY OF SUCH DAMAGE.
 */
```

### Inter typeface — SIL Open Font License 1.1

```text
Copyright (c) 2016 The Inter Project Authors (https://github.com/rsms/inter)

This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is copied below, and is also available with a FAQ at:
http://scripts.sil.org/OFL

-----------------------------------------------------------
SIL OPEN FONT LICENSE Version 1.1 - 26 February 2007
-----------------------------------------------------------

PREAMBLE
The goals of the Open Font License (OFL) are to stimulate worldwide
development of collaborative font projects, to support the font creation
efforts of academic and linguistic communities, and to provide a free and
open framework in which fonts may be shared and improved in partnership
with others.

The OFL allows the licensed fonts to be used, studied, modified and
redistributed freely as long as they are not sold by themselves. The
fonts, including any derivative works, can be bundled, embedded,
redistributed and/or sold with any software provided that any reserved
names are not used by derivative works. The fonts and derivatives,
however, cannot be released under any other type of license. The
requirement for fonts to remain under this license does not apply
to any document created using the fonts or their derivatives.

DEFINITIONS
"Font Software" refers to the set of files released by the Copyright
Holder(s) under this license and clearly marked as such. This may
include source files, build scripts and documentation.

"Reserved Font Name" refers to any names specified as such after the
copyright statement(s).

"Original Version" refers to the collection of Font Software components as
distributed by the Copyright Holder(s).

"Modified Version" refers to any derivative made by adding to, deleting,
or substituting -- in part or in whole -- any of the components of the
Original Version, by changing formats or by porting the Font Software to a
new environment.

"Author" refers to any designer, engineer, programmer, technical
writer or other person who contributed to the Font Software.

PERMISSION AND CONDITIONS
Permission is hereby granted, free of charge, to any person obtaining
a copy of the Font Software, to use, study, copy, merge, embed, modify,
redistribute, and sell modified and unmodified copies of the Font
Software, subject to the following conditions:

1) Neither the Font Software nor any of its individual components,
in Original or Modified Versions, may be sold by itself.

2) Original or Modified Versions of the Font Software may be bundled,
redistributed and/or sold with any software, provided that each copy
contains the above copyright notice and this license. These can be
included either as stand-alone text files, human-readable headers or
in the appropriate machine-readable metadata fields within text or
binary files as long as those fields can be easily viewed by the user.

3) No Modified Version of the Font Software may use the Reserved Font
Name(s) unless explicit written permission is granted by the corresponding
Copyright Holder. This restriction only applies to the primary font name as
presented to the users.

4) The name(s) of the Copyright Holder(s) or the Author(s) of the Font
Software shall not be used to promote, endorse or advertise any
Modified Version, except to acknowledge the contribution(s) of the
Copyright Holder(s) and the Author(s) or with their explicit written
permission.

5) The Font Software, modified or unmodified, in part or in whole,
must be distributed entirely under this license, and must not be
distributed under any other license. The requirement for fonts to
remain under this license does not apply to any document created
using the Font Software.

TERMINATION
This license becomes null and void if any of the above conditions are
not met.

DISCLAIMER
THE FONT SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO ANY WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT
OF COPYRIGHT, PATENT, TRADEMARK, OR OTHER RIGHT. IN NO EVENT SHALL THE
COPYRIGHT HOLDER BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
INCLUDING ANY GENERAL, SPECIAL, INDIRECT, INCIDENTAL, OR CONSEQUENTIAL
DAMAGES, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF THE USE OR INABILITY TO USE THE FONT SOFTWARE OR FROM
OTHER DEALINGS IN THE FONT SOFTWARE.
```

### fdlibm (erfc in `Stats.cs`; log/exp coefficients of the kernel's vectorised pow)

Notice from `s_erf.c`, `e_log.c` and `e_exp.c` of fdlibm 5.3 (<https://netlib.org/fdlibm/>), checked
against those files on 14 November 2026:

```text
Copyright (C) 1993 by Sun Microsystems, Inc. All rights reserved.

Developed at SunSoft, a Sun Microsystems, Inc. business.
Permission to use, copy, modify, and distribute this
software is freely granted, provided that this notice
is preserved.
```

### xoshiro256** / splitmix64

```text
Written in 2018 by David Blackman and Sebastiano Vigna (vigna@acm.org)

To the extent possible under law, the author has dedicated all copyright
and related and neighboring rights to this software to the public domain
worldwide.
```
