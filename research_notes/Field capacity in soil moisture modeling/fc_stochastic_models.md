# Field capacity (s_fc) in stochastic and bucket-type soil-moisture models (ecohydrology tradition)

Source key. Local repo papers are the primary sources. Links point to the local file (relative to this notes folder) and, where known, the DOI.
- **[Laio2001]** Laio F., Porporato A., Ridolfi L., Rodriguez-Iturbe I. (2001). Plants in water-controlled ecosystems: active role in hydrologic processes and response to water stress. II. Probabilistic soil moisture dynamics. *Adv. Water Resour.* 24(7), 707–723. Local: [1-s2.0-S0309170801000057-main.md](../../1-s2.0-S0309170801000057-main.md); DOI: https://doi.org/10.1016/S0309-1708(01)00005-7
- **[Rigby2006]** Rigby J.R., Porporato A. (2006). Simplified stochastic soil-moisture models: a look at infiltration. *Hydrol. Earth Syst. Sci.* 10, 861–871. Local: [hess-10-861-2006.md](../../hess-10-861-2006.md); https://doi.org/10.5194/hess-10-861-2006
- **[Daly2006]** Daly E., Porporato A. (2006). Impact of hydroclimatic fluctuations on the soil water balance. *Water Resour. Res.* 42, W06401. Local: [Daly & Porporato 2006](<../../Water Resources Research - 2006 - Daly - Impact of hydroclimatic fluctuations on the soil water balance.md>); https://doi.org/10.1029/2005WR004606
- **[Alizadeh2013]** Alizadeh H., Mousavi S.J. (2013). Coupled stochastic soil moisture simulation-optimization model of deficit irrigation. *Water Resour. Res.* 49, 4100–4113. Local: [alizadeh2013.md](../../alizadeh2013.md); https://doi.org/10.1002/wrcr.20282
- **[Bovier2025]** Bovier M.C., Fedotov S., Ferraris S., Gentile A., Toaldo B. Space-dependent continuous time random walk for soil moisture modeling. *Adv. Water Resour.* (c. 2025; the local file cites 2025 works but does not state volume or year). Local: [awr.md](../../awr.md)
- **[Gandhi2025]** Gandhi P., Oline M., Silber M. (2025, arXiv:2501.01569v1). A flow-kick model of dryland vegetation patterns: the impact of rainfall variability on resilience. Local: [2501.01569v1.md](../../2501.01569v1.md)
- **[Pelak2019]** Pelak N., Porporato A. (2019). Dynamic evolution of the soil pore size distribution and its connection to soil management and biogeochemical processes. *Adv. Water Resour.* Local: [1-s2.0-S0309170819303124-main.md](../../1-s2.0-S0309170819303124-main.md). This is a supplementary repo paper, not on the assigned list.
- **[Calc]** These notes' own numerical evaluation of the [Laio2001] and [Daly2006]/Porporato-2004 equations. Script: `/tmp/claude-0/-home-user/0a3227b4-1897-5dab-a854-a5839cefcaaf/scratchpad/calc/sens2.py`. Results from it are reported only under "Inferences".

Network note: full-text web fetching failed in this session (DNS and proxy 403). Web-derived findings come from search-engine abstracts and snippets. They are flagged as such, and the exact equations from paywalled sources (Porporato et al. 2004; Rodriguez-Iturbe & Porporato 2004 book; Laio 2006; Guswa et al. 2002; Vico & Porporato 2010/2011) could not be checked directly.

---

## 1. How do these models define the FC threshold? Loss-function regimes, leakage formulation, instantaneous vs. decaying drainage

### Takeaway
In the Rodriguez-Iturbe/Porporato/Laio lineage, s_fc is the lower limit of the "leakage" regime of a piecewise loss function ρ(s). Below s_fc, losses are only ET; above it, gravity drainage is added. Laio et al. (2001) define s_fc operationally as a flux criterion, K(s_fc) = 10% of E_max (= 0.05 cm/d), and not as a fixed matric potential. Three treatments of drainage above s_fc exist in the family:
- an exponential decay of K(s) from K_s at saturation to 0 at s_fc (Laio 2001);
- a linear decay (Rodriguez-Iturbe et al. 1999);
- an instantaneous loss of all water above a threshold s_1, placed between FC and saturation (the "minimalist" Milly 1993 / Porporato 2004 / Daly 2006 form).

Other simplified models in the repo have no s_fc at all: the Brooks–Corey percolation in Rigby & Porporato (2006), the CTRW in Bovier (2025) and the flow-kick model in Gandhi (2025).

### Cited Findings
**Laio et al. 2001: water balance and regimes**
- The point water balance is nZ_r ds/dt = φ[s(t);t] − χ[s(t)], where s is relative soil moisture (0 ≤ s ≤ 1), n is porosity and Z_r is the active (root) depth. Losses are χ(s) = E(s) + L(s), i.e. ET plus leakage. Rainfall is marked Poisson (rate λ, exponential depths of mean α), and γ = nZ_r/α. — [Laio2001](../../1-s2.0-S0309170801000057-main.md), Eqs. 1–6
- **The five-regime normalized loss function** (Eq. 16), ρ(s) = χ(s)/nZ_r:
  - 0 for 0 < s ≤ s_h (hygroscopic);
  - η_w (s − s_h)/(s_w − s_h) for s_h < s ≤ s_w (evaporation only, below wilting);
  - η_w + (η − η_w)(s − s_w)/(s* − s_w) for s_w < s ≤ s* (stressed transpiration, stomatal closure);
  - η for s* < s ≤ s_fc (well-watered, ET = E_max, no drainage);
  - η + m(e^{β(s−s_fc)} − 1) for s_fc < s ≤ 1 (leakage).

  Here η_w = E_w/nZ_r, η = E_max/nZ_r and m = K_s/[nZ_r(e^{β(1−s_fc)} − 1)]. — [Laio2001](../../1-s2.0-S0309170801000057-main.md), Eqs. 16–19
- **Leakage law** (Eq. 14): L(s) = K(s) = K_s [e^{β(s−s_fc)} − 1] / [e^{β(1−s_fc)} − 1] for s_fc < s ≤ 1. Leakage is "assumed to happen by gravity at the lowest boundary of the soil layer, neglecting possible differences in matric potential" with the layer below (unit gradient), and K "decays exponentially from … K_s at s = 1, to a value of zero at a field capacity, s_fc". The exponential was chosen "for reasons of mathematical tractability" as an alternative to the power law K = K_s s^c, with c = 2b + 3. — [Laio2001](../../1-s2.0-S0309170801000057-main.md), §2.6
- **β calibration:** equating the area under the exponential and power-law curves between s_fc and 1 gives β = 2b + 4, ranging "from 12 for sand to 26 for clay". — [Laio2001](../../1-s2.0-S0309170801000057-main.md), §2.6
- **Operational FC definition:** "the field capacity s_fc … is operationally defined as the value of soil moisture at which the hydraulic conductivity becomes negligible (here 10%) compared to the maximum daily evapotranspiration losses E_max (for this purpose assumed to be 0.5 cm/d). The power-law relationship (15) has been used to estimate s_fc." Table 1 repeats this: s_fc "is the s level at which the leakage losses become negligible with respect to the evapotranspiration losses". In contrast, s_h, s_w and s* are fixed by matric potentials of −10, −3 and −0.03 MPa on Clapp–Hornberger retention curves. — [Laio2001](../../1-s2.0-S0309170801000057-main.md), §2.6 and Table 1 footnote a
- **Drainage is not instantaneous above s_fc.** During a dry-down from s_0 ≥ s_fc, the solution follows a closed-form log/exponential decay until s_fc is reached at time t_sfc. After that, s decays linearly at rate η until s*, then exponentially toward s_w and s_h (Eqs. 20–21). This makes s_fc the switch point between nonlinear (drainage) and linear (constant-ET) decay. — [Laio2001](../../1-s2.0-S0309170801000057-main.md), Eqs. 20–21
- **Earlier linear form:** the Laio (2001) exponential leakage is "a considerable improvement with respect to the linear decay of the leakage losses used in the model by Rodriguez-Iturbe et al. [1999]". The 1999 model also had ET declining linearly from E_max at s* to zero at s = 0, with no s_w or s_h. — [Laio2001](../../1-s2.0-S0309170801000057-main.md), §§2.5–2.6. The linear RI-1999 leakage form L(s) = K_s (s − s_fc)/(1 − s_fc) is reproduced, with s_e in place of s_fc and s_s in place of 1, in [Alizadeh2013](../../alizadeh2013.md), Eq. 13.
- **Runoff** is generated only by saturation excess: a jump is truncated at 1 − s, which puts an atom of probability at s = 1. This is equivalent to "deterministic losses which take place at an infinite rate above s = 1". The analogue of this idea at s_1 is used by the minimalist models. — [Laio2001](../../1-s2.0-S0309170801000057-main.md), §2.3, Eq. 10
- **Steady-state pdf** (Eq. 29): p(s) = C/ρ(s) · exp(−γs + λ'∫ du/ρ(u)). In the leakage segment (s_fc < s ≤ 1), the pdf has a distinct closed form (Eq. 31, 4th branch) that depends on β, m and s_fc. Mean leakage is ⟨L⟩ = nZ_r ∫_{s_fc}^1 L(s)p(s) ds, with a closed form in terms of P(s_fc), p(s_fc) and p(1) (Eq. 42). — [Laio2001](../../1-s2.0-S0309170801000057-main.md), Eqs. 29–31, 42–44

**Minimalist (instantaneous-drainage) form**
- Daly & Porporato (2006): "Following the minimalist approach of Milly [1993] and Porporato et al. [2004], we will assume that runoff and drainage take place instantaneously (at the daily timescale) only close to saturation, i.e., for s ≥ s_1, where s_1 is a parameter comprised between field capacity and saturation." Rain exceeding nZ_r(s_1 − s) is "immediately lost as runoff or drainage" (lumped as LQ). ET = f(s)E_p, with f decreasing linearly from 1 at s_1 to 0 at s_w. — [Daly2006](<../../Water Resources Research - 2006 - Daly - Impact of hydroclimatic fluctuations on the soil water balance.md>), ¶19–20
- The storage capacity is w_0 = nZ_r(s_1 − s_w), and x = (s − s_w)/(s_1 − s_w) ∈ [0,1]. With no ET noise (b = 0), the pdf "reduces to a truncated Gamma distribution [e.g., Porporato et al., 2004]". The normalized water balance is 1 = D_I⟨x⟩ + ⟨LQ⟩/⟨R⟩ (Eq. 13 with V_I = 0), where D_I = Ē_p/(αλ) is the Budyko dryness index. — [Daly2006](<../../Water Resources Research - 2006 - Daly - Impact of hydroclimatic fluctuations on the soil water balance.md>), ¶21, ¶24, Eq. 13
- Example values: n = 0.373, Z_r = 300 mm, s_w = 0.047, s_1 = 0.6, Ē_p = 3.7 mm/d. Konza Prairie dry-down losses were "approximated with a linear dependence on s". — [Daly2006](<../../Water Resources Research - 2006 - Daly - Impact of hydroclimatic fluctuations on the soil water balance.md>), Fig. 4–5 captions, ¶20

**Models without an FC threshold**
- **Rigby & Porporato 2006 (IEM and FDEM):** both use a continuous Brooks–Corey percolation term between storms, nZ_r ds/dt = −(k_s s^{c+1} + E_max s), with c = 2(1+m)/m. There is no s_fc: percolation acts at all s. The IEM pdf is p(s) = C s^{λ/η−1} e^{−γs}(E_max + k_s s^c)^{−λ/(cη)−1}. — [Rigby2006](../../hess-10-861-2006.md), Eqs. 2, 5, 6
- **Alizadeh & Mousavi 2013:** replace s_fc with an "effective field capacity" s_e = ((Z − Z_r)/h_b)^{−1/b} − θ_r/n. This "depend[s] on the water table depth and soil properties" and marks "the relative soil moisture level at which soil shifts from the drainage behavior to the capillary uptake condition and vice versa" (after Vervoort & van der Zee 2008). Leakage is linear above s_e, L = K_s (s − s_e)/(s_s − s_e). Below s_e, capillary flux CF(s) is added: a constant m = K_s G for s_c ≤ s ≤ s*, then a linear decline to 0 at s_e. — [Alizadeh2013](../../alizadeh2013.md), ¶28–29, Eqs. 12–13, 15
- **Bovier et al. (c. 2025):** a space-dependent continuous-time random walk with Mittag-Leffler waiting times in three layers (0–30, 30–60, 60–100 cm). It has no FC parameter. Below 30 cm, particles make downward 1-cm jumps "because of pressure and gravity", and the surface is an absorbing state for ET. Dry spells are modeled starting "24 h after the last rainfall because of the coarseness of the soil" (loamy-sand to sandy site, Grugliasco, Italy). — [Bovier2025](../../awr.md), §2 and lines 62–96
- **Gandhi et al. 2025 (flow-kick):** soil water W loses water only by linear evaporation (−LW, L = 0.0075 d⁻¹) and saturating uptake ΓB·W/(1 + W/A), with A = 10 cm a "soil water saturation level" for transpiration. Water is redistributed only through storm "kicks" governed by biomass-dependent infiltration (K_I = 200 cm/d; bare/vegetated contrast f = 0.1). The flow equations contain no field-capacity threshold and no drainage or leakage term. — [Gandhi2025](../../2501.01569v1.md), Eqs. 1a–2b, Table 1

**Web sources (abstracts and snippets)**
- Bassiouni et al. (2018) describe the Laio-type loss curve as having five saturation thresholds, including field capacity, defined as the level "where gravity drainage becomes negligible". — [Bassiouni et al. 2018, HESS 22:3229](https://hess.copernicus.org/articles/22/3229/2018/hess-22-3229-2018.pdf) (search snippet)

### Inferences
- In Laio 2001, s_fc is functionally a flux-defined parameter: K(s_fc) ≈ 0.05 cm/d = 5.8×10⁻⁷ cm/s. This sits inside the 10⁻⁶–10⁻⁸ cm/s "negligible flux" range used in flux-based FC literature (see Q4). It is not a −33 kPa point.
- Because L(s_fc) = 0 exactly and L rises as e^{β(s−s_fc)}, with β ≈ 12–27, leakage is concentrated in a narrow band just below saturation. The exponential model therefore behaves between the linear RI-1999 form and the instantaneous minimalist s_1 form. A large β makes it approach the threshold (instantaneous) behaviour.
- Minimalist models merge s_fc and runoff into a single threshold s_1 (FC ≤ s_1 ≤ 1). FC then enters only through the storage capacity w_0. This is why s_1 is often loosely described as "field capacity" in that literature, although Daly & Porporato explicitly place it between FC and saturation.

### Gaps
- The exact equations of Rodriguez-Iturbe et al. (1999, Proc. R. Soc. A 455:3789) could not be accessed. The linear leakage form is inferred from secondary statements in [Laio2001] and [Alizadeh2013].
- Laio 2001 does not report the s_fc obtained with the 0.1·E_max criterion for different E_max values, so the dependence of s_fc on climate (via E_max) is implicit and not tabulated.

---

## 2. How sensitive are the pdf, mean water stress, leakage fraction and ET partitioning to s_fc?

### Takeaway
No source available here gives a dedicated analytical sensitivity analysis of s_fc. In the minimalist model, analytical results show s_fc (via s_1) acts only through the storage index γ = w_0/α = nZ_r(s_1 − s_w)/α, paired with the dryness index D_I. Shifting s_1 has the same effect as changing the effective soil depth. In the full Laio model, these notes' own evaluation of the published equations (loam) shows that leakage is the most sensitive output: raising s_fc from 0.57 to 0.80 cuts ⟨L⟩/⟨R⟩ by about 40–45% in a dry climate. The ET fraction and mean s change by only a few percent. Stress statistics respond strongly only in wet climates, where the pdf mass sits near s* to s_fc.

### Cited Findings
- **Porporato et al. 2004:** Porporato, Daly & Rodriguez-Iturbe (2004), *Am. Nat.* 164(5):625–632, extend Budyko's curve and classify "soil water balance of the world ecosystems based on two governing dimensionless groups summarizing the climate, soil, and vegetation conditions". Plant carbon uptake depends on rainfall intermittency and magnitude, not just totals. — [Porporato et al. 2004, Am. Nat. (journal page)](https://www.journals.uchicago.edu/doi/10.1086/424970); [Princeton record](https://collaborate.princeton.edu/en/publications/soil-water-balance-and-ecosystem-response-to-climate-change/)
- In that minimalist framework, the normalized variable and storage are x = (s − s_w)/(s_1 − s_w) and w_0 = nZ_r(s_1 − s_w). The parameters are γ = w_0/α ("inverse of the normalized mean rainfall depth") and η = Ē_p/w_0, and the b = 0 pdf is a truncated Gamma. — [Daly2006](<../../Water Resources Research - 2006 - Daly - Impact of hydroclimatic fluctuations on the soil water balance.md>), ¶21, ¶24, notation list
- **Laio 2001, texture and pdf:** coarser texture shifts the pdf "toward drier conditions, which in the most extreme case can reach a difference of 0.2 in the value of the mode". Compared with RI-1999, the exponential leakage "provides smoother pdfs for wet conditions, and also yields slightly lower values of soil moisture as a result of an increased relevance of leakage". — [Laio2001](../../1-s2.0-S0309170801000057-main.md), §3, Fig. 8 discussion
- **Laio 2001, texture trade-off:** a finer soil's lower K "increases soil water availability and thus the time to reach the wilting point", but its higher s_h, s_w and s* "lead to an increase in the amount of residual water which is not extractable". — [Laio2001](../../1-s2.0-S0309170801000057-main.md), §2.7
- **Laio 2001, water balance:** ⟨L⟩ is analytic (Eq. 42). Fig. 10 shows a maximum of both leakage and ET at intermediate λ for fixed total rainfall, and a strongly nonlinear dependence of all components on nZ_r. — [Laio2001](../../1-s2.0-S0309170801000057-main.md), §4, Eqs. 38–44, Fig. 10
- **Daly & Porporato 2006:** "the term related to leakage and runoff in equation (13) cannot change considerably" when ET variability changes. The soil-moisture pdf is "not much affected by evapotranspiration variability", while "rainfall variability … is much more significant". — [Daly2006](<../../Water Resources Research - 2006 - Daly - Impact of hydroclimatic fluctuations on the soil water balance.md>), abstract, ¶25, ¶29
- **Alizadeh 2013 (irrigated, FC-related leakage):** with stress-avoidance irrigation of barley (clay loam, DAID), "about 30% of infiltrated irrigation is deeply percolated from the root zone". Capillary flux supplied 33% of ET. — [Alizadeh2013](../../alizadeh2013.md), ¶61
- **Alizadeh 2013 (uncertainty):** the uncertainty analysis varied s*, n, K_s, Z (water-table depth), Z_r and ET_max. Water-table depth Z sets the effective FC s_e, but s_e itself was not varied as an independent factor. — [Alizadeh2013](../../alizadeh2013.md), ¶74, Table 2

### Inferences
**Closed form for the minimalist model.** Setting b = 0 in Daly & Porporato's Eq. 13 and using the truncated-Gamma pdf p(x) ∝ x^{γ/D_I − 1}e^{−γx} gives:

⟨LQ⟩/⟨R⟩ = D_I γ^{γ/D_I − 1} e^{−γ} / [Γ(γ/D_I) − Γ(γ/D_I, γ)], and ⟨ET⟩/⟨R⟩ = 1 − ⟨LQ⟩/⟨R⟩.

This matches the form usually quoted from Porporato et al. (2004), but it was derived here and not checked against that paper. It follows that ∂(ET/R)/∂s_1 = (nZ_r/α)·∂(ET/R)/∂γ. A change Δs_1 is therefore exactly equivalent to a change in rooting depth Δ(Z_r) = Z_r Δs_1/(s_1 − s_w).

**[Calc] minimalist example** (loam n = 0.45, Z_r = 30 cm, s_w = 0.24, α = 1.5 cm, E_max = 0.45 cm/d):

| λ (d⁻¹) | D_I | s_1 | ⟨LQ⟩/⟨R⟩ | ET/R |
|---|---|---|---|---|
| 0.2 | 1.5 | 0.57 | 0.28 | 0.72 |
| 0.2 | 1.5 | 0.65 | 0.24 | 0.76 |
| 0.2 | 1.5 | 0.75 | 0.20 | 0.80 |
| 0.2 | 1.5 | 0.85 | 0.17 | 0.83 |
| 0.5 | 0.6 | 0.57 | 0.55 | 0.45 |
| 0.5 | 0.6 | 0.85 | 0.50 | 0.50 |

The partitioning is more sensitive to s_1 in water-limited climates (D_I > 1).

**[Calc] full Laio 2001 model** (loam, Table 1; Z_r = 30 cm, α = 1.5 cm, E_max = 0.45, E_w = 0.01 cm/d, Δ = 0). s_fc was varied with K_s = 20 cm/d and β = 14.8 held fixed; ⟨ζ⟩ is an unconditional static-stress proxy (q = 2).

| λ (d⁻¹) | s_fc | ⟨s⟩ | L/R | Q/R | ET/R | P(s < s*) | ⟨ζ⟩ |
|---|---|---|---|---|---|---|---|
| 0.2 | 0.57 | 0.440 | 0.131 | 0.015 | 0.854 | 0.83 | 0.288 |
| 0.2 | 0.65 | 0.445 | 0.116 | 0.016 | 0.868 | 0.81 | 0.282 |
| 0.2 | 0.80 | 0.463 | 0.074 | 0.022 | 0.903 | 0.77 | 0.266 |
| 0.5 | 0.57 | 0.626 | 0.387 | 0.059 | 0.554 | 0.32 | 0.030 |
| 0.5 | 0.65 | 0.640 | 0.374 | 0.065 | 0.561 | 0.27 | 0.025 |
| 0.5 | 0.80 | 0.700 | 0.318 | 0.105 | 0.577 | 0.16 | 0.015 |

What the table shows:
- Leakage is the most s_fc-sensitive flux.
- Part of the "saved" leakage reappears as runoff: Q/R roughly doubles in the wet case, because the soil stays nearer saturation.
- ET/R and ⟨s⟩ are weakly sensitive (a change of 0.02–0.07 in ⟨s⟩).
- The stress probability P(s < s*) halves in the wet climate but changes little in the dry one.

Practical implication: errors in s_fc matter most for recharge and leaching estimates (e.g., nitrate, salts) and for wet-climate stress statistics, and less for ET or productivity in semi-arid settings. This is a self-computed illustration, not a published result.

### Gaps
- The full text of Porporato et al. (2004) and the Rodriguez-Iturbe & Porporato (2004) book (where sensitivity to s_1 and γ is discussed) could not be accessed, so their exact analytical results and figures on s_1 are not quoted.
- No paper found presents ∂⟨L⟩/∂s_fc or the sensitivity of Porporato et al.'s (2001) dynamic water stress θ̄ to s_fc. This appears to be an open gap in the literature, or at least not reachable here.

---

## 3. Bucket models beyond this lineage (Manabe 1969, Milly 1993/1994, Guswa 2002, Laio 2006, Vico & Porporato irrigation, minimalist models)

### Takeaway
The classic land-surface "bucket" (Manabe 1969) uses FC as a hard storage ceiling: about 15 cm of water in a 1 m layer, with overflow as runoff, and ET reduced below 75% of FC. Milly's analytical stochastic-storage models reduce FC to a plant-available water-holding capacity (FC minus wilting point times depth). The Princeton/Duke ecohydrology models keep FC as a separate leakage threshold, or merge it into s_1. Later extensions (Laio 2006 vertical model; Vico & Porporato irrigation; Vervoort & van der Zee capillary flux) either use FC as the post-event "reset" state or make it depend on boundary conditions.

### Cited Findings
- **Manabe (1969) bucket** (secondary sources): field capacity 0.15 m of water in a uniform 1 m layer. ET occurs at the potential rate down to 0.75 × FC and declines proportionally below that. Water above 15 cm overflows as runoff. A later variant notes that the original "overestimates evaporation during wet periods and underestimates it during dry periods". — [AMS conference paper (secondary)](https://ams.confex.com/ams/pdfpapers/72752.pdf); [HAL: "Linking stream flow to rainfall at the annual time step: the Manabe bucket model revisited", J. Hydrol. 2006](https://hal.inrae.fr/hal-02588062)
- **Milly 1993:** "An analytic solution of the stochastic storage problem applicable to soil water", *Water Resour. Res.* 29(11):3755–3758. It is cited as the origin of the minimalist "instantaneous drainage above a threshold" assumption. — [Daly2006](<../../Water Resources Research - 2006 - Daly - Impact of hydroclimatic fluctuations on the soil water balance.md>), ¶19; [Rigby2006](../../hess-10-861-2006.md), refs
- **Milly 1994:** "Climate, soil water storage, and the average annual water balance", *Water Resour. Res.* 30. Partitioning depends on seven dimensionless numbers, including "the ratio of the spatial average plant-available water-holding capacity of the soil to annual average precipitation". Uncalibrated, it gives eastern-US runoff and ET of 250 and 741 mm, against 263 and 728 mm observed. A companion *Adv. Water Resour.* 17:19–24 (1994) paper using the same storage concept underestimated runoff by about 30% (187 mm). — [USGS pubs: WRR 1994](https://pubs.usgs.gov/publication/70187191); [USGS pubs: AWR 1994](https://pubs.usgs.gov/publication/70017401)
- **Milly & Dunne / Milly 1997:** studied the sensitivity of the global water balance to land water-holding capacity and rooting depth. — cited in [Laio2001](../../1-s2.0-S0309170801000057-main.md), §2.4
- **Guswa, Celia & Rodriguez-Iturbe (2002)**, *Water Resour. Res.* 38(9), doi:10.1029/2001WR000826 (search abstract and snippets):
  - compared a zero-dimensional bucket based on Laio et al. (2001) with a 1-D Richards-equation model;
  - predicted growing-season ET and root-zone saturation;
  - the bucket "cannot represent the migration of a wetting front" and "predicts higher rates of uptake immediately following a rain event";
  - E/T partitioning may differ between the two models.
  — [Wiley](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2001WR000826); [Princeton PDF](https://www.princeton.edu/~celia/cv4papers/Guswa%20et%20al%20(WRR%20-%20Published%20Version%202002).pdf). Rigby & Porporato point to Guswa et al. (2002) "for a comparison of vertically lumped versus distributed models". — [Rigby2006](../../hess-10-861-2006.md), §1
- **Laio (2006):** "A vertically extended stochastic model of soil moisture in the root zone", *Water Resour. Res.* 42, doi:10.1029/2005WR004502. It includes random rainfall, vertical root distribution, and linear or nonlinear transpiration response, and gives depth-dependent analytical steady-state pdfs. Snippets indicate infiltration and redistribution are treated as instantaneous piston flow. After one day, soil water drops "to values close to the literature values of field capacity", with acknowledged "intrinsic subjectivity in the definition of field capacity". — [Wiley](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2005WR004502) (search snippets)
- **Vico & Porporato (2010)**, "Traditional and microirrigation with stochastic soil moisture", *Water Resour. Res.* 46, W03509: "a traditional scheme, consisting of the application of fixed water volumes that bring soil moisture to field capacity, and a microirrigation scheme supplying water continuously in order to avoid plant water stress". Exact steady-state pdfs are obtained for both. — [DukeSpace record](https://dukespace.lib.duke.edu/items/5efe097e-1e84-461d-9328-44976c3257ba)
- **Vico & Porporato (2011)**, "From rainfed agriculture to stress-avoidance irrigation: I. A generalized irrigation scheme with stochastic soil moisture", *Adv. Water Resour.* 34(2):263–271. Rainfed and stress-avoidance irrigation are the extreme cases. — [Princeton record](https://collaborate.princeton.edu/en/publications/from-rainfed-agriculture-to-stress-avoidance-irrigation-i-a-gener/)
- **Alizadeh & Mousavi (2013)**, using the Vico & Porporato (2011) scheme:
  - an intervention point s̃ and target level ŝ;
  - stress avoidance when s̃ = s*, and deficit irrigation when s̃ < s*;
  - "traditional irrigation often entails an application that brings the soil moisture back to the field capacity or a level slightly above it due to salt control considerations";
  - microirrigation corresponds to s̃ = ŝ.

  In their model the target is tied to the effective FC s_e set by water-table depth. — [Alizadeh2013](../../alizadeh2013.md), ¶25–28
- **Vervoort & van der Zee (2008)**, "Simulating the effect of capillary flux on the soil water balance in a stochastic ecohydrological framework", *Water Resour. Res.* 44, doi:10.1029/2008WR006889. This is the source of the water-table-dependent effective FC used by Alizadeh. — [EarthRef record](https://earthref.org/ERR/118774); [Alizadeh2013](../../alizadeh2013.md), ¶28
- **Tamea, Laio, Ridolfi et al. (2009)**, groundwater-dependent ecosystems: a soil-moisture model at generic depths with capillary rise, coupled to a stochastic water-table model. — [FAO AGRIS record](https://agris.fao.org/search/en/records/65df9a357c7033e84bee705f)
- **Kim, Stricker & Torfs (1996)** and **Eagleson (1978)**: finite-duration-event (Philip infiltration) precursors that use continuous Brooks–Corey percolation rather than an FC threshold. — [Rigby2006](../../hess-10-861-2006.md), §2.2

### Inferences
- The lineage moves from "FC as bucket brim" (Manabe; Milly's storage capacity) to "FC as onset of a state-dependent drainage flux" (Laio 2001), and then back to "FC/s_1 as an effective brim" in minimalist analytical work (Porporato 2004; Daly 2006). The choice is driven by analytical tractability.
- In irrigation applications, s_fc sets the target level of traditional irrigation and therefore directly controls irrigation-induced leakage and salt leaching. This makes s_fc a management-relevant parameter, unlike its weak role in semi-arid ET.

### Gaps
- Manabe (1969, *Mon. Weather Rev.* 97) was not accessed directly; its parameter values are from secondary sources.
- The specific Guswa et al. (2002) results on drainage and on bucket vs. Richards differences in leakage or FC could not be extracted.
- The assignment's "Laio 2006 analytical model with general loss functions" could not be confirmed under that description. The 2006 Laio WRR paper found is the vertically extended model; a general-loss-function analytical treatment may instead be in Rodriguez-Iturbe & Porporato (2004) or other Laio papers.

---

## 4. Criticisms and extensions: vertically averaged vs. resolved, non-instantaneous drainage, multi-layer stochastic models, −33 kPa vs. flux-based FC

### Takeaway
The main criticisms are:
- vertical averaging cannot represent wetting fronts and post-storm drainage (Guswa 2002; Rigby & Porporato 2006);
- FC is not a static soil constant: it depends on flux criterion, initial wetness, layering and water table (Twarakavi 2009; Assouline & Or 2014; Romano 2011; Vervoort & van der Zee 2008);
- in bucket models, flux- or drainage-based FC outperforms fixed retention-curve points.

Laio's own definition (K = 0.1·E_max) is in fact a flux criterion. Its s_fc lies wetter than the −33 kPa point, and the −30 kPa level is used instead for s*.

### Cited Findings
- **Rigby & Porporato (2006), during-storm leakage:** "accounting for fractional loss to leakage during a storm event is probably of equal or more concern for improving the accuracy of simplified models than is runoff". In the IEM the error from instantaneous events "is concentrated at an instant in time and is then damped quickly by the strongly nonlinear character of percolation". Kim et al. (1996), who neglected percolation during storms, overestimate infiltration. — [Rigby2006](../../hess-10-861-2006.md), §4
- **Rigby & Porporato (2006), IEM vs. FDEM:** the vertically averaged IEM reproduces FDEM pdfs well. Differences are mainly "in the position and less in the shape" and are largest for deep, clay or intense-rain cases. For s_0 = 0.8, the IEM saturation atom is about 0.14 vs. about 0.02 in the FDEM. — [Rigby2006](../../hess-10-861-2006.md), §3, Figs. 5–6, 10
- **Laio (2001) limitations:** the unit-gradient leakage "implies no interaction with the underlying soil layers and the water table"; applicability "needs to be assessed case by case". — [Laio2001](../../1-s2.0-S0309170801000057-main.md), §2.6
- **Bovier et al. (c. 2025):** an alternative to "traditional formulations (based on Richards' equation or bucket models)", which "often require detailed parameterization". Anomalous (non-Fickian) redistribution through heavy-tailed waiting times represents "the trapping effect of water caused by soil heterogeneity". It is a recent multi-layer stochastic, but non-threshold, extension. — [Bovier2025](../../awr.md), Introduction, Discussion
- **Assouline & Or (2014)**, *Water Resour. Res.* 50(6):4787–4802: FC has been "fraught with ambiguities and inconsistencies since its inception". They propose a static criterion based on a soil-intrinsic characteristic length (from the drainable pore-size distribution), marking loss of hydraulic continuity at FC, and extend it to a dynamic criterion for internal drainage. — [EGU 2015 abstract and related summaries](https://meetingorganizer.copernicus.org/EGU2015/EGU2015-1826.pdf); [UKY record of an Oxisol re-examination](https://scholars.uky.edu/en/publications/reexamination-of-the-field-capacity-concept-in-a-brazilian-oxisol/)
- **De Jong van Lier & Wendroth (2016), Brazilian Oxisol:** a 1 mm/d flux criterion placed FC at about −0.55 m pressure head (about −5.4 kPa), far wetter than −33 kPa. — [UKY Scholars record](https://scholars.uky.edu/en/publications/reexamination-of-the-field-capacity-concept-in-a-brazilian-oxisol/) (search snippet)
- **Twarakavi, Sakai & Šimůnek (2009)**, "An objective analysis of the dynamic nature of field capacity", *Water Resour. Res.* 45, doi:10.1029/2009WR007944. As summarized by Romano et al. (2011), it found that determining FC from "pre-fixed points of the water retention curve is inaccurate". — [EarthRef](https://earthref.org/ERR/125082); [Romano et al. 2011, HESS 15:3877](https://hess.copernicus.org/articles/15/3877/2011/hess-15-3877-2011.pdf)
- **Flux-based FC (1999, ASCE J. Geotech. Geoenviron. Eng. 125(7):595):** "values between 10⁻⁶ and 10⁻⁸ cm/s were considered as negligible flux", and the choice produces significant differences in available water capacity. — [ASCE](https://ascelibrary.com/doi/10.1061/%28ASCE%291090-0241%281999%29125%3A7%28595%29)
- **Romano et al. (2011)**, "Parameterization of a bucket model for soil-vegetation-atmosphere modeling under seasonal climatic regimes", *HESS* 15:3877. θ_fc "is a key parameter of a bucket-type approach as it represents a threshold water content that controls the processes of surface runoff generation and drainage". Better agreement with the Richards-based SWAP model comes from FC determined by the Romano & Santini (2002) drainage method. They extend Guswa (2002) to seasonal regimes. — [HESS](https://hess.copernicus.org/articles/15/3877/2011/hess-15-3877-2011.pdf); [HESSD preprint](https://hess.copernicus.org/preprints/8/5083/2011/hessd-8-5083-2011.pdf)
- **"Parameterizing field capacity as the upper limit of available water in bucket-type hydrological models"** (*Comput. Electron. Agric.*, 2022): questions the reference drainage flux. FC should not be characterized solely by a drainage time, since time-to-FC depends on soil properties, initial water content and soil depth. — [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0168169922001181) (abstract/snippet)
- **Bassiouni et al. (2018)**, HESS: in Laio-type inversions, FC and wilting point "don't match conventional definitions because the model simplifies soil water loss", so they are typically fitted rather than taken from the literature. The later Bassiouni et al. (2020, GRL) inferred loss-function thresholds from satellite soil moisture by MCMC. — [HESS 2018](https://hess.copernicus.org/articles/22/3229/2018/hess-22-3229-2018.pdf); [GRL 2020](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2020GL087077) (search snippets)
- **Pelak & Porporato (2019):** FC "may be defined as the value of s at which the hydraulic conductivity becomes negligible compared to the maximum daily evapotranspiration rate (Rodríguez-Iturbe and Porporato, 2004)". They make K(s,t) time-dependent through an evolving pore-size distribution (tillage and consolidation; Eq. 11), so the flux-defined s_fc evolves in time. — [Pelak2019](../../1-s2.0-S0309170819303124-main.md), §3 Eq. 11
- **Seasonal extensions:** Feng et al. (2012, WRR) and Feng et al. (2015, *Proc. R. Soc. A*, "Stochastic soil water balance under seasonal climates") extend the stochastic balance to seasonal (non-steady) climates. — [Feng 2012 (Wiley)](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2011WR011263); [Feng 2015 (PubMed)](https://pubmed.ncbi.nlm.nih.gov/25663808)

### Inferences
- **[Calc], potentials at the tabulated s_fc.** Evaluating Laio's Clapp–Hornberger curves (geometric-mean Ψ̄_s) at the Table 1 s_fc gives about −24 kPa (sand), −3 kPa (loamy sand), −12 kPa (sandy loam), −15 kPa (loam) and −2 kPa (clay). At s*, the corresponding potentials are −29 to −31 kPa. The conventional −33 kPa point gives s ≈ 0.32, 0.30, 0.455, 0.56 and 0.78 for those textures, essentially equal to Laio's s*.
- In the Laio parameterization, the "agronomic FC" (−33 kPa) therefore coincides with the onset of stomatal closure s*, while the model's s_fc is wetter by about 0.02–0.2 in s.
- If modelers substitute a −33 kPa FC for s_fc, the well-watered plateau (s* to s_fc) nearly collapses. Leakage would then start at s ≈ s*. Per the Q2 table, this raises leakage and lowers ET and storage relative to the flux-defined value.
- Non-instantaneous drainage is already present in Laio's exponential L(s) and in Rigby & Porporato's power-law percolation. The minimalist s_1 models are the main "instantaneous" target of criticism. Rigby & Porporato's finding that within-storm percolation matters more than Hortonian runoff supports keeping a finite-rate drainage term.

### Gaps
- A study that directly compares stochastic-model outputs using −33 kPa vs. flux-based s_fc was not found.
- No explicit "non-instantaneous drainage parameterization" paper (e.g., a drainage time-scale replacing the s_1 threshold) within the stochastic lineage was found in the accessible sources. The Porporato & Yin (2022) *Ecohydrology* book (cited in [Bovier2025](../../awr.md)) may cover it but was not accessed.
- An unverified snippet claimed that 10–50% of transpired water is taken up at water contents above FC. Its source could not be identified, so it is excluded from the findings.

---

## 5. How is s_fc typically parameterized (values by texture)?

### Takeaway
The standard reference values come from Laio et al. (2001), Table 1: s_fc = 0.35 (sand), 0.52 (loamy sand), 0.56 (sandy loam), 0.65 (loam) and ≈1 (clay). These are relative saturations, with n = 0.35, 0.42, 0.43, 0.45 and 0.50. They are computed from Clapp–Hornberger K = K_s s^c with K(s_fc) = 0.05 cm/d. Recomputing shows the loamy-sand, sandy-loam and loam values are reproducible, but the sand and clay values are not consistent with the tabulated K_s. Other studies use s_1 ≈ 0.6 (minimalist), a water-table-dependent s_e, or fit s_fc by inversion.

### Cited Findings
**Laio et al. (2001), Table 1**

Ψ̄_s is the geometric mean, and the clay K_s is given as < 10 cm/d.

| Texture | Ψ̄_s (MPa) | b | c | K_s (cm/d) | n | β | s_h | s_w | s* | s_fc |
|---|---|---|---|---|---|---|---|---|---|---|
| Sand | −0.34×10⁻³ | 4.05 | 11.1 | > 200 | 0.35 | 12.1 | 0.08 | 0.11 | 0.33 | 0.35 |
| Loamy sand | −0.17×10⁻³ | 4.38 | 11.7 | ≈ 100 | 0.42 | 12.7 | 0.08 | 0.11 | 0.31 | 0.52 |
| Sandy loam | −0.70×10⁻³ | 4.90 | 12.8 | ≈ 80 | 0.43 | 13.8 | 0.14 | 0.18 | 0.46 | 0.56 |
| Loam | −1.43×10⁻³ | 5.39 | 13.8 | ≈ 20 | 0.45 | 14.8 | 0.19 | 0.24 | 0.57 | 0.65 |
| Clay | −1.82×10⁻³ | 11.4 | 25.8 | < 10 | 0.50 | 26.8 | 0.47 | 0.52 | 0.78 | ≈ 1 |

s_h, s_w and s* correspond to −10, −3 and −0.03 MPa. Data sources are Clapp & Hornberger (1978), Dingman, Lai & Katul (2000) and Cosby et al. (1984). The model uses the geometric mean of Ψ̄_s because the arithmetic mean "would yield unrealistically high values of soil moisture". — [Laio2001](../../1-s2.0-S0309170801000057-main.md), Table 1, §2.5

**Other parameterizations**
- Laio (2001) typical climate and vegetation inputs: E_max = 0.45 cm/d, E_w = 0.01 cm/d, α = 1.5–2 cm, λ = 0.1–0.5 d⁻¹, Z_r = 30–90 cm. — [Laio2001](../../1-s2.0-S0309170801000057-main.md), Figs. 7–10
- Minimalist model (Daly & Porporato 2006): s_1 = 0.6, s_w = 0.047, n = 0.373, Z_r = 300 mm. — [Daly2006](<../../Water Resources Research - 2006 - Daly - Impact of hydroclimatic fluctuations on the soil water balance.md>), Fig. 5 caption
- Rigby & Porporato (2006): no s_fc. Brooks–Corey parameters are m = 0.5, ψ_s = −500 mm and k_s = 50, 200 or 2000 mm/d. — [Rigby2006](../../hess-10-861-2006.md), Table 1
- Alizadeh & Mousavi (2013): s measured from residual (wilting) content, s = (θ − θ_r)/n, so s_s = 1 − θ_r/n. FC is s_e = ((Z − Z_r)/h_b)^{−1/b} − θ_r/n, a function of mean water-table depth Z and Brooks–Corey/Campbell parameters. Average values in the sensitivity runs: s* = 0.22, n = 0.35, K_s = 250 cm/d, Z = 300 cm, Z_r = 80 cm. — [Alizadeh2013](../../alizadeh2013.md), ¶22, ¶28, Table 2 footnote
- Inversion approach: a Loess Plateau application calibrated six Laio-model parameters by genetic algorithm, including s_h, s_w and s*, and recommended sampling intervals of 10 days or less. — [Water 9(5):354 (2017)](https://doi.org/10.3390/w9050354) (search snippet). Bassiouni et al. (2018) note that FC is usually fitted rather than taken from literature. — [HESS 2018](https://hess.copernicus.org/articles/22/3229/2018/hess-22-3229-2018.pdf)

### Inferences
**[Calc] consistency check of Table 1**

Inverting K_s s_fc^c = 0.05 cm/d gives s_fc = 0.522 (loamy sand), 0.562 (sandy loam) and 0.648 (loam), matching the table. For sand, K_s = 200 gives 0.474, not 0.35; reaching 0.35 requires K_s ≈ 5,700 cm/d. For clay, K_s = 10 gives 0.81; the tabulated ≈ 1 implies K_s ≲ 0.05 cm/d. The sand and clay entries are therefore either based on unstated K_s values or are rounded or judgmental. They should be used with caution.

**Other observations on Table 1**
- β = 2b + 4 = c + 1 holds for all rows.
- s_fc − s* is the width of the "well-watered, non-draining" plateau. It is 0.02 (sand), 0.21 (loamy sand), 0.10 (sandy loam), 0.08 (loam) and about 0.22 (clay). For sand the plateau nearly vanishes, which makes sandy soils especially sensitive to the s_fc choice.
- In volumetric terms (θ = n·s), Laio's s_fc corresponds to θ_fc ≈ 0.12 (sand), 0.22 (loamy sand), 0.24 (sandy loam), 0.29 (loam) and about 0.50 (clay).

### Gaps
- The Rodriguez-Iturbe & Porporato (2004) book's soil-parameter tables (which may revise Laio's Table 1) were not accessible.
- No compiled global dataset of fitted s_fc values from stochastic-model inversions was found.
