# Field Capacity (FC): Concept, Definitions, and Scientific Debate

Note on sourcing: outbound web fetching was blocked in this session (the proxy refused connections to Wiley, ScienceDirect, SciELO, ASCE and others). The web claims below come from search-engine abstracts and snippets of the cited pages, not full texts. The local repo papers were read in full. Where only a secondary source supported a claim, that is said. Exact formulas that could not be checked against a primary source are listed under Gaps.

Local repo papers are cited as `[filename — short title](path)`.

---

## 1. Historical origin and classic (time/drainage-based) definitions

### Takeaway
FC grew out of Briggs & McLane's laboratory "moisture equivalent" (1907/1910; water retained against 1,000 g in a centrifuge). Veihmeyer & Hendrickson (1931) replaced it with a field-based, qualitative definition: water held after excess gravitational water has drained and downward movement has "materially decreased". Glossaries later put this into practice as "2–3 days after wetting, when free drainage is negligible". Richards & Weaver (1944) and Colman (1947) then tied it to a fixed potential of −1/3 bar (−33 kPa).

### Cited Findings
- **Moisture equivalent (Briggs & McLane).** This is the water a soil keeps against a centrifugal force 1,000 times gravity, applied for 30 minutes, measured on saturated, sieved and packed samples. Sources give the date as 1907 (USDA Bureau of Soils bulletin) or 1910 (an Agronomy Journal paper). — [Wikipedia: Moisture equivalent](https://en.wikipedia.org/wiki/Moisture_equivalent); [Frontiers in Earth Science 2017](https://www.frontiersin.org/journals/earth-science/articles/10.3389/feart.2017.00025/full); [Twarakavi et al. 2009, WRR](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2009wr007944)
- **Veihmeyer & Hendrickson (1931).** In "The moisture equivalent as a measure of the field capacity of soils" (Soil Sci. 32:181–193/194), FC is "the amount of water held in the soil after the excess gravitational water has drained away and after the rate of downward movement of water has materially decreased". They introduced the field concept because the moisture equivalent fit field soils and coarse soils poorly. — [Twarakavi et al. 2009, WRR](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2009wr007944); [Assouline & Or 2014, WRR](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1002/2014WR015475)
- **Date conflict.** Wikipedia-derived pages say Veihmeyer & Hendrickson proposed the concept "in 1949". The primary citation supports 1931. The 1949 paper on field methods (reportedly Soil Sci. 68:75–94) is confirmed only by a blog-type secondary source. — [Wikipedia: Field capacity](https://en.wikipedia.org/wiki/Field_capacity)
- **Richards & Weaver (1944).** In "Moisture retention by some irrigated soils as related to soil moisture tension" (J. Agric. Res. 69:215–235), they found that water held at −33 kPa (−0.33 bar) "correlate[s] closely with field capacity", with −10 kPa for sandy soils. Colman (1947) then proposed the arbitrary value ψFC = −1/3 bar for all soils. — [Wikipedia: Field capacity](https://en.wikipedia.org/wiki/Field_capacity); [Assouline & Or 2014 (via search snippet)](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1002/2014WR015475)
- **SSSA glossary.** "Field capacity, in situ (field water capacity)" is "the water content, on a mass or volume basis, remaining in a soil 2 or 3 days after having been wetted with water and after free drainage is negligible." — [SSSA Glossary of Soil Science Terms](https://www.soils.org/publications/soils-glossary/browse/f?q=publications%2Fsoils-glossary%2Fbrowse%2Ff%2F)
- **USDA soil survey glossary.** FC is "the content of water remaining in a soil soon after having been soaked by rain or irrigation and after free drainage becomes negligible, generally 2 to 3 days". — [NRCS Glossary of Terms Used in Soil Survey and Soil Classification](https://www.nrcs.usda.gov/sites/default/files/2022-08/A_Glossary_of_Terms_Used_in_Soil_Survey_and_Classification.pdf)
- **Main critique of the classic definition.** It is qualitative: "excess drainage" and "materially decreased" are vague, so operational estimates rely on empirical rules. — [Twarakavi et al. 2009](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2009wr007944). The Veihmeyer & Hendrickson and 1984 SSSA glossary versions are both described as imprecise about what counts as a "negligible" drainage rate. — [Nachabe 1998, J. Irrig. Drain. Eng. (abstract page)](https://ascelibrary.com/doi/10.1061/%28ASCE%290733-9437%281998%29124%3A4%28230%29)
- **Cassel & Nielsen (1986), "Field Capacity and Available Water Capacity".** This chapter in *Methods of Soil Analysis, Part 1* (2nd ed.) is the standard methods reference and is widely cited as questioning the concept itself. — [Cassel & Nielsen 1986, SSSA Book Series](https://acsess.onlinelibrary.wiley.com/doi/abs/10.2136/sssabookser5.1.2ed.c36); [Embrapa/Brazilian study citing it](https://www.alice.cnptia.embrapa.br/alice/bitstream/doc/1051668/1/2016026.pdf)
- **Repo usage of the classic time-based definition.**
  - Liu et al. define FC as "the amount of water the soil retains after excess gravitational water has drained, and the downward movement slows significantly". They describe it as the upper limit of plant-available water, "typically measured 24–48 h after heavy rainfall or irrigation". FC was measured in the field after natural rain events of more than 80 mm, as the mean of daily sensor values 24–48 h later. Note: the file is named `_2018` but is *Agronomy* 2025, 15, 1973. — [agronomy_hydrus1d_2018.md — Liu et al., "Spatiotemporal Simulation of Soil Moisture in Typical Ecosystems of Northern China… HYDRUS-1D"](/home/user/cavargar/fc_modeling/agronomy_hydrus1d_2018.md)
  - Bean et al. (2018) describe θFC as "the amount of water the soil can hold after gravity losses have occurred and before ET losses have started". For their sandy, well-drained Florida soils they took FC as reached "after one night of drainage". — [field_capacity_volumetric_water_content.md — Bean, Huffaker & Migliaccio 2018, "Estimating Field Capacity from Volumetric Soil Water Content Time Series Using Automated Processing Algorithms", Vadose Zone J. 17:180073](/home/user/cavargar/fc_modeling/field_capacity_volumetric_water_content.md)

### Inferences
- The concept has run through three stages: a laboratory centrifuge proxy (1907–1910), a field drainage-time concept (1931), and a fixed pressure-head proxy (1944–1947 onward). Each step traded physical meaning for ease of measurement. The flux-based definitions of 1998–2014 (Section 3) return to the drainage-rate idea of 1931 but make it quantitative.
- Practical drainage times vary widely in the repo papers alone: one night in Bean et al. (sands), 24–48 h in Liu et al., and 2–3 days in the glossaries. This is the time-dependence that Nachabe (1998) criticised.

### Gaps
- The full texts of Briggs & McLane (1907/1910), Veihmeyer & Hendrickson (1931, 1949) and Colman (1947) could not be retrieved. The quotes come from later papers.
- Whether Veihmeyer & Hendrickson 1949 is "Methods of measuring field capacity and permanent wilting percentage of soils" (Soil Sci. 68:75–94) could not be confirmed from an authoritative source.

---

## 2. Static matric-potential definitions (−5, −10, −33 kPa) and their critiques

### Takeaway
FC is most often approximated as θ at a fixed matric potential:
- −33 kPa (1/3 bar) as the international and USDA default
- −10 kPa for sandy or coarse soils
- −5 kPa in the UK (Hall et al. 1977), with −10 kPa for UK sands
- −6 kPa or −1 m used in some Brazilian and European work

These values come from empirical correlation, not physics. Recent field data (2017–2024) show that −33 kPa systematically underestimates in-situ FC, with typical field values near −6 to −10 kPa.

### Cited Findings
- **Textural rule.** −10 kPa for coarse-textured soils and −33 kPa for medium- and fine-textured soils, attributed to Cassel & Nielsen (1986). There is "not yet a consensus on the correct tension associated with field capacity for each soil type". — [Brazilian Arenosol/Ferralsol study, An. Acad. Bras. Ciênc.](https://www.scielo.br/j/aabc/a/dKBrCNWbjNWMGRxb63RzBYR/?lang=en); [SDSU Extension](https://extension.sdstate.edu/how-soil-holds-water)
- **In-situ FC in Brazilian Arenosols and Ferralsols** fell between the −10 and −33 kPa laboratory values, which suggests the true potential varies between soils. — [scielo.br/aabc](https://www.scielo.br/j/aabc/a/dKBrCNWbjNWMGRxb63RzBYR/?lang=en)
- **Status of −33 kPa.** "In the most widely used international standards" the soil is considered at FC when water potential reaches −33 kPa. — [ScienceDirect Topics: Permanent Wilting Point](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/permanent-wilting-point); [Springer Encyclopedia of Agrophysics, "Field Water Capacity"](https://link.springer.com/rwe/10.1007/978-90-481-3585-1_58)
- **Assouline & Or (2014)** note that −1/3 bar became "the de facto standard definition of FC despite inherent inconsistencies", citing Kirkham (2005). — [Assouline & Or 2014 (snippet)](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1002/2014WR015475); [ScienceDirect Topics: Field Capacity](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/field-capacity)
- **UK convention (−5 kPa).** Hall et al. (1977), Soil Survey of England and Wales Technical Monograph No. 9 ("Water Retention, Porosity and Density of Field Soils", 261 profiles), define the water held against gravity at 5 kPa suction (10 kPa for sandy soils). This is the basis for air capacity and available water. Scottish national AWC maps use the same 5 kPa FC. — [Welsh Government water-storage-capacity scoping report](https://www.gov.wales/sites/default/files/publications/2021-04/water-storage-capacity-soils-scoping-report.pdf); [TRID record](https://trid.trb.org/View/81676); [data.gov.uk AWC Scotland](https://www.data.gov.uk/dataset/3ad227a9-0ae9-4049-ad81-f278c0a1f0c8/available-water-capacity-scotland-wms)
- **Range of static heads in Brazilian/European practice.** FC is "often estimated from a static pressure head, commonly −3.3 m, −1 m or −0.6 m" (≈ −33, −10, −6 kPa). — [de Jong van Lier 2017, Agric. Water Manage. 193:214–220](https://ideas.repec.org/a/eee/agiwat/v193y2017icp214-220.html). Turek et al. (2019) tested static FC at heads of 0.6, 1 and 3.3 m and at the retention-curve inflection point. — [Turek et al. 2019, Eur. J. Soil Sci. 70(2):278–290](https://bsssjournals.onlinelibrary.wiley.com/doi/abs/10.1111/ejss.12747)
- **Recent evidence (2024).** Krueger & Ochsner (2024), SSSAJ 88(5):1678–1690, used automated time-series FC at 118 Oklahoma Mesonet sites. Both thresholds underestimated FC: −10 kPa produced a modest low bias and −33 kPa a much larger one. The optimal median matric potentials at FC were about −7.2 to −7.6 kPa at 5, 25 and 60 cm depth. — [Krueger & Ochsner 2024, SSSAJ](https://acsess.onlinelibrary.wiley.com/doi/10.1002/saj2.20733)
- **Benchmark heads are inaccurate.** Twarakavi et al. (2009) report that using benchmark pressure heads to estimate FC from the retention curve gives inaccurate results compared with a flux-based definition. — [Twarakavi et al. 2009 (PC-Progress PDF)](https://www.pc-progress.com/Documents/Jirka/Twarakavi_et_al_WRR_2009_Field_Capacity.pdf)
- **Teaching texts.** FC "is often incorrectly considered a property of the soil" and "there is not any one matric potential value which universally represents field capacity". — [Oklahoma State open textbook "Rain or Shine", §8.3 Field Capacity](https://open.library.okstate.edu/rainorshine/chapter/8-3-field-capacity/)
- **Repo usage of static potentials.** Laio et al. (2001) fix the other characteristic points by potential:
  - hygroscopic point s_h at Ψ = −10 MPa
  - wilting point s_w at −3 MPa
  - stomatal-closure point s* at −0.03 MPa (−30 kPa)

  They deliberately do *not* define s_fc by potential (see Section 3). In their framework the −30 kPa point s* plays a different role (onset of plant stress). — [1-s2.0-S0309170801000057-main.md — Laio, Porporato, Ridolfi & Rodriguez-Iturbe 2001, "Plants in water-controlled ecosystems… II. Probabilistic soil moisture dynamics", Adv. Water Resour.](/home/user/cavargar/fc_modeling/1-s2.0-S0309170801000057-main.md)

### Inferences
- A mismatch is possible when parameterising models: −33 kPa (Richards & Weaver's correlation, chosen for irrigated western-US soils) is often applied to sands and structured soils, where field evidence points to −5 to −10 kPa. Using −33 kPa then underestimates FC and the upper limit of plant-available water (consistent with Krueger & Ochsner 2024 and Turek et al. 2022).
- Choosing −5, −10 or −33 kPa is partly a regional institutional convention (UK, US/international, Brazil) as much as a texture rule. This should be stated when comparing FC values across datasets.

### Gaps
- I could not access the original text of the Cassel & Nielsen (1986) chapter to quote its texture rule and critique directly. The attribution of the −10/−33 kPa rule to them comes from secondary sources.
- I found no authoritative source explaining the physical basis, if any, for −5 kPa in the UK beyond Hall et al.'s operational choice.

---

## 3. Flux-based and dynamic definitions

### Takeaway
Since the late 1990s, FC has been redefined as the water content at which internal drainage flux falls to a chosen "negligible" value. Published thresholds span about four orders of magnitude, from about 0.005 to 4 mm d⁻¹ (Meyer & Gee 1999; Nachabe 1998; Twarakavi et al. 2009; Turek et al. 2022; Chen et al. 2024). Assouline & Or (2014) instead proposed an intrinsic static criterion: a characteristic length from the drainable pore-size distribution, linked to the loss of liquid-phase continuity near the retention-curve inflection. They paired it with a dynamic time-to-FC criterion.

### Cited Findings
- **Nachabe (1998)**, "Refining the Definition of Field Capacity in the Literature", J. Irrig. Drain. Eng. 124(4):230–232.
  - FC should be tied to drainage flux, not drainage time, because the time to reach FC depends on initial water content and wetting depth.
  - Proposed formula: Θfc = (qfc/Ks)^(1/n), with qfc = 0.05 mm d⁻¹. Θfc is normalized water content and n is a conductivity-curve exponent.
  - The result is "close to the water content at 1/3 bar matric potential for all soils".

  — [ASCE abstract page](https://ascelibrary.com/doi/10.1061/%28ASCE%290733-9437%281998%29124%3A4%28230%29)
- **Meyer & Gee (1999)**, "Flux-Based Estimation of Field Capacity", J. Geotech. Geoenviron. Eng. 125(7):595–599.
  - FC is the water content at a negligible drainage flux under unit gradient, read from the K(θ) curve. "Negligible" was taken as about 10⁻⁶ to 10⁻⁸ cm s⁻¹.
  - Coshocton (Ohio) lysimeter data gave FC at a flux of about 3 × 10⁻⁷ cm s⁻¹.
  - In HELP-model waste-cover water budgets, the choice of FC changed available water capacity. At an arid site, drainage decreased by a factor of 4 (from 25 to 6 mm yr⁻¹).

  — [ASCE](https://ascelibrary.com/doi/10.1061/%28ASCE%291090-0241%281999%29125%3A7%28595%29); [PNNL record](https://www.pnnl.gov/publications/flux-based-estimation-field-capacity)
- **Twarakavi, Sakai & Šimůnek (2009)**, "An objective analysis of the dynamic nature of field capacity", WRR 45, W10410, doi:10.1029/2009WR007944.
  - Free drainage was simulated with the Richards equation and van Genuchten–Mualem hydraulic functions.
  - FC is the water content at which profile drainage under natural conditions becomes negligible. The default qfc is 0.01 cm d⁻¹ (0.1 mm d⁻¹, after Dirksen & Matula 1994). Sensitivity was tested at 0.001 and 0.1 cm d⁻¹ (the latter per Meyer & Gee).
  - They derived an empirical closed-form relationship for effective saturation at FC, S_fc = (θfc − θr)/(θs − θr), as a function of the van Genuchten n and Ks (cm d⁻¹ only).
  - Benchmark-pressure-head estimates were found to be inaccurate.
  - Twarakavi's FC is implemented in hydrological model codes. The mHM parameterisation routine takes Ks, θs and n as inputs and treats a drainage flux of 0.01 cm d⁻¹ (stated in the code as "0.01 cm/d == 1 mm/d") as cessation of drainage.

  — [Wiley](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2009WR007944); [PC-Progress PDF](https://www.pc-progress.com/Documents/Jirka/Twarakavi_et_al_WRR_2009_Field_Capacity.pdf); [mHM documentation, mo_mpr_soilmoist](https://mhm.pages.ufz.de/mhm/stable/namespacemo__mpr__soilmoist.html)
  - Unit discrepancy: 0.01 cm d⁻¹ is 0.1 mm d⁻¹, not 1 mm d⁻¹. The mHM code comment as reported appears to be wrong by a factor of 10, or the snippet was garbled.
  - A 2025 WRR paper quotes the Twarakavi transfer function in a different algebraic form, θfc = θs·exp(γ1·(γ2 + log Ks)·n). — [Kholis et al. 2025, WRR](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2024WR039625)
- **Range of critical fluxes.** Critical drainage fluxes for estimating FC in the literature "vary from 0.001 to 0.1 cm d⁻¹ for different soil textures". — [Chen et al. 2024, Geoderma 449:117000](https://www.sciencedirect.com/science/article/pii/S0016706124002295)
- **Turek, de Jong van Lier & Armindo (2022)**, Comput. Electron. Agric. 194:106801.
  - Flux thresholds at 0.6 m depth of 1, 2 and 4 mm d⁻¹ were tested, described as "commonly used thresholds".
  - With common soil-based FC values, available water was underestimated by up to 60%.

  — [ADS abstract](https://ui.adsabs.harvard.edu/abs/2022CEAgr.19406801T/abstract); [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0168169922001181)
- **Turek et al. (2019)** compared static FC (heads of 0.6/1/3.3 m and the inflection point θi), the Assouline & Or model, and four dynamic-criterion equations from the literature. For all soils the largest FC came from setting FC = θi (inflection point). — [Turek et al. 2019, EJSS](https://bsssjournals.onlinelibrary.wiley.com/doi/abs/10.1111/ejss.12747)
- **Relative-drainage criterion (2024).** Chen et al. (2024) defined a relative drainage rate δ (fraction of storage lost per day). A critical δ of 1% d⁻¹ gave reliable FC in both uniform and layered (loam over buried sand) profiles. They also gave an empirical FC equation in terms of the sand layer's burial depth and thickness. — [Chen et al. 2024, Geoderma](https://www.sciencedirect.com/science/article/pii/S0016706124002295)
- **Assouline & Or (2014)**, "The concept of field capacity revisited: Defining intrinsic static and dynamic criteria for soil internal drainage dynamics", WRR 50:4787–4802, doi:10.1002/2014WR015475.
  - Working hypothesis: reaching "near equilibrium hydration status with a significantly diminished internal drainage is associated with the disruption of hydraulic and liquid phase continuity within the draining soil body".
  - Static criterion: an intrinsic characteristic length, a matric potential derived from the drainable pore-size distribution. It uses the Lehmann et al. (2008) linearization of the retention curve, with Lc = ψFC − ψa (ψa = air-entry value).
  - Dynamic criterion: an analytical internal-drainage model (Youngs & Aggelides 1976) with a rigorously derived effective conductivity of the draining zone, giving the time to reach FC.
  - Applied to 23 soils (sand to silty clay loam) with van Genuchten–Mualem parameters.
  - Assouline (2021) reports that time to FC is inversely proportional to Ks. A secondary summary links the inflection point to "loss of hydraulic continuity and thereby a sudden decrease in soil drainage rate".

  — [Wiley abstract](https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1002/2014WR015475); [ResearchGate record](https://www.researchgate.net/publication/262574122_The_concept_of_field_capacity_revisited_Defining_intrinsic_static_and_dynamic_criteria_for_soil_internal_drainage_dynamics); [Assouline 2021 WRR review](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2021WR031026)
  - Contested reading: an EGU 2015 abstract states its own conclusions conflict with Assouline & Or (2014), "whose proposal is not related with the flux- or time based concept of field capacity". — [EGU2015-1826](https://meetingorganizer.copernicus.org/EGU2015/EGU2015-1826.pdf)
- **Kirkham's position.** Kirkham's *Principles of Soil and Plant Water Relations* (2005) has a chapter "Field Capacity, Wilting Point, Available Water, and the Nonlimiting Water Range". Secondary sources attribute to this school the view that FC "is not a unique value but is rather expressed as a range of values". It is influenced by previous water content, texture, structure, clay type, organic matter, water table, impeding layers and ET. — [ScienceDirect Topics: Field Capacity](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/field-capacity); [Andabili 2025, Irrig. Drain.](https://onlinelibrary.wiley.com/doi/full/10.1002/ird.3032)
- **Model-based flux/ET-ratio definitions in the repo.**
  - Laio et al. (2001) define s_fc operationally as "the value of soil moisture at which the hydraulic conductivity becomes negligible (here 10%) compared to the maximum daily evapotranspiration losses E_max (for this purpose assumed to be 0.5 cm/d)". That is, K(s_fc) = 0.05 cm d⁻¹ = 0.5 mm d⁻¹, computed from the Clapp–Hornberger power law K = Ks s^c (c = 2b + 3). The table footnote states that s_fc "is the s level at which the leakage losses become negligible with respect to the evapotranspiration losses". They cite Hillel (1998) for FC's "physical and practical relevance". — [1-s2.0-S0309170801000057-main.md — Laio et al. 2001](/home/user/cavargar/fc_modeling/1-s2.0-S0309170801000057-main.md)
  - The soil pore-size-dynamics paper restates the same definition, citing Rodríguez-Iturbe & Porporato (2004): FC "may be defined as the value of s at which the hydraulic conductivity becomes negligible compared to the maximum daily evapotranspiration rate". — [1-s2.0-S0309170819303124-main.md — "Dynamic evolution of the soil pore size distribution and its connection to soil management and biogeochemical processes", Adv. Water Resour.](/home/user/cavargar/fc_modeling/1-s2.0-S0309170819303124-main.md)
  - Bean et al. (2018) give a data-driven dynamic estimator. After a wetting peak θB, overnight (no-ET) drying follows θ(t) = (θB − θFC) e^(−λt) + θFC, with drainage rate proportional to water above FC (after Hillel 1998), so θFC is the asymptote. θFC was estimated three ways: by regressing θ on 1/t to t → ∞ (SWDP-R), by the first "knee" where dθ/dt drops sharply (SWDP-K), and by findpeaks plateaus (R-FP). In one example the knee lay at θ ≈ 0.33–0.36 but overnight drainage ceased only below 0.30. SWDP-K tended to overestimate and SWDP-R to underestimate expert values. — [field_capacity_volumetric_water_content.md — Bean et al. 2018](/home/user/cavargar/fc_modeling/field_capacity_volumetric_water_content.md)
- **Other recent field-data methods.** Oklahoma State Extension's approach to determining FC from continuous sensor data, and Kumar et al. (2023), "A methodology to optimize site-specific field capacity and irrigation thresholds", Agric. Water Manage. 286:108385. — [OSU fact sheet](https://extension.okstate.edu/fact-sheets/determining-field-capacity-using-continuous-soil-water-content-data); [Kumar et al. 2023](https://www.sciencedirect.com/science/article/pii/S0378377423002500)

### Inferences
- In common units (my conversions, 1 cm s⁻¹ = 8.64 × 10⁵ mm d⁻¹), the "negligible flux" thresholds are:

  | Source | Threshold | mm d⁻¹ |
  |---|---|---|
  | Meyer & Gee (1999), range | 10⁻⁶ to 10⁻⁸ cm s⁻¹ | ≈ 0.86 to 0.0086 |
  | Meyer & Gee (1999), Coshocton | 3 × 10⁻⁷ cm s⁻¹ | ≈ 0.26 |
  | Nachabe (1998) | 0.05 mm d⁻¹ | 0.05 |
  | Twarakavi et al. (2009) | 0.001 / 0.01 / 0.1 cm d⁻¹ | 0.01 / 0.1 / 1 |
  | Laio et al. (2001) | 10% of E_max | 0.5 |
  | Turek et al. (2022) | 1–4 mm d⁻¹ | 1–4 |
  | Chen et al. (2024) | 1% of storage per day | storage-dependent, not absolute |

  A roughly 500-fold range in the threshold translates into large θFC differences, especially for coarse soils with steep K(θ).
- The ecohydrological (Laio / Rodríguez-Iturbe & Porporato) definition compares K to E_max, not to an absolute drainage rate. FC is therefore partly a climate and vegetation parameter in these bucket models: a higher E_max lowers s_fc for the same soil.
- Assouline & Or's approach is the main attempt to recover an *intrinsic* soil property from retention-curve shape. Flux-based approaches accept that FC is a conventional threshold on a continuous drainage process.

### Gaps
- **Exact Twarakavi et al. (2009) formula.** The snippets were garbled. It is widely reproduced (from memory, unverified here) as θfc = θr + (θs − θr) · n^(−0.60 (2 + log10 Ks)), with Ks in cm d⁻¹. Verify against the PDF (eq. ~10) before quoting.
- Assouline & Or (2014): the exact Lc and ψFC equations, the resulting ψFC values for the 23 soils, and their comparison with −10/−33 kPa could not be retrieved.
- Nachabe (1998): what the exponent n in Θfc = (qfc/Ks)^(1/n) is exactly (e.g., Brooks–Corey/Campbell conductivity exponent) was not confirmed from full text.
- No primary text was found for a "fraction of Ks" threshold beyond Nachabe's qfc/Ks ratio and Laio's ratio to E_max.
- The EGU 2015 objection to Assouline & Or was seen only as a one-line snippet.

---

## 4. Soil property or dynamic state? Layering, water table, evaporation, initial wetting; related terms (DUL)

### Takeaway
The prevailing view in soil physics (Hillel, Kirkham, Cassel & Nielsen) is that FC is a conditional, profile-scale state, not an intrinsic property. It depends on:
- antecedent water content and wetting depth
- layering or impeding horizons
- water-table depth and capillary upflux
- evaporation and root extraction during redistribution
- hysteresis and preferential flow

Assouline & Or (2014) are the main counterpoint, seeking an intrinsic criterion. Crop models use the operational equivalent "drained upper limit" (DUL), measured in the field.

### Cited Findings
- **Hillel-derived textbook statements.** Two points are relevant:
  - "Usually, the wetter the profile is at the outset, the greater is the depth of wetting during infiltration, the slower is the rate of redistribution, and the greater is the apparent field capacity."
  - Impeding layers "inhibit redistribution and increase the apparent field capacity", and "the term 'field capacity' is of questionable value for soils having layers of widely differing hydraulic conductivities".

  FC "is not a unique value, because equilibrium is never reached". — [ScienceDirect Topics: Field Capacity](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/field-capacity); [Tarboton, Rainfall–Runoff Processes, ch. 4](https://hydrology.usu.edu/rrp/pdfs/ch4.pdf)
- **In-situ FC depends on conditions.** In a field, FC "depends upon the initial water content, the depth of wetting before the commencement of redistribution, and the rate of change in water content over time. These conditions are not unique to a given soil." — [Jabro et al., USDA-ARS, "In-Situ Soil-Water Retention and Field…"](https://www.ars.usda.gov/ARSUserFiles/37611/Jabro_235411.pdf)
- **Layering (2023–2024).**
  - A 2023 Agric. Water Manage. paper argues that the usual FC definition "is ambiguous and biased for stratified soil profiles due to the soil water content discontinuity at the layer interfaces". — ["Revisiting the definition of field capacity as a functional parameter in a layered agronomic soil profile beneath irrigated maize", Agric. Water Manage. vol. 284, 2023](https://www.sciencedirect.com/science/article/pii/S0378377423002330)
  - Chen et al. (2024) found that a buried sand interlayer raises FC in the overlying loam. The increase was negatively correlated with burial depth and positively with sand-layer thickness. — [Geoderma 449:117000](https://www.sciencedirect.com/science/article/pii/S0016706124002295)
  - Zettl et al. (2011), "Influence of textural layering on field capacity of coarse soils" (Can. J. Soil Sci. 91:133–147), is cited in the repo for FC varying with depth because of heterogeneity. — [agronomy_hydrus1d_2018.md, ref. 49](/home/user/cavargar/fc_modeling/agronomy_hydrus1d_2018.md)
- **Water table.** Alizadeh & Mousavi (2013) replace a fixed FC with an "effective field capacity", s_e = ((Z − Z_r)/h_b)^(−1/b) − θ_r/n. It depends on water-table depth Z, root depth Z_r, bubbling pressure h_b and the Brooks–Corey b. They call it "the relative soil moisture level at which soil shifts from the drainage behavior to the capillary uptake condition and vice versa". Leakage is zero for s ≤ s_e and linear above (L = Ks (s − s_e)/(s_s − s_e)). Capillary flux tapers to zero at s_e. — [alizadeh2013.md — Alizadeh & Mousavi 2013, "Coupled stochastic soil moisture simulation-optimization model of deficit irrigation", WRR](/home/user/cavargar/fc_modeling/alizadeh2013.md)
- **Antecedent moisture and hysteresis (empirical).** Bean et al. (2018) state: "Although θFC is conventionally assumed to be static, the true values and automated estimates suggest that θFC may have a dynamic range". They attribute this to antecedent θ, preferential flow and probable hysteresis.
  - In turf datasets, FC increased between wetting events by generally < 2.0% d⁻¹ (maximum single-day increase 6.2%) and decreased by typically < 1.5% d⁻¹ (largest decrease 6.8% over 2 d).
  - Lower antecedent θ causes more preferential drainage and a lower FC (citing Merdun & Demirkiran 2008; Hardie et al. 2011).
  - They caution that the methods were tested only on coarse, well-drained soils without shallow water tables, with upflux not considered. Their key point: "Automated approaches needed to leverage temporally dynamic field capacity."

  — [field_capacity_volumetric_water_content.md — Bean et al. 2018](/home/user/cavargar/fc_modeling/field_capacity_volumetric_water_content.md)
- **Spatial variability within a profile.** Liu et al. (Agronomy 2025) measured FC by layer. It was 29.00–40.65% vol in a tea plantation and 22.50–28.55% in grassland (20–100 cm), with significant layer-to-layer differences (LSD, p < 0.05). — [agronomy_hydrus1d_2018.md](/home/user/cavargar/fc_modeling/agronomy_hydrus1d_2018.md)
- **Plant extraction.** "The rate and pattern of extraction of water by plant roots from soil can affect the gradients and flow directions in the profile and modify redistribution." — [ScienceDirect Topics: Field Capacity](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/field-capacity)
- **Drained upper limit (DUL).**
  - In APSIM, "The Drained Upper Limit (DUL) or Field Capacity (FC) of a soil defines the upper limit of the PAWC". It is the water content retained "after gravitational flow becomes negligible". Field determination means wetting a covered plot and monitoring drainage: equilibrium "may be reached after 2–5 days, but on heavy soils this can take weeks". A uniformly drained profile "consistently 'at DUL' is rarely possible". — [APSIM/DNRME 2017 technical note](https://www.apsim.info/wp-content/uploads/2021/01/Methods-for-PAWWRC-estimation_DNRME.pdf); [APSIM soil-description protocol, MethodsX](https://www.sciencedirect.com/science/article/pii/S2215016121003563)
  - DUL as a field-measured FC is credited to Ratliff, Ritchie & Cassel (1983) and Gardner et al. (1984). — [ResearchGate figure/Vertosol study](https://www.researchgate.net/figure/Adjusted-means-of-drained-upper-limit-DUL-and-crop-lower-limit-CLL-values-of-all_fig1_263003738)
- **Comparison of nine approaches (2023).** A comparison of nine FC approaches, including the Assouline & Or model (AO) alongside water-content-based criteria, is indexed under the same AWM vol. 284 (2023) record as the layered-profile paper above. The snippet did not make clear whether it is the same paper. — [IDEAS/AWM 2023](https://ideas.repec.org/a/eee/agiwat/v284y2023ics0378377423002330.html)

### Inferences
- In models FC is best treated as an *effective, boundary-condition-dependent parameter*. Its value depends on profile layering, lower boundary (free drainage vs. water table), the drainage threshold and climate (E_max in Laio-type models). Alizadeh & Mousavi's s_e is an explicit example of a water-table-dependent FC.
- DUL is an operational, in-situ cousin of FC. It folds in profile and layering effects and is therefore not transferable from retention-curve point values.

### Gaps
- No direct quotation was retrieved from Kirkham (2005) stating "FC is not a soil property". The attribution relies on secondary summaries and Assouline & Or's citation of Kirkham.
- I found no quantitative synthesis of how much FC shifts with water-table depth across textures, other than the analytical s_e formula.
- The full text of Ratliff, Ritchie & Cassel (1983, SSSAJ) was not retrieved.

---

## 5. Relation to wilting point, plant-available water, onset of drainage/leakage in models, and the inflection point

### Takeaway
FC is the conventional upper bound of plant-available water (PAW = θFC − θPWP, with PWP usually at −1500 kPa). In bucket and stochastic models it serves as the threshold above which leakage or deep drainage begins. Both roles are contested:
- 10–50% of transpiration can come from water above FC (de Jong van Lier 2017).
- The FC criterion can change simulated available water by up to 60% and drainage by about 4×.

The retention-curve inflection point (Dexter's S, Mueller et al. 2003, Assouline & Or 2014) gives a structural alternative that generally yields higher FC.

### Cited Findings
- **Bucket-model thresholds in Laio et al. (2001)**, ordered s_h < s_w < s* < s_fc < 1:
  - leakage L(s) = 0 for s ≤ s_fc
  - L(s) = Ks/(e^{β(1−s_fc)} − 1)·[e^{β(s−s_fc)} − 1] for s_fc < s ≤ 1, with β = 2b + 4 (≈12 for sand to 26 for clay)
  - ET = E_max on s* < s ≤ s_fc, falling linearly to s_w, then to s_h
  - after a storm, drydown from s_0 ≥ s_fc follows an analytical leakage-plus-ET decay until s_fc, then linear ET decay at rate η = E_max/(nZ_r)
  - mean leakage ⟨L⟩ = nZ_r ∫_{s_fc}^1 L(s)p(s) ds

  Table 1 values (Clapp & Hornberger soils):

  | Soil | s_h | s_w | s* | s_fc | n | b | β | Ks (cm d⁻¹) |
  |---|---|---|---|---|---|---|---|---|
  | Sand | 0.08 | 0.11 | 0.33 | 0.35 | 0.35 | 4.05 | 12.1 | > 200 |
  | Loamy sand | 0.08 | 0.11 | 0.31 | 0.52 | 0.42 | 4.38 | 12.7 | ≈ 100 |
  | Sandy loam | 0.14 | 0.18 | 0.46 | 0.56 | 0.43 | 4.90 | 13.8 | ≈ 80 |
  | Loam | 0.19 | 0.24 | 0.57 | 0.65 | 0.45 | 5.39 | 14.8 | ≈ 20 |
  | Clay | 0.47 | 0.52 | 0.78 | ≈ 1 | 0.50 | 11.4 | 26.8 | < 10 |

  — [1-s2.0-S0309170801000057-main.md — Laio et al. 2001](/home/user/cavargar/fc_modeling/1-s2.0-S0309170801000057-main.md)
- **Daly & Porporato (2006)** use a threshold s_1 "comprised between field capacity and saturation". Runoff and drainage occur instantaneously at the daily scale only for s ≥ s_1 (example s_1 = 0.6, s_w = 0.047, n = 0.373, Z_r = 300 mm), and ET decreases linearly from s_1 to s_w. — [Water Resources Research - 2006 - Daly - Impact of hydroclimatic fluctuations on the soil water balance.md](/home/user/cavargar/fc_modeling/Water%20Resources%20Research%20-%202006%20-%20Daly%20-%20Impact%20of%20hydroclimatic%20fluctuations%20on%20the%20soil%20water%20balance.md)
- **Alizadeh & Mousavi (2013).**
  - Leakage begins at the effective FC s_e (water-table dependent).
  - "Traditional irrigation often entails an application that brings the soil moisture back to the field capacity or a level slightly above it due to salt control considerations."
  - Irrigation triggers are set relative to s* (stomatal closure).

  — [alizadeh2013.md](/home/user/cavargar/fc_modeling/alizadeh2013.md)
- **Other repo models.** Rigby & Porporato (2006) model percolation as k_s s^c with no explicit FC threshold. — [hess-10-861-2006.md — "Simplified stochastic soil-moisture models: a look at infiltration", HESS 10:861](/home/user/cavargar/fc_modeling/hess-10-861-2006.md). Bovier et al. (awr.md, CTRW soil moisture model) cite Laio et al. (2001) as the stochastic-model reference. — [awr.md — "Space-dependent continuous time random walk for soil moisture modeling"](/home/user/cavargar/fc_modeling/awr.md). `2501.01569v1.md` (Gandhi et al., flow-kick vegetation) and `or2000.md` (Or et al. 2000, post-tillage pore evolution) contain no "field capacity" usage per grep.
- **FC as irrigation and PAW bound.**
  - Bean et al.: "efficient irrigation management optimizes θ cycling by maintaining θ between θFC and a minimum acceptable soil water content [MAD]" (USDA-NRCS 2005), and θFC "is a key parameter in hydrologic models used in irrigation scheduling". — [field_capacity_volumetric_water_content.md](/home/user/cavargar/fc_modeling/field_capacity_volumetric_water_content.md)
  - Liu et al.: FC "represents the upper limit of plant-available water". They used measured FC with texture and bulk density as constraints in HYDRUS-1D inverse estimation of van Genuchten parameters (θr, α, n, Ks) for 10 layers (calibration R² ≈ 0.81). — [agronomy_hydrus1d_2018.md](/home/user/cavargar/fc_modeling/agronomy_hydrus1d_2018.md)
- **FC as an upper limit is questioned.** de Jong van Lier (2017), "Field capacity, a valid upper limit of crop available water?" (AWM 193:214–220), finds "a considerable (10–50%) fraction of transpired water is taken up from the soil at water contents above FC", which casts doubt on bucket-type models. — [IDEAS/RePEc](https://ideas.repec.org/a/eee/agiwat/v193y2017icp214-220.html)
- **Sensitivity of available water and drainage to the FC criterion.**
  - Available water was underestimated by up to 60% with common soil-based FC values. — [Turek et al. 2022](https://ui.adsabs.harvard.edu/abs/2022CEAgr.19406801T/abstract)
  - Simulated landfill-cover drainage changed from 25 to 6 mm yr⁻¹ with FC choice. — [Meyer & Gee 1999](https://ascelibrary.com/doi/10.1061/%28ASCE%291090-0241%281999%29125%3A7%28595%29)
  - A flux-based PAW alternative has been developed for tropical soils. — [de Melo et al. 2023, Geoderma 429:116253 (cited in agronomy_hydrus1d_2018.md ref. 48)](/home/user/cavargar/fc_modeling/agronomy_hydrus1d_2018.md); [Flux-based plant water availability in tropical soils from Brazil (2025)](https://link.springer.com/article/10.1007/s44378-025-00066-z)
- **Inflection point.**
  - Mueller et al. (2003) proposed the retention-curve inflection point as corresponding to FC. Later studies found inflection-point FC to be higher than FC at −6, −10 and −33 kPa. — [ResearchGate: "Field capacity estimation from the inflection point…"](https://www.researchgate.net/publication/320094123_FIELD_CAPACITY_ESTIMATION_FROM_THE_INFLECTION_POINT_OF_THE_SOIL_MOISTURE_RETENTION_CURVE); [Pesquisa Agropecuária Tropical study](http://www.scielo.br/j/pat/a/LScSkW9BsXqYgR3LCzR9SKy/?lang=en)
  - Dexter (2004) defined the S index as the slope of gravimetric W vs ln|h| at the inflection point (S = 0.035 as the good/poor soil-quality boundary). — [Revisiting the S-index, RBCS](http://www.scielo.br/j/rbcs/a/D5XpsBSxhxWGM6TPhLWb8Sn/?lang=en)
  - Turek et al. (2019) found θi gave the largest FC of all criteria for all soils tested. — [EJSS](https://bsssjournals.onlinelibrary.wiley.com/doi/abs/10.1111/ejss.12747)
  - Assouline & Or (2014) link the inflection and characteristic length to the loss of liquid continuity, which causes the sharp drop in drainage rate. — [Assouline 2021 review](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2021WR031026)
- **Permanent wilting point convention.** PWP is conventionally θ at −1500 kPa, as reported alongside FC conventions. — [ScienceDirect Topics: Permanent Wilting Point](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/permanent-wilting-point)
  - Note the contrast: Laio et al. (2001) instead use s_w at −3 MPa (−3000 kPa) and s_h at −10 MPa, which are ecophysiological rather than agronomic values. — [Laio et al. 2001](/home/user/cavargar/fc_modeling/1-s2.0-S0309170801000057-main.md)

### Inferences
- In stochastic ecohydrology (Laio, Daly & Porporato, Alizadeh & Mousavi), "field capacity" is fundamentally a *leakage-onset parameter*. It is defined so that K(s_fc) is negligible relative to ET, not by a potential, and it sets the upper boundary of the ET plateau. In clay this pushes s_fc to about 1, effectively eliminating leakage, which shows how strongly the ET-ratio definition depends on Ks.
- Laio's s_fc and s* are very close for sand (0.35 vs 0.33). The "well-watered plateau" can therefore nearly vanish in coarse soils, so model behaviour there is highly sensitive to how s_fc is defined.
- Because the inflection-point FC is higher than −33 kPa FC and closer to the −6 to −10 kPa field-optimal values (Krueger & Ochsner 2024), structural (retention-shape) and empirical (time-series) definitions appear to agree better with each other than either does with −33 kPa. This is a tentative synthesis that needs checking with primary data.

### Gaps
- Quantitative agreement between inflection-point ψ and field FC across textures was not obtained (no full texts).
- de Jong van Lier (2017): the soils, crops and fluxes behind the 10–50% figure were not accessible.

---

## 6. How the repo papers define or use field capacity (summary table)

### Takeaway
The repo papers fall into two camps. The stochastic ecohydrology papers (Laio 2001; Daly & Porporato 2006; Alizadeh & Mousavi 2013; Bovier; the 2019 AWR pore-dynamics paper) define FC as a model threshold where K(s) becomes negligible relative to E_max, or where drainage switches to capillary uptake. The field and sensor papers (Bean et al. 2018; Liu et al. 2025) define FC empirically from post-wetting drainage in sensor time series and note that it varies in time and with depth.

### Cited Findings

| Paper (file) | Definition / role of FC | Quantitative detail |
|---|---|---|
| Laio et al. 2001 — [1-s2.0-S0309170801000057-main.md](/home/user/cavargar/fc_modeling/1-s2.0-S0309170801000057-main.md) | s_fc = s at which K(s) is negligible (10%) vs E_max; leakage zero below s_fc; upper limit of the ET = E_max plateau | E_max = 0.5 cm d⁻¹ → K(s_fc) = 0.05 cm d⁻¹; K = Ks s^c, c = 2b + 3; β = 2b + 4; s_fc = 0.35 (sand) to ≈ 1 (clay) |
| AWR 2019 pore-size dynamics — [1-s2.0-S0309170819303124-main.md](/home/user/cavargar/fc_modeling/1-s2.0-S0309170819303124-main.md) | FC = s where K is negligible vs maximum daily ET (Rodríguez-Iturbe & Porporato 2004); FC changes as the pore-size distribution evolves (K depends on time-varying φ, R_m, b) | K(s,t) from Hagen–Poiseuille, G_e = 1/8 |
| Daly & Porporato 2006 — [WRR 2006 Daly .md](/home/user/cavargar/fc_modeling/Water%20Resources%20Research%20-%202006%20-%20Daly%20-%20Impact%20of%20hydroclimatic%20fluctuations%20on%20the%20soil%20water%20balance.md) | Drainage threshold s_1 "between field capacity and saturation" | s_1 = 0.6 in example |
| Alizadeh & Mousavi 2013 — [alizadeh2013.md](/home/user/cavargar/fc_modeling/alizadeh2013.md) | "Effective field capacity" s_e depends on water-table depth; leakage/upflux switch; irrigation refills to FC | s_e = ((Z − Z_r)/h_b)^(−1/b) − θ_r/n |
| Bean et al. 2018 — [field_capacity_volumetric_water_content.md](/home/user/cavargar/fc_modeling/field_capacity_volumetric_water_content.md) | θFC after gravity drainage, before ET; estimated from sensor drying cycles; shown to be temporally dynamic | One-night drainage rule; θ = (θB − θFC)e^(−λt) + θFC; daily FC shifts < 2%, max 6.2–6.8% |
| Liu et al. 2025 (Agronomy) — [agronomy_hydrus1d_2018.md](/home/user/cavargar/fc_modeling/agronomy_hydrus1d_2018.md) | FC as upper limit of PAW, measured 24–48 h after > 80 mm rain; constraint for HYDRUS-1D inverse calibration | FC 29.0–40.65% (tea), 22.5–28.55% (grass) |
| Rigby & Porporato 2006 — [hess-10-861-2006.md](/home/user/cavargar/fc_modeling/hess-10-861-2006.md) | No explicit FC; continuous percolation k_s s^c | — |
| Bovier et al. — [awr.md](/home/user/cavargar/fc_modeling/awr.md) | Cites Laio et al. 2001 framework; no own FC definition found by grep | — |
| Gandhi et al. 2025 — [2501.01569v1.md](/home/user/cavargar/fc_modeling/2501.01569v1.md); Or et al. 2000 — [or2000.md](/home/user/cavargar/fc_modeling/or2000.md) | No "field capacity" usage found by grep | — |

### Inferences
- The repo's stochastic models treat s_fc as a fixed soil parameter. The two empirical papers (Bean et al.; Liu et al.) and the AWR 2019 pore-dynamics paper all point to FC varying in time (antecedent moisture, hysteresis, structural evolution) and in depth. That tension is a natural framing for a review on FC in soil-moisture modeling.
- The repo's definitions correspond to the literature families:
  - Laio's is a flux-ratio definition, closest to Meyer & Gee and Twarakavi.
  - Bean's regression asymptote is a time-series cousin of the drainage-cessation definition.
  - Liu's 24–48 h rule is the classic Veihmeyer & Hendrickson / SSSA time-based definition.

### Gaps
- The full reference [27] in Laio et al. is Hillel (1998), *Environmental Soil Physics*. Hillel's specific discussion of FC's "physical and practical relevance" was not accessed directly.
- I did not verify whether Rodríguez-Iturbe & Porporato (2004, *Ecohydrology of Water-Controlled Ecosystems*) specify the same 10% / 0.5 cm d⁻¹ numbers as Laio et al. (2001).
