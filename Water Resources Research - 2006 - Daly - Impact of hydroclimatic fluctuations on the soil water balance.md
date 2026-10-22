## Impact of hydroclimatic fluctuations on the soil water balance

E. Daly<sup>1,2</sup> and A. Porporato<sup>1,2</sup>

Received 22 September 2005; revised 19 January 2006; accepted 2 February 2006; published 1 June 2006.

[1] We analyze the propagation of daily fluctuations in rainfall and potential evapotranspiration to soil moisture dynamics, using a stochastic model that accounts for these two different forms of hydroclimatic variability. The pulsing, intermittent behavior of daily precipitation is described by a compound Poisson process that models the unpredictability of both frequency and amount of rainfall events, while fluctuations in potential evapotranspiration that act continuously in time are assumed to be Gaussian. The resulting model for the soil water balance is thus a stochastic differential equation, forced by a state-dependent compound Poisson noise and a multiplicative Gaussian noise. Steady state probability distribution functions (pdfs) of soil moisture are obtained analytically along with the equations for the expected water balance and its variability. The multiplicative effect of temporal fluctuations in potential evapotranspiration on soil moisture reduces the soil water losses caused by evapotranspiration compared to the case when they are not present. Most importantly, the analysis also shows that because of their different forms and state dependence the impact of rainfall variability on soil moisture dynamics is much more significant than that of potential evapotranspiration, the fluctuations of which do not affect appreciably the soil moisture statistical properties.

**Citation:** Daly, E., and A. Porporato (2006), Impact of hydroclimatic fluctuations on the soil water balance, *Water Resour. Res.*, 42, W06401, doi:10.1029/2005WR004606.

### 1. Introduction

[2] Soil moisture fluctuations control in a nonlinear way mass, momentum, and energy fluxes, as well as vegetation conditions and soil nutrient dynamics, playing a unique role in the soil-plant-atmosphere system [e.g., Noy-Meir, 1973; Eagleson, 1978; Brubaker and Entekhabi, 1995; Porporato and Rodriguez-Iturbe, 2002; Rodriguez-Iturbe and Porporato, 2004]. In turn, soil moisture temporal dynamics is the result of different and complex processes within the soil-plant system that are strongly affected by climatic and environmental fluctuations. The interplay between soil water and climatic conditions is chiefly established through rainfall, which is the input to the soil water balance, and evapotranspiration, which is the main mechanism to soil water loss [e.g., Budyko, 1974; Milly, 1994; Koster and Suarez, 1999; Farmer et al., 2003; Potter et al., 2005].

[3] Both rainfall and evapotranspiration are characterized by a strong temporal variability that covers a wide spectrum of timescales ranging from seconds to decades. The interactions with the other hydrological processes add further variability and this makes it arduous to quantify the impact of the hydroclimatic forcings on soil moisture dynamics. While the complexity of the problem hinders full analytical approaches, field data analysis and numerical models are often case-specific and lack the generality of analytical

results. It is thus clear the necessity of simplified analytical approaches that focus on the main governing processes at specific scales of interest.

[4] At short timescales, insights on the interaction of evapotranspiration and soil water content have been obtained combining detailed models of soil-plant-atmosphere continuum with measured micrometeorological data [e.g., Baldocchi and Meyers, 1998; Katul et al., 2001; Daly et al., 2004]. Although these models have elucidated the role of environmental variables on stomatal control, photosynthesis, and transpiration, the upscaling of such models to include long-term hydroclimatic variability is still lacking. Other approaches have dealt with longer timescales using simplified models of soil water balance and accounting, at least in part, for the external hydroclimatic variability by suitable stochastic processes. Starting with the work of Eagleson [1978], stochastic models have analyzed impact of daily rainfall variability, in terms both of amount and timing of events, on the soil water balance [Milly, 1993; Rodriguez-Iturbe et al., 1999; Laio et al., 2001; Porporato et al., 2004], while D'Odorico et al. [2000] investigated the effect of interannual rainfall variability on the mean soil moisture content. Other models [e.g., Milly, 1994; Laio et al., 2002; Potter et al., 2005] considered the role of seasonal variability of both precipitation and potential evapotranspiration. However, while these models account for the stochastic nature of rainfall, the random variability of potential evapotranspiration rate was not explicitly considered. Conversely, fluctuations in evapotranspiration rate were considered in the soil-atmosphere model of Brubaker and Entekhabi [1996] in the absence of rainfall input, while both forms of fluctuations were considered in the numerical

<sup>1</sup>Department of Civil and Environmental Engineering, Duke University, Durham, North Carolina, USA.

<sup>2</sup>Also at Nicholas School of the Environment and Earth Sciences, Duke University, Durham, North Carolina, USA.analysis by *Atkinson et al.* [2002] and *Farmer et al.* [2003] using case-specific data.

[5] In the present paper, we focus on the propagation of fluctuations in rainfall and potential evapotranspiration to soil moisture dynamics at the daily timescale. To this aim we use a stochastic framework to derive a rigorous analytical description of the relative importance of these two different forms of variability on the soil moisture probabilistic structure. The probability density function of soil moisture, the mean water balance and its variability are obtained analytically and analyzed for different soil, climate, and vegetation conditions.

## 2. Daily Hydroclimatic Variability

[6] Rainfall and potential evapotranspiration are two very different forms of forcing to the soil water balance, not only because they act in opposite directions, but also because their daily temporal variability is quite different, as potential evapotranspiration is basically continuous in time and symmetric about its mean value, while rainfall is highly intermittent and asymmetric due to its positive pulses. Despite their different dynamics, however, the cumulative contribution of rainfall and potential evapotranspiration fluctuations is often of the same order of magnitude (see section 2.3), indicating a “potentially” similar impact on the expected soil water balance, at least in some conditions.

[7] The “actual” effect of both precipitation and evapotranspiration on the soil water balance depends on soil moisture dynamics itself. As a result, both types of forcing are not simply additive but, although in different manners, state-dependent. Thus the amount of rainfall that actually infiltrates into the soil is controlled by soil moisture through runoff generation, while actual evapotranspiration rate is strongly reduced at low soil water content. Their soil moisture dependence is quite different, as saturation acts as a threshold type of control on rainfall infiltration, while soil moisture deficit acts progressively on evapotranspiration from the onset of water stress to the plant wilting point [e.g., *Porporato et al.*, 2001]. We will discuss this in more detail in section 3; for now, we focus on the daily variability of rainfall and potential evapotranspiration, introducing suitable stochastic models for their modeling. In the following cross correlation between precipitation and evapotranspiration will be neglected, so that the two processes are considered independent.

### 2.1. Potential Evapotranspiration

[8] In temperate to arid regions soil water losses occur mainly through evapotranspiration during the growing season. Moreover, in presence of continuous vegetation cover, transpiration is dominant over soil evaporation. Given our focus at the daily timescale, we will use averaged daily rates without consideration of the diurnal variability (see *Daly et al.* [2004, and references therein] for a discussion of the temporal upscaling of transpiration from hourly to daily levels).

[9] For the sake of simplicity, we will assume that daily evapotranspiration occurs at a maximum rate under well watered conditions; this corresponds to the potential evapotranspiration rate,  $E_p$ , the value of which depends on plant characteristics and climatic conditions in a highly nonlinear way. The possible control that soil moisture has on  $E_p$

through the boundary layer dynamics [e.g., *Parlange and Katul*, 1992; *Szilagyi*, 2001; *Ramirez et al.*, 2005] is neglected. As soil water availability decreases, evapotranspiration is reduced and the actual evapotranspiration,  $E$ , is assumed to be related to  $E_p$  via a reduction factor that depends on the relative soil moisture content over the rooting zone, i.e.,  $E = f(s)E_p$  [e.g., *Federer*, 1979; *Wetzel and Chang*, 1987; *Albertson and Kiely*, 2001; *Laio et al.*, 2001; *Daly et al.*, 2004]. The inclusion of a dependence of evapotranspiration on vertical soil water profiles [*Guswa et al.*, 2002] or different forms of soil moisture control on evapotranspiration [e.g., *Cowan*, 1965; *Guswa*, 2005] are not expected to change qualitatively the results of what will be presented.

[10]  $E_p$  is strongly affected by environmental factors and by the related plant stomatal behavior, as it appears from the familiar semiempirical Penman-Monteith equation [e.g., *Daly et al.*, 2004],

$$E_p = \frac{g_s L_{AI} (c_p \rho_a g_a D + S \Phi)}{\rho_w \lambda_w [\gamma_p (g_a + g_s L_{AI}) + S g_s L_{AI}]}, \quad (1)$$

where  $g_s$  and  $g_a$  ( $\text{mm s}^{-1}$ ) are the stomatal and atmospheric conductances,  $L_{AI}$  ( $\text{m}^2 \text{ leaf m}^{-2} \text{ ground}$ ) is the leaf area index,  $c_p = 1012 \text{ J kg}^{-1} \text{ K}^{-1}$  is the specific heat of air,  $\rho_a = 1.2$  and  $\rho_w = 1000 \text{ kg m}^{-3}$  are air and water density,  $D$  (Pa) is vapor pressure deficit,  $S$  ( $\text{Pa K}^{-1}$ ) is the slope of the curve relating saturation vapor pressure and temperature (which depends on atmospheric temperature,  $T_a$ ),  $\Phi$  is net radiation ( $\text{W m}^{-2}$ ),  $\lambda_w = 2.5 \cdot 10^6 \text{ J kg}^{-1}$  is the latent heat of water vaporization, and  $\gamma_p = (p_a c_p) / (0.622 \lambda_w) = 66.1 \text{ Pa K}^{-1}$  is the psychrometric constant, with  $p_a$  (Pa) being the air pressure.

[11] An example of the marked daily variability of the environmental variables involved in equation (1) is represented in Figure 1 that shows daily averages of net radiation ( $\Phi$ ), air temperature ( $T_a$ ), vapor pressure deficit ( $D$ ), and atmospheric conductance ( $g_a$ ) measured during the Duke FACE experiment (Duke Forest, North Carolina, United States). Atmospheric conductance is evaluated using wind speed data, following *Campbell and Norman* [1998]. The series are used to estimate the potential daily transpiration through equation (1), assuming constant stomatal conductance of  $5 \text{ mm s}^{-1}$  [e.g., *Jones*, 1992], and  $L_{AI} = 3$  [*Katul et al.*, 2003]. It is important to stress that the value of  $g_s$  represents a daily and canopy-averaged conductance under conditions of no soil moisture deficit. The resulting potential evapotranspiration time series is represented in Figure 2a, suggesting that the potential evapotranspiration rate can be decomposed into a constant mean value,  $\bar{E}_p$ , plus symmetric fluctuations,  $E'_p(t)$ , that are approximately Gaussian distributed.

[12] Since the autocorrelation of such fluctuations decays to zero in an exponential manner, the Ornstein-Uhlenbeck (OU) process is a good candidate for modeling the stochastic fluctuations of  $E'_p(t)$  [e.g., *Gardiner*, 1990]. Accordingly,

$$\frac{dE'_p}{dt} = -kE'_p + a\xi(t), \quad (2)$$

where  $\xi(t)$  is a Gaussian white noise, with  $\langle \xi(t) \rangle = 0$  and  $\langle \xi(t)\xi(u) \rangle = \delta(t - u)$  (e.g., the formal time derivative of a![Figure 1: Four time series plots for the 2001 growing season. Top-left: Net solar radiation (Φ) in W m⁻², ranging from 0 to 400. Top-right: Air temperature (Tₐ) in °C, ranging from 0 to 30. Bottom-left: Vapor pressure deficit (D) in kPa, ranging from 0 to 1.5. Bottom-right: Atmospheric conductance (gₐ) in mm s⁻¹, ranging from 0 to 90. All plots have an x-axis labeled 'DOY' from 150 to 300.](4363a04790cf3b55f20df47bfaa3a527_4_img.webp)

**Figure 1.** Time series of net solar radiation ( $\Phi$ ), air temperature ( $T_a$ ), vapor pressure deficit ( $D$ ), and atmospheric conductance ( $g_a$ ). Data are of the 2001 growing season from the Duke Forest site, North Carolina (United States).

Wiener process). The value of the two parameters  $k$  ( $\text{d}^{-1}$ ) and  $a$  ( $\text{mm d}^{-3/2}$ ) can be evaluated from the time series of potential evapotranspiration. In fact, the characteristic correlation time,  $\tau$ , of the exponential decay of the autocorrelation function of  $E'_p$ , is equal to  $1/k$  [e.g., *Gardiner*, 1990]. This is typically of the order of few days, being controlled by climatic synoptic disturbances; in particular, for the series shown in Figure 2a,  $\tau \sim 2\text{d}$ , so that  $k \sim 0.5\text{ d}^{-1}$ . The other parameter,  $a$ , can be obtained from the variance of the steady state Gaussian distribution of the OU process,  $\text{var}_{E'_p} = a^2/(2k)$ . Since  $\tau \sim 2$  days,  $a$  results to be numerically equal to the standard deviation of the time series, which, in the case of the series of Figure 2a, is  $2.86\text{ mm d}^{-1}$ .

[13] Equation (2) is a realistic description of  $E'_p$  fluctuations, but its temporal correlation makes it a colored Gaussian noise, which is difficult to deal with analytically. However, thanks to the relatively low correlation time, the model of  $E'_p$  can be simplified adopting the so-called adiabatic elimination of fast variables [see, e.g., *Gardiner*, 1990, pp. 195–196]. In this manner, the (short memory) colored noise of equation (2) is replaced by an equivalent idealized Gaussian white noise with zero memory, where, in order to maintain the same dynamical effect on the soil water balance, the diminution of correlation must be coupled to an adequate augment in the noise strength [e.g., *Horsthemke and Lefever*, 1984]. Accordingly, the potential evapotranspiration can be written as

$$E_p = \bar{E}_p + E'_p = \bar{E}_p + b \xi(t), \quad (3)$$

where, as before,  $\xi(t)$  is the formal derivative of the Wiener process and  $b = a/k$  [e.g., *Gardiner*, 1990]. Using the parameters obtained before for the series shown in Figure 2a,  $b$  is equal to  $5.74\text{ mm d}^{-1/2}$ .

[14] Figure 3 shows the cumulative water loss by potential evapotranspiration,  $w_E$ , during the course of a typical

growing season, using parameters derived from the series in Figure 2a. The different realizations of the process are close to the integral of the time series of Figure 2a (thick line in Figure 3) and give rise to a Gaussian pdf at the end of the

![Figure 2: Two time series plots. (a) Potential evapotranspiration (Eₚ) in mm d⁻¹, ranging from 0 to 12. (b) Precipitation (rainfall) in mm, ranging from 0 to 45. Both plots have an x-axis labeled 'DOY' from 150 to 300.](4363a04790cf3b55f20df47bfaa3a527_12_img.webp)

**Figure 2.** Time series of (a) potential evapotranspiration, evaluated from data of Figure 1, and (b) precipitation recorded during the 2001 growing season at the Duke Forest site, North Carolina (United States).![Figure 3: Cumulative rainfall and potential evapotranspiration. The main plot shows cumulative rainfall (w_R in mm) and potential evapotranspiration (w_E in mm) over time (DOY). The y-axis ranges from -900 to 600 mm. The x-axis ranges from 0 to 300 DOY. Thick lines represent data from Figure 2, while thinner lines represent model realizations. Parameters for rainfall: lambda = 0.31 d^-1, alpha = 8.2 mm, mu = 440 mm, var = 7340 mm^2. Parameters for evapotranspiration: E_p = 5.3 mm d^-1, sigma_E = 2.87 mm d^-1, mu = 930 mm, var = 5798 mm^2. On the right, two probability density function (pdf) curves are shown, one for rainfall and one for evapotranspiration, with a scale bar of 0.05.](11f576ea281a403c6c37b4e13aecd791_4_img.webp)

**Figure 3.** Cumulative rainfall and potential evapotranspiration. The thick lines are derived from the data of Figure 2, while the other curves are different realizations obtained with the models presented in sections 2.1 and 2.2, with the parameters calculated from the time series ( $\sigma_E$  is the standard deviation of  $E_P$  in Figure 2). On the right the analytical pdfs of the two processes (sections 2.1 and 2.2) are also shown.

growing season, which is also represented in Figure 3. Since the mean and the variance of such a pdf vary in time as  $\langle w_E(t) \rangle = \bar{E}_p t$  and  $\text{var}_{w_E}(t) = b^2 t$ , respectively, at the end of the growing season (for the data in Figures 1, 2, and 3 the growing season has been assumed to last for 176 days from the beginning of May to the end of October) they are  $\langle w_E \rangle = 930$  mm and  $\text{var}_{w_E} = 5798 \text{ mm}^2$ .

## 2.2. Precipitation

[15] At the daily timescale, precipitation may be considered as a sequence of instantaneous rainfall events each carrying a random amount of water. This intermittent and impulsive nature is apparent in the time series of Figure 2b measured at the Duke Forest site. A good model for this type of external forcing is the so-called compound Poisson process, that has been previously used in stochastic soil moisture models [e.g., *Milly, 1993; Rodriguez-Iturbe et al., 1999; Laio et al., 2001; Porporato et al., 2004*]. Accordingly, the occurrence of rainfall events is modeled as a series of point events, arising in a Poisson process with rate  $\lambda$ , while the amount of water per event is assumed to be extracted from an exponential distribution with mean  $\alpha$ .

[16] Writing the master equation of the process, it is possible to obtain the pdf of the cumulative rainfall at time  $t$ ,  $w_R(t)$ , as

$$p(w_R, t) = \exp\left(-\frac{w_R}{\alpha} - \lambda t\right) \left[ \sqrt{\frac{\lambda t}{\alpha w_R}} I_1\left(2\sqrt{\lambda w_R t / \alpha}\right) + \delta(w_R) \right], \quad (4)$$

where  $I_\nu(\cdot)$  is the modified Bessel function of the first kind of order  $\nu$  [e.g., *Abramowitz and Stegun, 1965*]. The Dirac-delta function  $\delta(\cdot)$  accounts for the probability that it does not rain up to time  $t$ . It is also possible to show that the mean rainfall grows linearly with time according to  $\langle w_R(t) \rangle = \lambda \alpha t$ , while the variance depends on time as  $\text{var}_{w_R} = 2\lambda \alpha^2 t$ . A comparison between the data of Figure 2b and the model is

represented in Figure 3. Different realizations, in which the input parameters  $\lambda = 0.31 \text{ d}^{-1}$  and  $\alpha = 8.2 \text{ mm}$  are evaluated from the series, are shown along with the pdf of  $w_R$ , equation (4), at the end of the growing season. The mean amount of water over a growing season is 440 mm, while the variance is  $7340 \text{ mm}^2$ .

## 2.3. Precipitation Versus Evapotranspiration

[17] The two stochastic models presented in the previous subsections take into account the unpredictable dynamics of precipitation and evapotranspiration, adopting a relatively simple formulation with a minimal number of parameters. Figure 3 also compares the total amount of precipitation with the total potential evapotranspiration losses for the specific case of the Duke forest. The ratio between the mean potential evapotranspiration rate,  $\bar{E}_p$ , and rainfall rate,  $\alpha \lambda$ , is the Budyko dryness index,  $D_I$  [*Budyko, 1974*], which in this case is about 2, indicating a semiarid growing season [*Porporato et al., 2004*]. More interesting for the purpose of this investigation is the fact that the variability of the two processes is quite similar. The ratio of the two variances, i.e., the ratio of  $\text{var}_{w_E}(t) = b^2 t$  and  $\text{var}_{w_R} = 2\lambda \alpha^2 t$ , gives an estimate of which of the two mechanisms has potentially more impact on the variability of soil moisture. A dryness variability index can thus be defined as  $V_I = b^2 / (2\lambda \alpha^2)$ , which in the case of Figure 2 is about 0.8.

[18] It should be added here that the previous considerations do not account for plant canopy interception, which is a form of direct evaporation but technically not a soil water loss. It is thus interesting to briefly discuss, again using a simplified approach, how interception may reduce rainfall variability. Following *Rodriguez-Iturbe et al.* [1999], interception can be modeled assuming that a maximum given amount of water,  $\Delta$ , is intercepted from each rainfall event. This can be shown to be equivalent to the frequency of the events as  $\lambda' = \lambda \exp(-\Delta/\alpha)$ . Therefore, assuming for instance an interception  $\Delta = 1.5 \text{ mm}$ , the equivalent![Figure 4: (a) Soil moisture data from the Konza Prairie Biological Station, Kansas (United States) [see, e.g., Knapp et al., 2002] and (b) corresponding soil water losses for ambient (triangles) and altered (squares) rainfall regimes (see text for details). The solid line represents the approximation of the losses, while the dashed lines show the lower and upper limits in the fluctuations of the losses, which increase linearly with soil moisture as well.](0d129a8c5b1da1cb49f2dbc1ea0022a7_4_img.webp)

Figure 4 consists of two panels. Panel (a) is a line graph showing soil moisture (s) on the y-axis (ranging from 0.2 to 0.8) versus time (t in days) on the x-axis (May to September). The data points are connected by a dashed line, showing fluctuations in soil moisture over time. Panel (b) is a scatter plot showing soil water losses (ds/dt in mm d⁻¹) on the y-axis (ranging from 0 to 8) versus soil moisture (s) on the x-axis (ranging from 0 to 0.8). Data points are shown for ambient rainfall (triangles) and altered rainfall (squares). A solid line represents the linear approximation of the losses, and two dashed lines represent the lower and upper limits of the fluctuations, which increase linearly with soil moisture.

**Figure 4.** (a) Soil moisture data from the Konza Prairie Biological Station, Kansas (United States) [see, e.g., *Knapp et al.*, 2002] and (b) corresponding soil water losses for ambient (triangles) and altered (squares) rainfall regimes (see text for details). The solid line represents the approximation of the losses, while the dashed lines show the lower and upper limits in the fluctuations of the losses, which increase linearly with soil moisture as well.

frequency of rainfall events becomes  $\lambda' = 0.26 \text{ d}^{-1}$ , so that the mean and the variance of the total rainfall that is not intercepted at the end of the growing season becomes 375 mm and 6150 mm<sup>2</sup>, respectively. Consequently, due to the interception, the dryness index increases and its variability moves closer to 1. As a result, the potential variabilities of rainfall and evapotranspiration on the soil water balance become even closer.

### 3. Soil Moisture Dynamics

[19] We turn now to consider how rainfall and evapotranspiration variability propagate through the daily soil moisture dynamics. The soil water balance equation, averaged over the root zone of depth  $Z_r$ , can be written as

$$nZ_r \frac{ds}{dt} = R(t) - I(t) - LQ[s(t), t] - E[s(t), t], \quad (5)$$

where  $s$  is vertically averaged relative soil moisture,  $n$  is soil porosity,  $R$  is rainfall rate,  $I$  is canopy interception,  $LQ$  represents the sum of runoff and deep percolation, and  $E$  is evapotranspiration. Differently from previous similar models [e.g., *Milly*, 1993; *Rodriguez-Iturbe et al.*, 1999; *Laio et al.*, 2001; *Porporato et al.*, 2004], we will include here the temporal variability of potential evapotranspiration rate. Following the minimalist approach of *Milly* [1993] and *Porporato et al.* [2004], we will assume that runoff and drainage take place instantaneously (at the daily timescale) only close to saturation, i.e., for  $s \geq s_1$ , where  $s_1$  is a parameter comprised between field capacity and saturation. Therefore, when the amount of water carried by a rainfall event is higher than the available soil storage capacity, e.g.,  $nZ_r(s_1 - s)$ , the exceeding rainfall is immediately lost as runoff or drainage. Because of this saturation control on infiltration, precipitation acts as a state-dependent forcing on the soil water balance. Canopy interception is modeled as described in section 2.3, using a threshold  $\Delta$  that depends on vegetation type and condition (e.g., function of plant type and leaf area index).

[20] As explained before, actual evapotranspiration is simply considered to be a function of potential evapotranspiration, i.e.,  $E[s(t), t] = f(s)E_p(t)$ , where  $f(s)$  is assumed to decrease linearly from 1 under well watered conditions ( $s = s_1$ ) to zero at the wilting point ( $s = s_w$ ). A linear relation provides a good representation of field data and was used in

previous theoretical studies of soil moisture dynamics [e.g., *Brubaker and Entekhabi*, 1995; *Porporato et al.*, 2004]. In this paper we also include time variability in  $E_p(t)$  (see section 2.1), and thus actual evapotranspiration is given by the sum of a deterministic component, dependent on soil water content, plus a stochastic term (also dependent on soil moisture) that accounts for the environmental variability and acts as a multiplicative noise on the soil moisture equation. As an example, Figure 4 shows the soil water losses obtained from the soil moisture time series measured by *Knapp et al.* [2002] during a long-term rainfall manipulative experiment. The losses, computed as time derivative of soil moisture series during dry downs in both ambient and altered conditions, can be approximated with a linear dependence on  $s$  plus irregular fluctuations that also tend to linearly increase with  $s$ .

[21] Equation (5) can be normalized with respect to the maximum soil water storage capacity,  $w_0 = nZ_r(s_1 - s_w)$ , as

$$\frac{dx}{dt} = Y[x(t), t] - [\eta x(t) + \beta x(t)\xi(t)], \quad (6)$$

where  $x = (s - s_w)/(s_1 - s_w)$  is the effective relative soil moisture, bounded between 0 and 1,  $Y = (R - I - LQ)/w_0$  is the normalized rate of rainfall minus interception, runoff and drainage,  $\eta x(t)$  is the deterministic component of evapotranspiration ( $\eta = \bar{E}_p/w_0$ ) and  $\beta x(t)\xi(t)$  is the stochastic forcing related to evapotranspiration, where  $\beta = b/w_0$ . Equation (6) is a nonlinear stochastic differential equation driven by two different forms of noise: a multiplicative Gaussian noise and a state dependent Poisson noise. The multiplicative noise  $x(t)\xi(t)$  is interpreted according to Stratonovich [e.g., *Van Kampen*, 1981]. This interpretation is appropriate when the multiplicative Gaussian white noise is obtained as a limit of a colored noise (see section 2.1).

[22] It is interesting to study the soil moisture pdf during dry downs, when only evapotranspiration variability is present. With the substitution  $y = \ln(x)$  ( $-\infty < y < 0$ ), and in the absence of rainfall, equation (6) becomes

$$\frac{dy}{dt} = -\eta + \beta \xi(t), \quad (7)$$

which is simply a Wiener process with constant drift  $-\eta$  and a reflecting barrier at  $y = 0$  (classical rules of differential![Figure 5: (a) Transient pdf of x during dry down of 47 days. (b) Time dependence of var_x(t) for three different values of b.](6324b75a6d2507364315d404bb36a908_4_img.webp)

Figure 5 consists of two subplots. Subplot (a) shows the transient probability density function (pdf) of soil moisture \$x\$ during a dry down of 47 days. The x-axis represents soil moisture \$x\$ from 0 to 1, and the y-axis represents the pdf \$p(x)\$ from 0 to 25. Multiple curves are shown for different days: 47d, 42d, 37d, 32d, 27d, 22d, 17d, 12d, 7d, and 2d. The curves shift to the right and become broader as the dry down progresses. Subplot (b) shows the time dependence of the variance \$var\_x(t)\$ for three different values of the noise intensity \$b\$: 1 (short-dashed line), 2 (long-dashed line), and 3 (solid line). The x-axis is time \$t\$ in days from 0 to 20, and the y-axis is \$var\_x\$ from 0 to 0.008. All three curves show an initial increase in variance, peaking around \$t=10\$ days, followed by a gradual decrease.

**Figure 5.** (a) Transient pdf of \$x\$ during dry down of 47 days starting from well watered conditions (e.g., \$x = 1\$, \$s = s\_1\$), with \$b = 2.5 \text{ mm d}^{-1/2}\$. (b) Time dependence of \$var\_x(t)\$ for three different values of \$b\$: 1 (short-dashed line), 2 (long-dashed line), and 3 \$\text{mm d}^{-1/2}\$ (solid line). Other parameters are \$n = 0.373\$, \$Z\_r = 300 \text{ mm}\$, \$s\_w = 0.047\$, \$s\_1 = 0.6\$, and \$\bar{E}\_p = 3.7 \text{ mm d}^{-1}\$.

calculus are used because of the Stratonovich interpretation of the noise). The transient pdf of \$y\$ is well known [e.g., Cox and Miller, 1965] and the one of \$x\$, obtained as a derived distribution, reads

$$p(x, t) = \frac{1}{x\beta\sqrt{2\pi t}} \left\{ \exp \left[ -\frac{(\eta t + \ln x_0 + \ln x)^2}{2\beta^2 t} \right] + \exp \left[ -\frac{4\eta \ln x_0 t + (\eta t - \ln x_0 + \ln x)^2}{2\beta^2 t} \right] + \frac{2\eta}{\beta^2} \exp \left( \frac{2\eta \ln x}{\beta^2} \right) \times \left[ 1 - \text{erf} \left( \frac{-\ln x + \ln x_0 + \eta t}{\beta\sqrt{t}} \right) \right] \right\}, \quad (8)$$

where \$x\_0\$ is the initial condition and \$\text{erf}(\cdot)\$ is the error function [Abramowitz and Stegun, 1965]. Figure 5a shows the temporal evolution of the pdf during a dry down starting from \$x\_0 = 1\$. The mean value of \$x\$ does not vary much with \$\beta\$ and it decays approximately as \$x\_0 \exp(-\eta t)\$, while the variance initially increases up to a maximum, after which it gradually decreases. It is clear how the two bounds at 1 and 0 harness the oscillations of \$x\$ depending on the value of \$\beta\$, whose impact is reduced at low soil moisture values because of the multiplicative form of the noise. The variance of soil

moisture is thus lower in very wet and in dry conditions (Figures 5a and 5b).

#### 4. Soil Moisture Probability Distribution

[23] The dynamics of the probability density function \$p(x, t)\$ when both noises are present is governed by the master equation [e.g., Czernik et al., 1997; Daly and Porporato, 2006]

$$\frac{\partial}{\partial t} p(x, t) = \frac{\partial}{\partial x} \left[ \left( \eta x - \frac{1}{2} \beta^2 x \right) p(x, t) \right] - \lambda p(x, t) + \lambda \gamma \int_0^x e^{-\gamma(x-u)} p(u, t) du + \frac{1}{2} \beta^2 \frac{\partial^2}{\partial x^2} [x^2 p(x, t)], \quad (9)$$

where \$\gamma = w\_0/\alpha\$. The fluctuations in evapotranspiration give rise to the state-dependent diffusion (last term in equation (9)), while for \$\beta = 0\$ the problem reduces to that studied by Porporato et al. [2004].

[24] Given the complexity of equation (9), we only analyze the system in stationary conditions (e.g., \$\partial p(x, t) = 0\$). As shown by Daly and Porporato [2006], the steady state solution can be derived as

$$p(x) = C e^{-\gamma x} x^{\kappa_1 - 1} L_{-\kappa_1 - 1}^{\kappa_1 - \kappa_2}(\gamma x), \quad (10)$$
![Figure 6: (top) Time series of modeled soil moisture. (bottom) Corresponding pdfs.](6324b75a6d2507364315d404bb36a908_16_img.webp)

Figure 6 consists of two subplots. Subplot (top) shows the time series of modeled soil moisture \$x\$ over 200 days. The x-axis is time \$t\$ in days from 0 to 200, and the y-axis is soil moisture \$x\$ from 0 to 0.6. Two curves are shown: a dashed line for \$b = 2.5 \text{ mm d}^{-1/2}\$ and a solid line for \$b = 5 \text{ mm d}^{-1/2}\$. Both curves show oscillatory behavior with peaks around \$x = 0.4\$ and troughs around \$x = 0.1\$. Subplot (bottom) shows the corresponding probability density functions (pdfs) \$p(x)\$ for the same two noise intensities. The x-axis is soil moisture \$x\$ from 0 to 1, and the y-axis is \$p(x)\$ from 0 to 2. The solid line (\$b = 5\$) has a higher peak than the dashed line (\$b = 2.5\$). A dotted line represents the pdf for \$b = 0 \text{ mm d}^{-1/2}\$, which has a lower peak than both.

**Figure 6.** (top) Time series of modeled soil moisture with two different values of noise intensity (\$b = 2.5\$, dashed line, and \$b = 5 \text{ mm d}^{-1/2}\$, solid line) when \$\lambda = 0.2 \text{ d}^{-1}\$, \$\alpha = 4.5 \text{ mm}\$, and \$\Delta = 0\$. (bottom) Corresponding pdfs (the dotted line represents the pdf with \$b = 0 \text{ mm d}^{-1/2}\$). Other parameters are as in Figure 5.![Figure 7: Mean soil moisture as a function of (a) λ and (b) Z_r. Plot (a) shows mean soil moisture <x> increasing with λ (d⁻¹) from 0.25 to 0.4. Plot (b) shows mean soil moisture <x> increasing with Z_r (cm) from 0 to 30. Both plots show three curves for different evapotranspiration rates b: 5 mm d⁻¹/² (solid), 2.5 mm d⁻¹/² (long-dashed), and 0 mm d⁻¹/² (short-dashed).](972db4ba6baaac2a20a1ae885f113fbf_4_img.webp)

**Figure 7.** Mean soil moisture as a function of (a)  $\lambda$  and (b)  $Z_r$  with  $b = 5 \text{ mm d}^{-1/2}$  (solid lines),  $b = 2.5 \text{ mm d}^{-1/2}$  (long-dashed lines), and  $b = 0 \text{ mm d}^{-1/2}$  (short-dashed lines). Other parameters are as in Figure 5.

where  $C$  is a constant of normalization, obtained with the condition  $\int_0^1 p(x) dx = 1$ ,

$$\kappa_{1,2} = \frac{-\eta \pm \sqrt{\eta^2 + 2\lambda\beta^2}}{\beta^2}, \quad (11)$$

and  $L_n^m(\cdot)$  is the generalized Laguerre polynomial [Abramowitz and Stegun, 1965]. In the limit case  $\beta = 0$ , equation (10) reduces to a truncated Gamma distribution [e.g., Porporato et al., 2004].

[25] Figure 6 shows two realizations for two different values of noise with the corresponding pdfs compared to the case with no evapotranspiration fluctuations ( $\beta = 0$ ). While the effect of  $\beta$  is hardly visible in the time series, it becomes more evident in the probability distributions. The most evident effect of increases in  $\beta$  is the movement of the mode of the pdf toward lower values of  $x$ , as it is typical in stochastic processes with multiplicative noise [e.g., Schenzle and Brand, 1979]. Further analyses for different soil and climatic conditions (not shown) reveal that generally soil moisture pdfs are not much affected by evapotranspiration variability. However, deeper soils tend to attenuate the effect of  $\beta$  on  $x$ , since  $nZ_r$  largely controls the relaxation time of the system, while different climatic conditions, i.e., different values of  $\lambda$  and  $\alpha$ , induce slight changes in the pdf of  $x$ .

[26] This can also be seen by analyzing the mean of  $\langle x \rangle$ . The effect of daily fluctuations of  $E_p$ , although quantitatively small, tends to increase the mean soil moisture value especially for deep-rooted soils (Figures 7a and 7b). Including canopy interception tends to reduce the impact of

environmental fluctuations, since interception makes the soil drier, with a consequent reduction in actual evapotranspiration fluctuations because of their multiplicative nature. While the impact on the mean of  $x$  is very low, the variance of  $x$  is more evidently affected by the Gaussian noise. Figure 8 shows how the soil moisture variance increases as  $\beta$  grows for different rainfall frequency and rooting depths.

[27] In order to verify that the negative values of  $E_p$  that are sometimes generated by the evapotranspiration model do not affect the conclusions of our analysis, we also generated numerically a pdf in which the negative  $E_p$  values are set to zero. As can be seen in Figure 9, the effects of such values are indeed negligible.

#### 4.1. Expected Soil Water Balance

[28] The contribution of each component of the soil moisture balance equation (i.e., rainfall, leakage and runoff, and evapotranspiration) to the long-term water balance can be computed by multiplying equation (9) by  $x$  and integrating between 0 and 1. This leads to (see Appendix A)

$$\frac{\lambda}{\gamma} \left( \eta - \frac{1}{2} \beta^2 \right) \langle x \rangle - \frac{\lambda}{\gamma} \int_0^1 e^{-\gamma(1-z)} p(z) dz - \frac{1}{2} \beta^2 [p(x)]_{x=1} = 0, \quad (12)$$

which can be interpreted as an averaged water balance normalized by  $w_0$  [Porporato et al., 2004], where the input

![Figure 8: Variance of soil moisture as a function of (a) λ and (b) Z_r. Plot (a) shows variance var_x increasing with λ (d⁻¹) from 0.1 to 0.3. Plot (b) shows variance var_x increasing with Z_r (mm) from 0 to 300. Both plots show three curves for different evapotranspiration rates b: 0 mm d⁻¹/² (short-dashed), 2.5 mm d⁻¹/² (long-dashed), and 5 mm d⁻¹/² (solid).](972db4ba6baaac2a20a1ae885f113fbf_17_img.webp)

**Figure 8.** Variance of soil moisture as a function of (a)  $\lambda$  ( $\alpha = 4.5 \text{ mm}$ ,  $Z_r = 300 \text{ mm}$ ) and (b)  $Z_r$  ( $\lambda = 0.2 \text{ d}^{-1}$ ,  $\alpha = 4.5 \text{ mm}$ ) for  $b = 0 \text{ mm d}^{-1/2}$  (short-dashed line),  $b$  equal to  $2.5 \text{ mm d}^{-1/2}$  (long-dashed line), and  $5 \text{ mm d}^{-1/2}$  (solid line). Other parameters are as in Figure 5.![Figure 9: Two plots showing analytical probability density functions (pdfs) compared to numerical simulations (histograms). The left plot is for b = 2.5 mm d⁻¹/² and the right plot is for b = 5 mm d⁻¹/². Both plots show p(x) on the y-axis (ranging from 0 to 3) and x on the x-axis (ranging from 0 to 1). The histograms represent numerical simulations, and the solid lines represent analytical pdfs. The distributions are skewed towards the right, with the peak around x = 0.2.](c0e5f34904ba6b39716535a9a8bfc3a7_4_img.webp)

**Figure 9.** Analytical pdfs (solid line) obtained by (equation 10) compared to the results of numerical simulations (histograms), where the negative area of the Gaussian distribution describing evapotranspiration fluctuations has been concentrated in  $-\bar{E}_p$ . Parameters are as in Figure 6.

of water given by the mean seasonal rainfall rate,  $\langle R \rangle = \lambda/\gamma$ , is compensated by the average losses due to evapotranspiration (second part of the first row) and leakage plus runoff (e.g., the integral term). The last term of equation (12) is an artificial contribution to the loss rates introduced by the interaction between the bound at  $x = 1$  and the evapotranspiration fluctuations when  $E_p$  is not strictly bounded at  $x = 0$ . As noticed before, however, with realistic values of the parameters this term is negligible and can be ignored.

[29] The novel effect introduced by evapotranspiration fluctuations is in the second part of the evapotranspiration term, i.e.,  $\beta^2 \langle x \rangle / 2$ , which in the stochastic process literature is called “spurious drift” and is generated by the Stratonovich interpretations of the multiplicative noise [e.g., *Horsthemke and Lefever*, 1984]. This is responsible for a reduction of soil water losses, leading to higher values of averaged soil moisture (Figure 7), when compared to a similar water balance with constant potential evapotranspiration. In fact, writing equation (12) as

$$1 + \frac{V_l}{\gamma} \langle x \rangle = D_l \langle x \rangle + \frac{\langle LQ \rangle}{\langle R \rangle}, \quad (13)$$

where  $\langle LQ \rangle$  is the average loss rate due to leakage and runoff (the term  $V_l p(1)/\gamma$  has been neglected), clearly shows that when the evaporation fluctuations (e.g.,  $V_l$ ) increase, the average soil water losses grow as well. Increasing  $V_l$  while keeping the same climatic conditions is equivalent to increasing  $b$ , that is to having higher evapotranspiration variability. Since the term related to leakage and runoff in equation (13) cannot change considerably, it follows that, with the same value of  $\bar{E}_p$ , the average soil water content is higher than in the case with  $b = 0$  (see *Porporato et al.* [2004]).

[30] A physical intuition of this reduction of evapotranspiration losses due to the multiplicative noise can be gathered by analyzing the following simplistic case. Assuming potential evapotranspiration fluctuations in the form of a square wave of amplitude  $b$  around a mean value  $\bar{E}_p$  and constant precipitation, the water balance is simply

$$\frac{dx}{dt} = P - (\eta + \beta S)x(t), \quad (14)$$

where, as before,  $\eta = \bar{E}_p/w_0$ ,  $\beta = b/w_0$ , while  $P$  is the normalized rainfall rate,  $S = \text{sgn} [\sin(2\pi t/T)]$ , with  $\text{sgn}(\cdot)$  the sign function, and  $T$  is the period of the wave. With  $P/(\eta +$

$\beta) < 1$  and  $\beta < \eta$ , equation (14) can be solved analytically and its steady state mean reads

$$\langle x \rangle = \frac{P}{\eta(1 - \beta^2/\eta^2)} + \frac{4\beta^2 P}{(\eta^2 - \beta^2)^2 T \sinh(\eta T/2)} \cdot [\cosh(\beta T/2) - \cosh(\eta T/2)]. \quad (15)$$

One can easily see that when the ‘noise’ is uncorrelated (i.e.,  $T \rightarrow 0$ ), the oscillations do not affect the mean of the process (as would have been erroneously the case if we had interpreted evapotranspiration fluctuations in the Itô sense), and the average of  $x$  tends to  $P/\eta$ , which is the stationary value of  $x$  in the absence of fluctuations. When, on the other hand, the correlation of the fluctuations increases (i.e., higher values of  $T$ ),  $\langle x \rangle$  grows and reaches its maximum value  $P/[\eta(1 - \beta^2/\eta^2)]$  for  $T \rightarrow +\infty$ , which is higher than in the absence of fluctuations.

#### 4.2. Long-Term Soil Water Balance Variability

[31] Analogously to the mean soil water balance, an equation describing the rates of change of the variance of  $x$  ( $\text{var}_x = (\langle x^2 \rangle - \langle x \rangle^2)$ ) can be derived for statistically steady state conditions as (see Appendix A)

$$\frac{\lambda}{\gamma^2} - \eta \text{var}_x - \frac{\lambda}{\gamma} \left( \frac{1}{\gamma} + 1 - \langle x \rangle \right) \int_0^1 e^{-\gamma(1-z)} p(z) dz + \beta^2 \langle x^2 \rangle - \frac{1}{2} \beta^2 [p(x)]_{x=1} (1 - \langle x \rangle) = 0, \quad (16)$$

where the terms describe the effect of each component of the water balance on the variance of  $x$ . In particular, the first term in equation (16) is the variance rate introduced by rainfall variability, which is reduced by the action of evapotranspiration (second term) plus drainage and runoff (third term). The last two terms are related to the Gaussian fluctuations. In particular, the fourth one is a positive contribution to the variance rate due to the stochastic evapotranspiration fluctuations, while the last one is a negligible artificial term related (as for the mean water balance) to the interaction of the Gaussian noise with the bound at  $x = 1$ . The physical meaning of equation (16) is that at steady state the temporal variability introduced by the rainfall and evapotranspiration (the two positive terms) is balanced by the action of the deterministic component of evapotranspiration as well as by the variability of runoff and drainage losses (e.g., the integral term).![Figure 10: Components of the balance of variance rate normalized by the rainfall variance. The figure consists of two plots. The left plot shows %var vs λ (d⁻¹) for b=0 (dashed lines) and b=4 mm d⁻¹/² (solid lines). The right plot shows %var vs Zr (cm) for b=0 (dashed lines) and b=4 mm d⁻¹/² (solid lines). Both plots show three curves: E (top), LQ (middle), and b (bottom).](57542623c2567a377dbf038b4dcb0321_4_img.webp)

**Figure 10.** Components of the balance of variance rate normalized by the rainfall variance (e.g.,  $\lambda\alpha^2$ ) with  $b = 0$  (dashed lines) and  $b = 4 \text{ mm d}^{-1/2}$  (solid lines) for different  $\lambda$  and  $Z_r$ , with  $\alpha = 5 \text{ mm}$  and  $\Delta = 0$ . The labels  $E$ ,  $LQ$ , and  $b$  refer to the percentage of variance related to the deterministic evapotranspiration, runoff plus drainage, and evapotranspiration fluctuations, respectively. Other parameters are as in Figure 5.

[32] Figure 10 shows the balance of the components of the long-term variance (e.g., equation (16)) as a function of rainfall frequency and soil depth. The effect of  $\beta$  is that of a ‘negative’ loss of variance, since it actually introduces variance into the system. It mainly affects the deterministic component of evapotranspiration, which results to be higher than the correspondent loss in the absence of noise ( $\beta = 0$ ). On the other hand, the differences between the variance leakage rates with or without the Gaussian noise are always quite small.

## 5. Conclusions

[33] The effects of both rainfall and evapotranspiration variability on soil water balance have been analyzed theoretically in a simplified stochastic model of soil moisture dynamics. As expected, the presence of fluctuations in evapotranspiration tends to increase the variance of soil moisture dynamics, while interestingly it always reduces the water losses compared to the case with constant potential evapotranspiration. This reduction is due to the temporal correlation of such fluctuations, that, when coupled multiplicatively to soil moisture, tend to give less weight to evapotranspiration at higher soil moisture values. The most important conclusion, however, is that evapotranspiration fluctuations do not alter qualitatively the probabilistic properties of soil moisture dynamics (see Figures 7 and 8). This implies that simplified stochastic soil moisture models at the daily timescale provide quite a realistic description of the main soil moisture probabilistic properties even if only accounting for rainfall variability.

## Appendix A: Long-Term Mean and Variance Equations of the Water Balance

[34] Equation (9) can be written in a more manageable form as

$$\frac{\partial}{\partial t} p(x, t) = -\frac{\partial}{\partial x} J(x, t), \quad (\text{A1})$$

where the probability current  $J(x, t)$  is

$$J(x, t) = -\eta x p(x, t) + \lambda \int_0^x p(u, t) e^{-\gamma(x-u)} du + \frac{1}{2} \beta^2 x p(x, t) - \frac{1}{2} \frac{\partial}{\partial x} [\beta^2 x^2 p(x, t)]. \quad (\text{A2})$$

[35] From equation (A1), the dynamics of the mean effective relative soil moisture is

$$\frac{d\langle x \rangle_t}{dt} = \int_0^1 x \frac{\partial}{\partial t} [p(x, t)] dx = \int_0^1 x \frac{\partial}{\partial x} J(x, t) dx, \quad (\text{A3})$$

that in stationary conditions becomes

$$\begin{aligned} \int_0^1 x \frac{d}{dx} J(x) dx &= [xJ(x)]_0^1 - \int_0^1 J(x) dx \\ &= + \int_0^1 \eta x p(x) dx - \int_0^1 \lambda e^{-\gamma x} \left[ \int_0^x e^{\gamma z} p(z) dz \right] dx \\ &\quad - \frac{1}{2} \int_0^1 \beta^2 x p(x) dx + \frac{1}{2} \int_0^1 \beta^2 x^2 p(x) dx \\ &= 0. \end{aligned} \quad (\text{A4})$$

Solving the integrals with respect to  $x$  and reorganizing the terms gives equation (12).

[36] The dynamics of the variance of  $x$ ,  $\text{var}_x$ , is described by the relation

$$\begin{aligned} \frac{d\text{var}_x}{dt} &= \frac{d}{dt} \int_0^1 [(x - \langle x \rangle_t)^2 p(x, t)] dx \\ &= + \int_0^1 x^2 \frac{\partial}{\partial t} p(x, t) dx - 2\langle x \rangle_t \int_0^1 x \frac{\partial}{\partial t} p(x, t) dx \\ &= + \int_0^1 x^2 \frac{\partial}{\partial x} J(x, t) dx - 2\langle x \rangle_t \int_0^1 x \frac{\partial}{\partial x} J(x, t) dx. \end{aligned} \quad (\text{A5})$$

In steady state conditions, integrating by parts gives

$$\begin{aligned} &+ \int_0^1 x^2 \frac{d}{dx} J(x) dx - 2\langle x \rangle_t \int_0^1 x \frac{d}{dx} J(x) dx \\ &= -2 \int_0^1 x J(x) dx - 2\langle x \rangle_t \int_0^1 x \frac{d}{dx} J(x) dx \\ &= -2 \int_0^1 x J(x) dx - 2\langle x \rangle_t \frac{d\langle x \rangle_t}{dt} = 0, \end{aligned} \quad (\text{A6})$$

that, integrated with respect to  $x$ , gives equation (16).

## Notation

- $a$  intensity of the colored noise forcing  $E_p'$  ( $\text{mm d}^{-3/2}$ ).
- $b$  intensity of the white noise forcing  $E_p$  ( $b = a/k$ ) ( $\text{mm d}^{-3/2}$ ).$c_p$  air specific heat ( $\text{J kg}^{-1} \text{ K}^{-1}$ ).  
 $D$  vapor pressure deficit (Pa).  
 $D_I$  Budyko dryness index [Budyko, 1974] (dimensionless).  
 $E$  actual evapotranspiration rate ( $\text{mm d}^{-1}$ ).  
 $E_p$  potential evapotranspiration rate ( $\text{mm d}^{-1}$ ).  
 $\bar{E}_p$  mean potential evapotranspiration rate ( $\text{mm d}^{-1}$ ).  
 $E'_p$  fluctuations of potential evapotranspiration rate from  $\bar{E}_p$  ( $\text{mm d}^{-1}$ ).  
 $g_a$  atmospheric conductance ( $\text{mm s}^{-1}$ ).  
 $g_s$  stomatal conductance ( $\text{mm s}^{-1}$ ).  
 $I$  interception rate ( $\text{mm d}^{-1}$ ).  
 $k$  rate of decay of  $E'_p$  ( $\text{d}^{-1}$ ).  
 $L_{AI}$  leaf area index ( $\text{m}^2_{\text{leaf}} \text{m}^{-2}_{\text{ground}}$ ).  
 $LQ$  runoff and deep percolation loss rate ( $\text{mm d}^{-1}$ ).  
 $n$  soil porosity (dimensionless).  
 $p_a$  air pressure (Pa).  
 $R$  rainfall rate ( $\text{mm d}^{-1}$ ).  
 $S$  slope relating temperature and saturation vapor pressure ( $\text{Pa K}^{-1}$ ).  
 $s_w$  wilting point (dimensionless).  
 $s_1$  threshold defining well watered conditions (dimensionless).  
 $T_a$  air temperature (K).  
 $x$  effective relative soil moisture (dimensionless).  
 $V_I$  dryness variability index (dimensionless).  
 $w_0$  maximum soil storage capacity (mm).  
 $w_E$  cumulative water loss by evapotranspiration (mm).  
 $w_R$  cumulative rainfall (mm).  
 $Y$  normalized infiltration rate ( $\text{d}^{-1}$ ).  
 $Z_r$  root depth (mm).  
 $\alpha$  mean rainfall amount per event (mm).  
 $\beta$  normalized white noise intensity ( $b/w_0$ ) ( $\text{d}^{-3/2}$ ).  
 $\gamma$  inverse of the normalized mean rainfall depth ( $w_0/\alpha$ ) (dimensionless).  
 $\gamma_p$  psychrometric constant ( $\text{Pa K}^{-1}$ ).  
 $\Delta$  canopy interception threshold (mm).  
 $\eta$  normalized mean potential evapotranspiration rate ( $\bar{E}_p/w_0$ ) ( $\text{d}^{-1}$ ).  
 $\lambda$  mean rate of rainfall occurrence ( $\text{d}^{-1}$ ).  
 $\lambda_w$  latent heat of water vaporization ( $\text{J kg}^{-1}$ ).  
 $\rho_a$  air density ( $\text{kg m}^{-3}$ ).  
 $\rho_w$  water density ( $\text{kg m}^{-3}$ ).  
 $\Phi$  net solar radiation ( $\text{W m}^{-2}$ ).

[37] **Acknowledgments.** This research was supported by the Office of Science (BER) Program, U.S. Department of Energy, and through its Southeast Regional Center (SERC) of the National Institute for Global Environmental Change (NIGEC) under cooperative agreement DE-FC02-03ER63613. We acknowledge the support of the National Science Foundation (United States) through grants Biocomplexity and National Center for Earth Surface Dynamics. We thank Fernando Porte-Agel, P. C. D. Milly, and two anonymous reviewers for their helpful suggestions. We are also grateful to P. A. Fay for providing Konza Prairie data and G. G. Katul for the Duke forest data.

## References

Abramowitz, M., and I. A. Stegun (1965), *Handbook of Mathematical Functions*, Dover, Mineola, N. Y.  
Albertson, J. D., and G. Kiely (2001), On the structure of soil moisture time series in the context of land surface model, *J. Hydrol.*, **243**, 101–119.  
Atkinson, S. E., R. A. Woods, and M. Sivapalan (2002), Climate and landscape controls on water balance model complexity over changing time-scales, *Water Resour. Res.*, **38**(12), 1314, doi:10.1029/2002WR001487.  
Baldocchi, D., and T. Meyers (1998), On using ecophysiological, micro-meteorological and biogeochemical theory to evaluate carbon dioxide, water vapor and trace gas fluxes over vegetation: A perspective, *Agric. For. Meteorol.*, **90**(1–2), 1–25.  
Brubaker, K. L., and D. Entekhabi (1995), An analytic approach to modeling land-atmosphere interaction: 1. Construct and equilibrium behavior, *Water Resour. Res.*, **31**(3), 619–632.  
Brubaker, K. L., and D. Entekhabi (1996), Analysis of feedback mechanisms in land-atmosphere interaction, *Water Resour. Res.*, **32**(5), 1343–1357.  
Budyko, M. I. (1974), *Climate and Life*, Elsevier, New York.  
Campbell, G. S., and J. M. Norman (1998), *An Introduction to Environmental Biophysics*, Springer, New York.  
Cowan, I. R. (1965), Transport of water in the soil-plant-atmosphere system, *J. Appl. Ecol.*, **2**(1), 221–239.  
Cox, D. R., and H. D. Miller (1965), *The Theory of Stochastic Processes*, Methuen, New York.  
Czernik, T., J. Kula, J. Luczka, and P. Hänggi (1997), Thermal rachets driven by Poissonian white noise, *Phys. Rev. E*, **55**(4), 4057–4066.  
Daly, E., and A. Porporato (2006), Probabilistic dynamics of some jump-diffusion systems, *Phys. Rev. E*, **73**, 026108, doi:10.1103/PhysRevE.73.026108.  
Daly, E., A. Porporato, and I. Rodriguez-Iturbe (2004), Coupled dynamics of photosynthesis, transpiration, and soil water balance. Part I: Upscaling from hourly to daily level, *J. Hydrometeorol.*, **5**(3), 546–558.  
D'Odorico, P., L. Ridolfi, A. Porporato, and I. Rodriguez-Iturbe (2000), Preferential states of seasonal soil moisture: The impact of climate fluctuations, *Water Resour. Res.*, **36**(8), 2209–2219.  
Eagleson, P. S. (1978), Climate, soil, and vegetation: 1. Introduction to water balance dynamics, *Water Resour. Res.*, **14**(5), 705–712.  
Farmer, D., M. Sivapalan, and C. Johityangkoon (2003), Climate, soil, and vegetation controls upon the variability of water balance in temperate and semi-arid landscapes: Downward approach to water balance analysis, *Water Resour. Res.*, **39**(2), 1035, doi:10.1029/2001WR000328.  
Federer, C. A. (1979), A soil-plant-atmosphere model for transpiration and availability of soil water, *Water Resour. Res.*, **15**, 555–561.  
Gardiner, G. W. (1990), *Handbook of Stochastic Methods for Physics, Chemistry and the Natural Sciences*, 2nd ed., Springer, New York.  
Guswa, A. J. (2005), Soil-moisture limits on plant uptake: An upscaled relationship for water-limited ecosystems, *Adv. Water Resour.*, **28**, 543–552.  
Guswa, A. J., M. A. Celia, and I. Rodriguez-Iturbe (2002), Models of soil moisture dynamics in ecohydrology: A comparative study, *Water Resour. Res.*, **38**(9), 1166, doi:10.1029/2001WR000826.  
Horsthemke, W., and R. Lefever (1984), *Noise-Induced Transitions: Theory and Applications in Physics, Chemistry, and Biology*, Springer, New York.  
Jones, H. G. (1992), *Plant and Microclimate: A Quantitative Approach to Environmental Plant Physiology*, Cambridge Univ. Press, New York.  
Katul, G. G., C. T. Lai, K. Schafer, B. Vidakovic, J. D. Albertson, D. Ellsworth, and R. Oren (2001), Multiscale analysis of vegetation surface fluxes: From seconds to years, *Adv. Water Resour.*, **24**, 1119–1132.  
Katul, G. G., R. Leuning, and R. Oren (2003), Relationship between plant hydraulic and biochemical properties derived from a steady-state coupled water and carbon transport model, *Plant Cell Environ.*, **26**, 339–350.  
Knapp, A. K., P. A. Fay, J. M. Blair, S. L. Collins, M. D. Smith, J. D. Carlisle, C. W. Harper, M. S. Lett, and J. K. McCarron (2002), Rainfall variability, carbon cycling, and plant species diversity in a mesic grassland, *Science*, **298**, 2202–2205.  
Koster, R. D., and M. J. Suarez (1999), A simple framework for examining the interannual variability of land surface moisture fluxes, *J. Clim.*, **12**, 1911–1917.  
Laio, F., A. Porporato, L. Ridolfi, and I. Rodriguez-Iturbe (2001), Plants in water-controlled ecosystems: Active role in hydrologic processes and response to water stress: II. Probabilistic soil moisture dynamics, *Adv. Water Resour.*, **24**(7), 707–723.  
Laio, F., A. Porporato, L. Ridolfi, and I. Rodriguez-Iturbe (2002), On the seasonal dynamics of mean soil moisture, *J. Geophys. Res.*, **107**(D15), 4272, doi:10.1029/2001JD001252.  
Milly, P. C. D. (1993), An analytic solution of the stochastic storage problem applicable to soil-water, *Water Resour. Res.*, **29**, 3755–3758.  
Milly, P. C. D. (1994), Climate, soil water storage, and the average annual water balance, *Water Resour. Res.*, **30**, 2143–2156.  
Noy-Meir, I. (1973), Desert ecosystems: Environment and producers, *Annu. Rev. Ecol. Syst.*, **4**, 25–44.  
Parlange, M. B., and G. G. Katul (1992), Estimation of the diurnal variation of potential evaporation from a wet bare soil surface, *J. Hydrol.*, **132**, 71–89.  
Porporato, A., and I. Rodriguez-Iturbe (2002), Ecohydrology—A challenging multidisciplinary research perspective, *J. Hydrol. Sci.*, **47**(5), 811–821.Porporato, A., F. Laio, L. Ridolfi, and I. Rodriguez-Iturbe (2001), Plants in water-controlled ecosystems: Active role in hydrologic processes and response to water stress. III. Vegetation water stress, *Adv. Water Resour.*, 24(7), 725–744.

Porporato, A., E. Daly, and I. Rodriguez-Iturbe (2004), Soil water balance and ecosystem response to climate change, *Am. Nat.*, 164(5), 625–632.

Potter, N. J., L. Zhang, P. C. D. Milly, T. A. McMahon, and A. J. Jakeman (2005), Effects of rainfall seasonality and soil moisture capacity on mean annual water balance for Australian catchments, *Water Resour. Res.*, 41, W06007, doi:10.1029/2004WR003697.

Ramirez, J. A., M. T. Hobbins, and T. C. Brown (2005), Observational evidence of the complementary relationship in regional evaporation lends strong support for Bouchet's hypothesis, *Geophys. Res. Lett.*, 32, L15401, doi:10.1029/2005GL023549.

Rodriguez-Iturbe, I., and A. Porporato (2004), *Ecohydrology of Water-Controlled Ecosystems: Soil Moisture and Plant Dynamics*, Cambridge Univ. Press, New York.

Rodriguez-Iturbe, I., A. Porporato, L. Ridolfi, V. Isham, and D. R. Cox (1999), Probabilistic modeling of water balance at a point: The role of climate, soil and vegetation, *Proc. R. Soc. London, Ser. A*, 455, 3789–3805.

Schenzle, A., and H. Brand (1979), Multiplicative stochastic processes in statistical physics, *Phys. Rev. A*, 20(4), 1628–1647.

Szilagyi, J. (2001), On Bouchet's complementary hypothesis, *J. Hydrol.*, 246, 155–158.

Van Kampen, N. G. (1981), Ito versus Stratonovich, *J. Stat. Phys.*, 24(1), 175–187.

Wetzel, P. J., and J. T. Chang (1987), Concerning the relationship between evapotranspiration and soil-moisture, *J. Clim. Appl. Meteorol.*, 26, 18–27.

---

E. Daly and A. Porporato, Department of Civil and Environmental Engineering, Duke University, 127 Hudson Hall, Box 90287, Durham, NC 37708-0328, USA. (edaly@duke.edu; amilcare@duke.edu)