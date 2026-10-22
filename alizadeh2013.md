## Coupled stochastic soil moisture simulation-optimization model of deficit irrigation

Hosein Alizadeh<sup>1</sup> and S. Jamshid Mousavi<sup>1</sup>

Received 23 May 2012; revised 26 April 2013; accepted 29 April 2013; published 16 July 2013.

[1] This study presents an explicit stochastic optimization-simulation model of short-term deficit irrigation management for large-scale irrigation districts. The model which is a nonlinear nonconvex program with an economic objective function is built on an agrohydrological simulation component. The simulation component integrates (1) an explicit stochastic model of soil moisture dynamics of the crop-root zone considering interaction of stochastic rainfall and irrigation with shallow water table effects, (2) a conceptual root zone salt balance model, and (3) the FAO crop yield model. Particle Swarm Optimization algorithm, linked to the simulation component, solves the resulting nonconvex program with a significantly better computational performance compared to a Monte Carlo-based implicit stochastic optimization model. The model has been tested first by applying it in single-crop irrigation problems through which the effects of the severity of water deficit on the objective function (net benefit), root-zone water balance, and irrigation water needs have been assessed. Then, the model has been applied in Dasht-e-Abbas and Ein-khosh Fakkeh Irrigation Districts (DAID and EFID) of the Karkheh Basin in southwest of Iran. While the maximum net benefit has been obtained for a stress-avoidance (SA) irrigation policy, the highest water profitability has been resulted when only about 60% of the water used in the SA policy is applied. The DAID with respectively 33% of total cultivated area and 37% of total applied water has produced only 14% of the total net benefit due to low-valued crops and adverse soil and shallow water table conditions.

**Citation:** Alizadeh, H., and S. J. Mousavi (2013), Coupled stochastic soil moisture simulation-optimization model of deficit irrigation, *Water Resour. Res.*, 49, 4100–4113, doi:10.1002/wrcr.20282.

### 1. Introduction

[2] *Deficit irrigation* (DI), an irrigation practice whereby water supply is reduced below maximum level and mild stress is allowed with minimal effect on yield [Kirda, 2002], is known as a demand management measure toward dealing with the water scarcity and improving water productivity. Under conditions of droughts and scarcity of water supply, DI may lead to greater economic gains than maximizing the yield per unit water volume applied.

[3] Several efforts have been made in using mathematical optimization models of irrigation management including two categories of models, that is, single-crop (SC) and multicrop (MC; multifield). In a SC model, the problem is either to determine an optimal applied water (intensive irrigation), an optimal cultivated area (extensive irrigation) [English *et al.*, 2002], or the intraseasonal water application for deficit (extensive) irrigation [Bras and Cordova, 1981]. Mathemati-

cal programming techniques have been also used in MC problems to optimize the performance of an entire irrigation field as a single planning unit. The problems have addressed determining at least one of the aspects of cropping pattern, irrigation scheduling, and resource (surface reservoir and/or groundwater aquifer) operation policies.

[4] For intensive irrigation, an economic objective function of the net benefit resulting from irrigation has been considered [Tsakiris and Spiliotis, 2006]; but for DI, an objective function of either maximization of net benefit or maximization of crop yield has been used [e.g., Vedula *et al.*, 2005]. More comprehensive models of irrigation scheduling include soil moisture dynamics equations [e.g., Ghahraman and Sepaskhah, 2002]. To determine the allocation policies from a surface or groundwater reservoir, the reservoir's water balance equations combined with soil water dynamics equations may also be considered [e.g., Teixeira and Mariño, 2002].

[5] Irrigation planning and management becomes more complicated due to uncertainties on agrohydrological variables (e.g., rainfall, potential evapotranspiration, and crop and soil properties), and socioeconomic factors (e.g., crop prices, production costs, farmers behavior, and political forces). From another point of view, the sources of uncertainty may be classified as temporal variability, spatial heterogeneity, measurement errors, human's behavior complexity, etc. Some socioeconomic factors are mainly

<sup>1</sup>Department of Civil and Environmental Engineering, Amirkabir University of Technology (Polytechnic of Tehran), Tehran, Iran.

Corresponding author: S. J. Mousavi, Department of Civil and Environmental Engineering, Amirkabir University of Technology (Polytechnic of Tehran), Tehran 15875-4413, Iran. (jmosavi@aut.ac.ir)under long-term temporal variation. Also, some of the factors caused by spatial heterogeneity, which have been considered in a few irrigation management studies [e.g., Russo, 1986; Gates and Grismer, 1989], are only influential in small-scale problems; so they progressively become less important as the spatial scale of the problem increases [Rodriguez-Iturbe et al., 2006]. Rhenals and Bras [1981] have shown that the effect of the uncertainty of potential evapotranspiration on irrigation performance measures could be apparently minimal in a semiarid climate such as Lower South Platte, Colorado.

[6] Rainfall, a relevant part in supplying the agricultural water requirement, is under uncertainty. By assessing different hydroclimatic conditions, Daly and Porporato [2006] have shown that the impact of rainfall temporal variability on soil moisture dynamics is much more significant than that of potential evapotranspiration, whose fluctuations do not considerably affect the soil moisture statistical properties. Therefore, attempts have been taken to consider rainfall uncertainty in both long-term and short-term irrigation optimization models. Stochastic dynamic programming (SDP) models [e.g., Dudley and Burt, 1973] and the detailed soil moisture dynamics simulation models [e.g., Ahmed et al., 1976; Ines et al., 2006] have been developed to precisely survey SC farm problems. However, these models are not applicable in MC problems due to being computationally intensive.

[7] Most of the MC models used for long-term irrigation planning consist of a long-term stochastic optimization constituent, for example, SDP, and a short-term deterministic optimization module, for example, linear programming, nonlinear programming, or dynamic programming [e.g., Dudley et al., 1976; Ghahraman and Sepaskha, 2002; Vedula and Kumar, 1996]. The long-term part seeks for the interseasonal water allocation policies, while the short-term model is about intercrop and intraseason optimal water allocations. In this regard, Alizadeh and Mousavi [2013a] developed a model coupling Particle Swarm Optimization (PSO) and Monte Carlo simulation for stochastic-order-based design of a reservoir-irrigation district system. Moreover, Positive Mathematical Programming has been used for calibration of the agricultural-production and resource-use models with parameters that are implicit in the observed land allocation decisions [e.g., Howitt, 1995; Paris and Howitt, 1998].

[8] The computational burden of Monte Carlo-based approaches has led to a class of optimization models in which an explicit stochastic simulation component of soil moisture dynamics is used. Bras and Cordova [1981] presented a short-term SDP model for determining optimal intraseasonal DI policies for a SC farm based on a stochastic physically based soil moisture model considering rainfall uncertainty as a Poisson process. Ganji et al. [2006] developed a stochastic model of short-term DI optimization based on an explicit stochastic simulation model using indicator functions.

[9] Recently, more realistic explicit stochastic models of soil moisture dynamics have been introduced [Rodriguez-Iturbe and Porporato, 2004], which have not yet been used in an optimization model of irrigation management. This paper presents a new explicit stochastic optimization model of short-term MC DI management in the form of a

simulation-optimization model with an economic objective function. The agrohydrological simulation model will estimate the actual crop yield and irrigation water requirement based on soil water and salt balance of root zone. It also takes the effects of shallow water table and different irrigation methods into account. Then, the PSO algorithm, linked to the agrohydrological simulation model, will solve the resulting nonlinear nonconvex program for different SC and MC problems.

## 2. Model Formulation

[10] This section is about presenting a short-term stochastic simulation-optimization model of DI for large-scale irrigation districts. The model aims to optimally allocate a predetermined amount of water available between crops in a number of irrigation districts over a growing season considering stochastic rainfall in supplying part of crop water requirement. The size of each irrigation district is so that it can be assumed almost lumped in terms of climate and soil and shallow water table conditions. Each irrigation district is divided into some smaller SC irrigation units with their own irrigation and drainage technology and operation.

[11] The model addresses the short-term irrigation management of a large-scale system, so the uncertainty of the factors with less significant variations over a short-term horizon has not been considered. Moreover, those sources of uncertainty due to spatial heterogeneity such as uncertainty of soil properties, which are more important in spatially small-scale systems, have not been taken into account. Therefore, among all uncertain factors, only the temporal variability of rainfall has been taken into consideration.

### 2.1. Mathematical Program

[12] The model is a mathematical program with an economic objective function subject to irrigation and drainage management constraints. The objective function, equation (1), is maximization of the summation over all irrigation units of the gross economic income subtracted by the costs which include fixed agricultural-production costs (seeds, pesticides, fertilizers, field machinery, labor, and operation expenses), fixed irrigation-related costs (equipments maintenance and labor costs), and variable irrigation-related costs (fuel for pumping and price paid for off-farm water).

[13] Irrigation and drainage-related decision variables of the program are classified into two types of intervention point and target level. Inequality (2) indicates that the intervention-point variables are bounded variables; also the next two constraints, that is, (3) and (4), are about the target-level decision variables. Inequality (5) is about limitation of the depth of each irrigation application to a minimum threshold which depends on the type of the used technology for traditional irrigation, that is, surface or sprinkler. While inequality (6) is about considering a lower bound for the actual crop yield of each irrigation unit, inequality (7) limits the total volume of applied water to the total available water in the season.

[14] The model formulation may be written as follows:

$$\max f(\vec{s}, \vec{\hat{s}}) = \sum_u \{Pe_u A_u \bar{Y}_{a,u}(\vec{s}_u, \vec{\hat{s}}_u) - (C_{0,u} + C_{1,u})A_u - C_{2,u} \bar{V}_{t,u}(\vec{s}_u, \vec{\hat{s}}_u)\} \quad (1)$$subject to

$$s_{c,u} \leq \tilde{s}_u \leq s_u^* \quad , \forall u \in U \quad (2)$$

$$\hat{s}_u = \tilde{s}_u \quad , \forall u \in MU \quad (3)$$

$$s_u^* \leq \hat{s}_u \leq s_s \quad , \forall u \in TU \quad (4)$$

$$d_{\min,u} \leq n_u Z_{r,u} \times (\hat{s}_u - \tilde{s}_u) \quad , \forall u \in TU \quad (5)$$

$$Y_{\min,u} \leq \bar{Y}_{a,u}(\tilde{s}_u, \hat{s}_u) \quad , \forall u \in U \quad (6)$$

$$\sum_u \bar{V}_{t,u}(\tilde{s}_u, \hat{s}_u) \leq TW \quad (7)$$

where the model's parameters and variables are

- $(\tilde{s}, \hat{s})$  the control matrix consisting of irrigation and drainage parameters which are typical values of relative soil moisture;
- $\tilde{s}$  the relative soil moisture point of irrigation intervention (briefly intervention point) consisting of  $\tilde{s}_u$  entries; more details about these parameters are described in section 2.3.1;
- $\hat{s}$  the relative soil moisture level of irrigation target (briefly target level) consisting of  $\hat{s}_u$  elements; more details about these parameters are described in section 2.3.1;
- $u$  index standing for an irrigation unit;
- $Pe_u$  the crop price per unit mass;
- $A_u$  the cultivation area;
- $\bar{Y}_{a,u}$  the expected value (e.v.) of actual crop yield (per unit area) which depends on the irrigation-drainage decision variables ( $\tilde{s}_u$  and  $\hat{s}_u$ ) as will be discussed in sections 2.2 and 2.3.2;
- $C_{0,u}$  fixed agricultural-production cost per unit cultivated area;
- $C_{1,u}$  fixed irrigation-related cost per unit cultivated area;
- $C_{2,u}$  irrigation-related cost per unit water applied;
- $\bar{V}_{t,u}$  e.v. of seasonal water volume withdrawn from the source to apply to an irrigation unit;
- $s_{c,u}$  the relative soil moisture value below which soil will never dry out because the potential capillary flux becomes equal to the actual evapotranspiration [Vervoort and van der Zee, 2008];
- $s_u^*$  the relative soil moisture value characterizing the point of incipient stomatal closure below which the rate of transpiration is reduced and the crop will experience water stress [Porporato et al., 2001];
- $s_s$  relative soil moisture value at soil saturation point;
- $U$  set of all irrigation units;
- $MU$  subset of the irrigation units with microirrigation technology;
- $TU$  subset of the irrigation units with traditional irrigation technology;
- $d_{\min,u}$  a minimum value for each irrigation application depth;
- $n_u$  soil porosity;
- $Z_{r,u}$  active soil depth incorporating the most of crop root of the unit;

- $Y_{\min,u}$  minimum acceptable actual yield per unit cultivation area; and
- $TW$  total available water in the season.

[15] The above mathematical program is approached by a simulation-optimization algorithm consisting of simulation and optimization parts as illustrated in Figure 1. The simulation model is a combination of three modules. In the following sections, more details are presented about each of the modules and their interconnections.

[16] Random rainfall will cause the important variables of the above mathematical program, that is, actual crop yield and irrigation requirement, to become random. So we develop a methodology to analytically derive expressions for e.v.s of crop yield,  $\bar{Y}_{a,u}$ , and irrigation requirement,  $\bar{V}_{t,u}$ .

## 2.2. Crop Yield Module

[17] This section presents an approach to estimate the e.v. of the actual crop yield in an irrigation unit under stochastic rainfall based on the simple crop yield model of *FAO* [1998] expressed as follows:

$$Y_a(\tilde{s}, \hat{s}) = Y_p \times (1 - k_1 \times \zeta_{os}(\tilde{s}, \hat{s})) \times (1 - k_2 \times \pi(\tilde{s}, \hat{s})) \quad (8)$$

where  $Y_p$  represents the potential crop yield per unit cultivated area and  $k_1$  and  $k_2$  are, respectively, the factors of crop sensitivity to water stress and salt stress.  $\zeta_{os}$  is an overseason water stress index which depends on soil moisture dynamics. It is defined as  $\zeta_{os} = 1 - CET_a(\tilde{s}, \hat{s}) / CET_p$ , where  $CET_p$  and  $CET_a$  are, respectively, cumulative potential and actual evapotranspiration over a growing season. Note that  $CET_a$  depends on the soil moisture, so does it on the irrigation and drainage decision variables.

[18] The salt stress index,  $\pi$ , is defined as follows:

$$\pi(\tilde{s}, \hat{s}) = \begin{cases} 0, & C_e(\tilde{s}, \hat{s}) \leq C_{e,T} \\ C_e(\tilde{s}, \hat{s}) - C_{e,T}, & C_e(\tilde{s}, \hat{s}) > C_{e,T} \end{cases} \quad (9)$$

Figure 1. Schematic view of simulation-optimization model of deficit irrigation (DI).where  $C_e$  is the salt concentration of the saturation extract in the root zone which depends on the components of the soil moisture balance which are described in details in section 2.3.4. Therefore,  $C_e$  will be a function of the decision variables. Also,  $C_{e,T}$  is a threshold value of salt concentration above which the crop yield is less than the potential yield.

[19] Random rainfall causes the interdependent variables of cumulative actual evapotranspiration, overseason water stress index, and actual crop yield to become random too. The randomness of these variables can be considered through the e.v. of the overseason water stress index,  $\bar{\zeta}_{os} = E\{1 - CET_a/CET_p\}$ , estimation of which is explained in section 2.3.2, where  $E\{\cdot\}$  is the e.v. operator. Effects of other sources of uncertainty on the actual crop yield due to climatic forcings (temperature, wind speed, and humidity) and management-related factors (fertilizer, pesticide, farmers behavior, etc.) can be taken into account via the potential evapotranspiration ( $CET_p$ ), the potential crop yield ( $Y_p$ ), and the water stress sensitivity factor ( $k_1$ ). Seeking simplicity, we assume that the mentioned variables ( $\zeta_{os}$ ,  $CET_p$ ,  $Y_p$ , and  $k_1$ ) are statistically independent; therefore, one can use equation (8) for the e.v. of actual crop yield as follows:

$$\bar{Y}_a(\tilde{s}, \hat{s}) = \bar{Y}_p \times (1 - \bar{k}_1 \times \bar{\zeta}_{os}(\tilde{s}, \hat{s})) \times (1 - k_2 \times \pi(\tilde{s}, \hat{s})) \quad (10)$$

where bar sign stands for the operator of the e.v. Finally,  $\bar{Y}_{a,u}$  can be estimated through particularizing the above equation for different irrigation units. The time horizon of the optimization model, represented by equations (1)–(7), is a growing season. However, the main variables of interest, that is, actual crop yield and seasonal irrigation requirement, are estimated based on a daily representation of soil moisture balance as described in the following section.

## 2.3. Soil Water Module

### 2.3.1. Physically Based Stochastic Soil Moisture Process

[20] This section is about how to analytically derive explicit expressions for the probability density function (pdf) of the soil moisture subject to random loading of rainfall while considering the influential processes of interception, runoff, leakage, and evapotranspiration as well as the effects of both irrigation and shallow water table.

[21] The goal is achieved using a physically based stochastic soil moisture model [Rodriguez-Iturbe *et al.*, 1999]. In this approach, soil moisture dynamics at a daily time scale is modeled by treating the active soil of crop-root zone as a reservoir with an effective storage capacity that is filled by intermittent rainfall, demand-based irrigation events, and capillary fluxes. Assuming vertically averaged conditions and in the absence of lateral redistribution, one can express the soil water balance dynamics of root zone by the following equation:

$$nZ_r \frac{ds(t)}{dt} = R(t) + I(s(t)) + CF(s(t)) - L(s(t)) - ET(s(t)) - Q(s(t)) \quad (11)$$

where  $n$  is the soil porosity,  $Z_r$  is the active soil depth where most of the root is located, and  $s = (\theta - \theta_r)/n$  is the

relative soil moisture which represents the crop-accessible water.  $\theta$  is volumetric water content and  $\theta_r$  is residual water content at wilting point. Therefore,  $s$  varies between 0 at wilting point and  $s_s = 1 - \theta_r/n$  at soil saturation point. The system inputs are rainfall,  $R(t)$ , infiltrated irrigation,  $I(s(t))$ , and capillary upflux from shallow water table,  $CF(s(t))$ . The soil moisture losses or the system outputs are leakage due to both rainfall and irrigation,  $L(s(t))$ , actual evapotranspiration,  $ET(s(t))$ , and surface runoff caused by rainfall,  $Q(s(t))$ , where  $t$  represents time index.

[22] Rainfall is modeled as an instantaneous event following a marked Poisson process of rate  $\lambda$  and exponentially distributed depths with mean  $\alpha$  [Rodriguez-Iturbe and Porporato, 2004]. Interception is modeled by purging rainfall from canopy storage in the form of reduced frequency of the rainfall, that is,  $\lambda'$  [Laio *et al.*, 2001].

[23] The infiltrated irrigation,  $I(s(t))$ , equals the total amount of water withdrawn from the source minus water losses which are considered through an efficiency factor. In other words, the infiltrated irrigation consists of two parts. The first part effectively meets the evapotranspiration demand of the crop and the second part is associated with the irrigation-related leakage. We have used a generalized scheme of demand-based irrigation [Vico and Porporato, 2011] which can distinguish between often-used methods, including the traditional irrigation (surface and sprinkler) and the modern microirrigation techniques. The scheme also provides a framework for considering a range of irrigation strategies from rainfed agriculture to stress-avoidance (SA) irrigation covering different levels of DI.

[24] In this scheme, there are two key parameters by which the irrigation strategies are characterized. The first parameter is called the intervention point,  $\tilde{s}$ , that is a typical value of the relative soil moisture. In a demand-based irrigation, an application is triggered when the soil moisture reaches  $\tilde{s}$ . This parameter corresponds to the percentage of allowable water depletion which is often used in crop models. The second parameter,  $\hat{s}$ , is a target level for the relative soil moisture that needs to be restored by each irrigation application. The difference between the target level and the intervention point,  $\hat{s} - \tilde{s}$ , is proportional to the depth of water supplied by each irrigation application, where the depth of each application equals  $nZ_r(\hat{s} - \tilde{s})$ .

[25] In a SA irrigation strategy, an irrigation application is triggered whenever the soil moisture reaches the point of incipient closure,  $\tilde{s} = s^*$ . Meanwhile, irrigation strategies with the intervention points below the point of incipient closure,  $\tilde{s} < s^*$ , are known as DI. The rainfed agriculture is about when  $\tilde{s}, \hat{s} \rightarrow 0$ . For traditional irrigation, the target level needs to be larger than the intervention point.

[26] The traditional irrigation often entails an application that brings the soil moisture back to the field capacity or a level slightly above it due to salt control considerations. However, it could be implemented by the following two contrasting technologies: (1) surface irrigation which is particularly suited for larger applications (exceeding 50 mm per treatment) and (2) sprinkler or spray systems which can mimic the rainfall events with a depth as small as 5 mm in the case of center pivot systems; therefore, a constraint on the minimum irrigation depth,  $d_{min,u}$ , can be used characterizing the type of traditional irrigation technology as mentioned before in section 2.1 through inequality (5).Also, a microirrigation technology corresponds to the case in which  $\tilde{s} = \hat{s}$  (equation (3)). According to the generalized irrigation scheme described and by taking the two mentioned parameters as decision variables of the optimization model presented in section 2.1, one can derive optimal irrigation strategies ranging from rainfed agriculture to SA irrigation. Also, for the cases where the salt leaching through extra leakage from irrigation is essential, the optimum value of the target level obtained by the model determines the optimum amount of water needed for leaching.

[27]  $CF(s(t))$  and  $L(s(t))$  terms in equation (11) represent the interaction between root zone and groundwater which includes two mutually exclusive components. The first one is the capillary rise from groundwater table to the root zone that occurs during interstorm periods, whereas the second one is the leakage from root zone to groundwater which takes place during and immediately after storms and also irrigation applications. Agricultural ecosystems under irrigation usually encounter the presence of shallow groundwater caused by huge amount of water applied for irrigation and then drained from the root zone. Shallow water table can have both positive and negative effects on the crop yield function; while it could contribute to supplying part of the crop water requirement by means of capillary flux [Kandil and Willardson, 1992], it could prevent a sufficient aeration needed for crop-root development [Wright and Sands, 2001] and also could cause a salt accumulation in root zone because of an upflux from highly saline groundwater. Accordingly, extra water intended for salt leaching should be applied to prevent or minimize a decrease in yield due to salinity.

[28] By linearizing the capillary flux-soil moisture relation suggested by Vervoort and van der Zee [2008] and assuming a time average value for the water table depth, we can derive a new analytical relation between the capillary flux rate and the relative soil moisture as follows:

$$CF(s) = \begin{cases} m, & s_c \leq s \leq s^* \\ m \frac{s_e - s}{s_e - s^*}, & s^* < s \leq s_e \\ 0, & s_e < s \leq s_s. \end{cases} \quad (12)$$

where  $m = K_s G$  is the maximum capillary flux for the average shallow groundwater depth ( $Z$ ).  $K_s$  is the saturated hydraulic conductivity and  $G = \alpha_e (h_b / (Z - Z_r))^{2+3/b}$  is a parameter in which hydraulic properties of soil are encapsulated.  $b$  and  $\alpha_e = (5b + 6) / (2b + 6)$  are the parameters of the capillary flux function [Eagleson, 1978], and  $h_b$  is the bubbling pressure.  $s_c = ms^* / ET_p$  ( $ET_p$  is the maximum rate of daily evapotranspiration) is an specific value of the relative soil moisture below which soil will never dry out, because the potential capillary flux becomes equal to the actual evapotranspiration. It is assumed that capillary fluxes supply a sufficient moisture, so  $s_c > 0$ ; while they are small enough to maintain the maximum evapotranspiration, so  $s_c < s^*$ . The effective field capacity ( $s_e = ((Z - Z_r) / h_b)^{-1/b} - \theta_r / n$ ), which is a parameter depending on the water table depth and soil properties, represents the relative soil moisture level at which soil shifts from the drainage behavior to the capillary uptake condition and vice versa. It will be discussed in section 2.3.5 that the average shallow water table depth is assumed to be always below the root zone depth, that is,  $Z > Z_r$ .

[29] Leakage is considered in a simplified manner as a function of the relative soil moisture [Rodriguez-Iturbe et al., 1999] in the form of

$$L(s) = \begin{cases} 0, & s \leq s_e \\ K_s \frac{s - s_e}{s_s - s_e}, & s > s_e. \end{cases} \quad (13)$$

[30] The daily rate of actual evapotranspiration varies over time as the soil moisture changes. However, the potential ET is assumed to be time invariant. This assumption is made to provide with the model simplicity and its analytical tractability because of its secondary effect on the model results compared to rainfall [Vico and Porporato, 2010]. A piecewise linear dependence between actual evapotranspiration and soil moisture has been observed through empirical evidence [Hale and Orcutt, 1987]. As a result, the actual evapotranspiration increases basically from zero at wilting point ( $s = 0$ ) up to a maximum rate  $ET_p$  at the point of incipient stomatal closure ( $s^*$ ), after which it remains constantly at  $ET_p$  for higher soil moisture values. Therefore, actual evapotranspiration, as a function of soil moisture, can be expressed as follows:

$$ET(s) = \begin{cases} ET_p \frac{s}{s^*}, & 0 \leq s < s^* \\ ET_p, & s^* \leq s. \end{cases} \quad (14)$$

[31] One of the main components of soil water losses is runoff caused by either rainfall or irrigation. The irrigation-related part of runoff can implicitly be considered through an efficiency factor, while the rainfall-related part,  $Q(s(t))$ , is modeled in a simplified manner by assuming that it takes place instantaneously (at a daily time scale) whenever the soil moisture reaches the saturation level, that is,  $s = s_s$ . Combining the actual evapotranspiration, capillary flux, and leakage functions, one can write the soil water loss function as follows:

$$\rho(s) = \frac{ET(s) + L(s) - CF(s)}{nZ_r} = \frac{1}{nZ_r} \begin{cases} ET_p \frac{s}{s^*} - m, & \tilde{s} \leq s \leq s^* \\ ET_p - m \frac{s_e - s}{s_e - s^*}, & s^* < s \leq s_e \\ ET_p + K_s \frac{s - s_e}{s_s - s_e}, & s_e < s \leq s_s. \end{cases} \quad (15)$$

[32] Rainfall randomness is propagated through the soil moisture dynamics and causes soil moisture to become a stochastic process. Consequently, Chapman-Kolmogorov equation, which is a differential equation defining time evolution of stochastic processes, can be used for describing the soil moisture process subject to rainfall random input. Under the stochastic steady-state condition, one can derive the pdf of the soil moisture considering the general form of the loss function for respectively microirrigation and traditional irrigation [Vico and Porporato, 2011] as follows:

$$p_m(s) = \frac{C_m}{\rho(s)} \exp \left( -\gamma \times s + \lambda' \int_{\tilde{s}}^s \frac{du}{\rho(u)} \right), \quad (16)$$$$p_t(s) = \frac{C_t}{\rho(s)} \exp \left( - \int_{\bar{s}}^s \left( \gamma - \frac{\lambda'}{\rho(u)} \right) du \right) \times \left\{ 1 + \int_{\bar{s}}^s (\gamma \cdot H(\hat{s} - u) - \delta(\hat{s} - u)) \exp \left( \int_{\bar{s}}^u \left( \gamma - \frac{\lambda'}{\rho(y)} \right) dy \right) du \right\}, \quad (17)$$

[33] The pdf of the soil moisture for microirrigation case is of the mixed type and contains an atom of probability as

$$p_0 = \frac{C_m}{\lambda'} e^{-\gamma \bar{s}}. \quad (18)$$

[34] In equations (16)–(18) and also later in equation (19),  $t$  and  $m$  are indices corresponding to respectively traditional irrigation and microirrigation,  $\rho(\cdot)$  is the loss function and  $H(\cdot)$  and  $\delta(\cdot)$  are Heaviside and Dirac delta functions, respectively. Also  $1/\gamma = \alpha/nZ_r$  is normalized mean depth of daily rainfall events.  $C_t$  and  $C_m$  are normalizing constants derived by using the axiom of probability as

$$\int_{\bar{s}}^{s_s} p_t(u) du = 1 \quad p_0 + \int_{\bar{s}}^{s_s} p_m(u) du = 1 \quad (19)$$

### 2.3.2. Overseason Water Stress Index

[35] As mentioned before through equation (10), estimation of the e.v. of the actual crop yield ( $\bar{Y}_a$ ), requires that the e.v. of the overseason water stress index ( $\bar{\zeta}_{os}$ ) be known. This requirement calls for analyzing the transient behavior of the stochastic soil moisture process as well as modeling the cumulative actual evapotranspiration. This will be a rather difficult goal to achieve via explicit methods; therefore, some simplifying assumptions should be made.

[36] The first assumption is replacing the e.v. of an overseason water stress index,  $\bar{\zeta}_{os}$ , with the e.v. of an instantaneous water stress index at stochastic steady-state condition,  $\bar{\zeta}_i$ . The instantaneous water stress index can be defined based on the daily rate of actual evapotranspiration,  $ET(s)$ , and the potential evapotranspiration,  $ET_p$ , as

$$\zeta_i(s) = \begin{cases} 1 - \frac{ET(s)}{ET_p} = 1 - \frac{s}{s^*}, & 0 \leq s < s^* \\ 0, & s^* \leq s, \end{cases} \quad (20)$$

[37] Although the overseason and the instantaneous water stress indices are not identical, we can verify that their e.v.s are almost the same. Therefore, the e.v. of overseason water stress index has been derived by applying the expectation operator to equation (20) as follows:

$$\bar{\zeta}_{os} = \bar{\zeta}_i = \int_{\bar{s}}^{s^*} (1 - s/s^*) p(s) ds, \quad (21)$$

where  $p(s)$  represents the pdf of soil moisture including  $p_t(s)$  and  $p_m(s)$ . Combining equations (21) and (10), one

can find an expression for e.v. of actual crop yield. Although in general, there are nonlinear forms of the relationship between crop yield and actual evapotranspiration [e.g., *Hexem and Heady*, 1978], we have derived such an expression by assuming a linear relationship as defined in FAO crop model. This is of course a simplifying assumption made for analytical tractability.

### 2.3.3. Infiltrated Irrigation Water

[38] By defining an efficiency factor as the ratio of infiltrated irrigation water at the farm to total water withdrawn from the source, one can write the e.v. of total water requirement volume as follows:

$$\bar{V}_I(\bar{s}, \hat{s}) = \bar{V}_I(\bar{s}, \hat{s}) A / \mu \quad (22)$$

where  $\bar{V}_I$  is the e.v. of total volume per unit cultivated area (total depth) of infiltrated irrigation water over a growing season,  $A$  is cultivation area, and  $\mu$  is the efficiency factor. The efficiency factor ( $\mu$ ), which should be estimated based on field measurements, implicitly includes the effects of water losses in delivery and distribution systems and water losses at farm. The infiltrated water ( $\bar{V}_I$ ) consists of the following two essential parts: (1) the part which participates effectively in meeting crop water requirement (evapotranspiration) and (2) the remaining water which is percolated down through the soil that causes salt leaching from the root zone.

[39]  $\bar{V}_{I,u}$ , whose value is needed in the evaluation of the objective function and also the total water requirement constraint (equation (1) and inequality (7)) can be estimated through particularizing  $\bar{V}_I$  in equation (22) for different irrigation units.

[40] To estimate the e.v. of the infiltrated irrigation depth ( $\bar{V}_I$ ) (as well as overseason water stress index), we need to make a simplifying assumption based on which the stochastic transient behavior of the soil moisture process over a growing season is replaced by a stochastic steady-state condition. To assess how valid this assumption is, we compared the two transient and steady-state water stress indices, that is,  $\bar{\zeta}_{trs}$  and  $\bar{\zeta}_{std}$  as well as two e.v.s of the net irrigation requirement, that is, the transient ( $\bar{V}_{trs}$ ) and the steady-state ( $\bar{V}_{std}$ ) e.v.s of the net irrigation requirement, under different climate, soil-type, and crop-root-depth conditions.  $\bar{\zeta}_{std}$  and  $\bar{V}_{std}$  were estimated by the analytical expressions, that is, equations (21) and (23), while  $\bar{\zeta}_{trs}$  and  $\bar{V}_{trs}$  were evaluated by an equivalent Monte Carlo-based numerical model considering the initial soil moisture parameter explicitly.

[41] The numerical model was the same as the analytical model, that is, explicit model, with respect to soil moisture dynamics (equation (11)) and the crop yield equation (equation (8)); but considered rainfall uncertainty differently through a Monte Carlo simulation approach. Therefore, different rainfall time series (realizations) were generated using the marked stochastic Poisson process fitted to historical rainfall time series. Then, the soil moisture process was simulated for each realization. Finally, the simulated processes were statistically analyzed to obtain  $\bar{\zeta}_{trs}$  and  $\bar{V}_{trs}$ . The results, not presented herein, confirmed the credibility of the steady-state assumption during the growing season with respect toestimation of e.v.s of net irrigation requirement and actual crop yield. However, this would be valid only in humid regions or wet season in arid and semiarid regions when rainfall plays a key role.

[42] Using the crossing properties of soil moisture process, *Vico and Porporato* [2011] have derived the e.v. of the infiltrated irrigation depth as follows:

$$\bar{V}_I(\tilde{s}) = nZ_r\rho(\tilde{s})p_0T_s \quad (23)$$

for microirrigation and

$$\bar{V}_I(\tilde{s}, \hat{s}) = nZ_r(\hat{s} - \tilde{s})\rho(\tilde{s})p_I(\tilde{s})T_s \quad (24)$$

for traditional irrigation, where  $T_s$  is the duration of the growing season and other parameters have been already defined. It is worth mentioning that analytical expressions have been derived for probability density (mass) function of irrigation requirement [*Alizadeh and Mousavi*, 2013b].

[43] Given that using soil water module the irrigation requirement can be estimated at seasonal time scale, the model will not provide any information on optimal intraseasonal irrigation water allocations. Meanwhile, one can use another simulation or optimization model which incorporates intraseasonal time steps to obtain water application across months based on the obtained optimal irrigation policy.

#### 2.3.4. Soil Moisture Balance Components

[44] Under the assumption of stochastic steady-state condition, one can express the soil moisture balance over a growing season from equation (11) as  $\bar{V}_R + \bar{V}_I + \bar{V}_{CF} = \bar{V}_L + \bar{V}_{ET} + \bar{V}_Q$ , where the terms on the left-hand side (l.h.s.) of the equation correspond to input components of water to the root zone and those on the right-hand side (r.h.s.) are associated with the output components. The average depth of total rainfall over the season ( $\bar{V}_R$ ) equals  $\alpha\lambda'T_s$  [*Rodriguez-Iturbe et al.*, 1999], while the average total infiltrated irrigation depth can be estimated using equations (23) and (24). The other terms of the balance equation can be derived by using the e.v. operator as follows:

$$\begin{aligned} \bar{V}_{CF}(\tilde{s}, \hat{s}) &= T_s \int_{\tilde{s}}^{s_e} CF(s)p(s)ds \\ \bar{V}_L(\tilde{s}, \hat{s}) &= T_s \int_{s_e}^{s_s} L(s)p(s)ds \\ \bar{V}_{ET}(\tilde{s}, \hat{s}) &= T_s \int_{\tilde{s}}^{s_s} ET(s)p(s)ds \end{aligned} \quad (25)$$

[45] Also, one can estimate the average total depth of runoff caused by rainfall over the growing season through the other terms of the balance equation in the form of  $\bar{V}_Q = \bar{V}_R + \bar{V}_I + \bar{V}_{CF} - \bar{V}_L - \bar{V}_{ET}$ .

#### 2.3.5. Irrigation-Dependent Shallow Groundwater

[46] An average irrigation-dependent water table depth is considered in this study based on which the more the leakage due to irrigation (and or rainfall), the shallower will be the groundwater. Consequently, the average groundwater table depth will not be constant for different (deficit) irrigation policies. Given that crops require soil

aeration for a sufficient root development which improves productivity, subsurface drainage will provide a situation where water table is prevented from entering into the crop-root zone [*Sands*, 2001], except for some short periods during and immediately after heavy rainfall events and intensive irrigation applications. Therefore, the average water table depth is considered to be below the depth of the crop-root zone.

[47] There are two interdependent mechanisms whose balance affects the average water table depth. The first mechanism is related to the effect of the water table depth on soil moisture balance at root zone, and especially the leakage volume, through the upflux influence. In this regard, the e.v. of the total leakage volume (per unit area) from the root zone over a growing season,  $\bar{V}_L(\cdot)$ , is expressed by equation (25) as a function of decision variables,  $\tilde{s}$  and  $\hat{s}$ . Moreover,  $\bar{V}_L(\cdot)$ , through the parameters of capillary flux, that is,  $G$  and  $s_e$ , is also related to the  $Z$ . In contrast, the second mechanism is associated with the effect of the leakage volume on the water table depth due to the features of the shallow groundwater (e.g., aquifer characteristics, drainage system, etc.). Based on conservation of mass and given that lateral water movement occurs mainly horizontally in the saturated region [*Skaggs*, 1978] and in steady-state condition, the flow per unit length of drain at any point on the horizontal axis,  $x$ , will be equal to the total input, that is, leakage rate, in the form of the below equation [*Gini and Bras*, 1991],

$$-K_s h \frac{dh}{dx} = -R(L/2 - x) \quad (26)$$

where  $K_s$  is the saturated hydraulic conductivity,  $h$  is height of water table as a function of  $x$ ,  $R = \bar{V}_L/T_s$  is the average rate of deep percolation, and  $L$  represents the distance between lateral drains. By integrating the above equation, then applying the average operator and knowing that  $\bar{h} = D + d - Z$  ( $\bar{h}$  is the average height of water table above the bottom impermeable boundary,  $d$  is the height of drains above the bottom, and  $D$  is the depth of drains below the soil surface), one can represent the relation between the average depth of water table and deep percolation volume as follows,

$$Z = D + d - \frac{1}{L} \int_0^L \sqrt{d^2 + \frac{\bar{V}_L L}{T_s K_s} x - \frac{\bar{V}_L}{T_s K_s} x^2} dx. \quad (27)$$

[48] Given that  $Z$  is considered not to vary spatially reflecting general state of irrigation management all over the district,  $\bar{V}_L$  in equation (27) represents the average leakage depth over the district. As mentioned before,  $\bar{V}_L$  in equation (27) depends on  $Z$  (equation (25)). Therefore, equation (27) coupled to equation (25) is solved iteratively.

#### 2.4. Root Zone Salt Module

[49] The root zone mass balance equation of salt, which is linked to soil water balance of root zone, can be expressed as follows:

$$\begin{aligned} \frac{dm(t)}{dt} &= C_R R(t) + C_I I(s(t)) + C_{CF} CF(s(t)) \\ &\quad - C(s(t), m(t)) L(s(t)), \end{aligned} \quad (28)$$where  $m$  is the salt mass in the root zone and  $s$  is the relative soil moisture of root zone;  $t$  is the time index;  $C_R$ ,  $C_I$ , and  $C_{CF}$  are the salt concentrations of the input components of soil water corresponding respectively to rainfall, irrigation, and groundwater upflow;  $C = m/(nZ_r s)$  is salinity concentration of soil water in the root zone where  $R$ ,  $I$ ,  $CF$ , and  $L$  are respectively the flow rates of rainfall, infiltrated irrigation, capillary flux, and leakage.

[50] As the salt mass in the root zone does not significantly fluctuate during the short time period of a growing season, one can consider the salt mass dynamics in an average sense by applying time and ensemble integrations to the mass balance equation (equation (28)) resulting in

$$m_e - m_i = C_R \bar{V}_R + C_I \bar{V}_I(\tilde{s}, \hat{s}) + C_{CF} \bar{V}_{CF}(\tilde{s}, \hat{s}) - \frac{\bar{m}}{nZ_r s_1} \bar{V}_L(\tilde{s}, \hat{s}). \quad (29)$$

[51] In equation (29), the l.h.s. represents the salt accumulation in the root zone during a growing season which is the difference between the salt masses at end ( $m_e$ ) and beginning ( $m_i$ ) of a season. The first three terms on the r.h.s. of the equation are the salt mass input components respectively corresponding to the rainfall, irrigation, and groundwater upflow volumes. Note that  $\bar{V}_R$ ,  $\bar{V}_I$ , and  $\bar{V}_{CF}$  are respectively the e.v.s of those water volumes entering into the root zone during a growing season defined in sections 2.3.3 and 2.3.4. The last term on the r.h.s. of the equation is associated with the mass of salt leached from the root zone due to leakage (including effects of both the excess irrigation and rainfall), where  $\bar{m} = (m_e + m_i)/2$  is the time average of the salt mass,  $\bar{V}_L$  is the e.v. of the leakage water volume in the growing season. Also,  $s_1$  is an average value of relative soil moisture during leaching events that can be determined by knowing that  $L(s_1) = \int_{s_e}^{s_s} L(s)p(s)ds$ , where  $L(s)$  and  $p(s)$  are respectively the leakage function and the steady-state pdf of soil moisture (defined in section 2.3.1) as follows:

$$s_1 = s_e + \frac{(\bar{V}_L(\tilde{s}, \hat{s})/T_s)}{K_s} (s_s - s_e). \quad (30)$$

[52] Assuming an equilibrium concentration for salt accumulation in root zone that results in  $m_e = m_i$ , which is usually reached after many successive irrigations [Ayers and Westcot, 1985], one can derive the salt concentration of saturation extract of the root zone. We can estimate the saturation extract concentration of salt, defined by  $C_e = \bar{m}/nZ_r$ , by rewriting equation (29) as follows:

$$C_e(\tilde{s}, \hat{s}) = \frac{C_R \bar{V}_R + C_I \bar{V}_I(\tilde{s}, \hat{s}) + C_{CF} \bar{V}_{CF}(\tilde{s}, \hat{s})}{\bar{V}_L(\tilde{s}, \hat{s})/s_1}. \quad (31)$$

[53] It is worth mentioning that the value of  $C_e$  is used to estimate respectively the salt stress index and the actual crop yield by means of equations (9) and (10).

## 2.5. Solution Approach of the Optimization Model

[54] The issue of which algorithm is better to use for solving a nonlinear optimization model depends on the

model structure, especially whether or not it is convex. An analytical assessment on the convexity of the mathematical program presented in section 2.1 for DI optimization may not be easily done because of the complicated forms of the equations. To have an idea on the shape of the objective function and the feasible space, we have studied numerically the variations of the objective function, the actual crop yield function and the function of total applied water with respect to main decision variables for a SC model. The results have shown that all the mentioned functions are likely to be concave functions. In regard of the feasible space, constraints (2)–(5) form a convex set; while the actual crop yield function is concave that causes inequality (6) to form a convex set. However, given that the total applied water,  $\bar{V}_t$ , varies in a concave form with respect to decision variables, inequality (7) does not form a convex subset, whose intersection with other constraints will form a nonconvex feasible space. Therefore, the mathematical program is nonconvex. Consequently and as the model is highly nonlinear, one should make use of a global optimization algorithm such as PSO to solving the program.

### 2.5.1. Particle Swarm Optimization

[55] The PSO algorithm, combined with the presented agrohydrological simulation model, has been used to solve the nonlinear program presented in section 2.1. The algorithm is a member of evolutionary computation techniques that belongs to the wide category of swarm intelligence methods for solving global optimization problems. Kennedy and Eberhart [1995] originally proposed the PSO as an optimization algorithm. It can be easily implemented and is computationally inexpensive, since its memory and CPU speed requirements are low while using only primitive mathematical operators [Eberhart et al., 1996]. More details on the PSO algorithm and its application in solving a variety of water resources optimization problems may be found elsewhere [e.g., Mousavi and Shourian, 2010a, 2010b].

## 3. Results and Discussion

### 3.1. Case Study

[56] The Karkheh River Basin (KRB) with an area of 43,000 km<sup>2</sup>, located in southwest of Iran, is one of the most important basins of the country in terms of available surface and groundwater resources and its role in hydropower and agricultural developments. At downstream part of the basin, water resources are more limited due to both water quality and quantity issues, as groundwater resources are quality-limited because of the aquifers that are highly saline. Therefore, there is an essential need for applying irrigation water more efficiently. Karkheh Reservoir (KR) with an active capacity of 3904 million cubic meters (mcm) at downstream of KRB is the main source for irrigating 300,000 ha of the cultivation areas of KRB [Mahab Ghodss Consulting Engineers, 2001]. A tunnel, called Dasht-e-Abbas, delivers part of KR's water storage to Dasht-e-Abbas Irrigation District (DAID), with an area of 16,500 ha, as well as Ein-khosh Fakkeh Irrigation District (EFID), with an area of 32,750 ha [Mahab Ghodss Consulting Engineers, 1999]. Among all the irrigation districts, DAID and EFID have rather proper water resources (groundwater with an average TDS of about 3160 mg L<sup>-1</sup>and KR with an average TDS of about  $700 \text{ mg L}^{-1}$ ) and soil conditions (I, II, and III classes of the USBR classification of land suitability for irrigated agriculture) [Mahab Ghodss Consulting Engineers, 2000a]. The climate is semiarid with an average annual rainfall of 280 mm and annual reference ET of 1625 mm. Taking daily rainfall time series at Dasht-e-Abbas climatology station, the reduced rainfall frequency ( $\lambda'$ ) and its depth ( $\alpha$ ) have been estimated as  $0.088 \text{ d}^{-1}$  and 1.12 cm, respectively.

[57] While DAID, which is covered by fine soil texture (largely clay and loam), is irrigated by furrows with a total irrigation efficiency of 45%, EFID has deep coarse soil (mostly sand and sandy loam) and is irrigated partly (about 22% of total area) by microirrigation (drip irrigation tape) and partly by sprinkler (solid-set with movable riser), with respectively total irrigation efficiencies of 74% and 61%. DAID needs both deep and surface drains because of the soil depth and texture, while only surface drains have been designed in EFID to collect extra surface runoff due to rainfall and irrigation; therefore, existence of shallow water table is expected only in DAID [Mahab Ghodss Consulting Engineers, 2000a].

[58] About respectively 75% and 100% of cultivation in DAID and EFID are taken place during winter months. Table 1 presents agronomic and economic properties of the winter crops in DAID and EFID. The crop prices, fixed agricultural-production costs (such as fertilizer, pesticides, labor, machinery, and land leveling) and variable irrigation-related costs (e.g., price paid for water and irrigation-related labor) have been estimated based on the statistics that are published annually [Ministry of Jihad-E-Agriculture, 2007]. The fixed irrigation-related costs have been estimated based on the economic evaluations performed in the project regarding operation and maintenance costs of the main and secondary irrigation and drainage channels, pipes, and also irrigation and drainage systems in the farms [Mahab Ghodss Consulting Engineers, 2000b].

[59] The problem of optimizing short-term irrigation planning in DAID and EFID is dealt with in the following sections.

### 3.2. Single-Crop Case

[60] Before approaching the real MC problem considering DAID and EFID, it is of value to analyze SC problems through which the model's response to different factors such as water requirement, crop yield, and net benefit is more understood. The mathematical program represented

in section 2.1 has been solved for a number of SC problems under different DI regimes.

[61] Figure 2 shows the change of root-zone water balance during the growing season with respect to the applied water for the semiarid climate of DAID; Figures 2a and 2b are respectively related to barley and tomato. An increase in the applied water has led to an increase in irrigation water, evapotranspiration, capillary flux, and leakage volumes. A SA policy for barley in DAID has led to such a water balance scheme in which rainfall, irrigation, and capillary flux volumes constitute respectively 42%, 25%, and 33% of the ET. Also, neglecting leakage due to rainfall, about 30% of infiltrated irrigation is deeply percolated from the root zone. Under the most severe DI regime in which only 10% of the total crop water requirement is applied, the rainfall supplies about 90% of actual ET; although different forms of water balance can be observed for different crops under different soil and climatic conditions.

[62] One of the major problems which this study deals with is about how water should be allocated to different crops in a MC problem, which is controlled by two essential factors, that is, the net benefit function and the amount of water requirement. Figure 3 shows how the net benefit value varies against the change of the applied water for different crops. Figure 3a compares the crops in EFID which are irrigated by the microirrigation technology. The comparisons have been made for cucumber with a medium net benefit and a low water demand, water melon and tomato with relatively low net benefits and high water demands and potato with a high water demand and a high net benefit. Due to the high costs, compared to the net benefit achieved, and also a high ET demand, compared to rainfall, negative net benefits have been resulted for small amounts of applied water. Assuming a situation in which water is to be allocated to multiple crops with the same cultivation areas as those of SC cases, it becomes clear that under a severe water scarcity condition, one can expect that the cucumber's water demand is supplied first due to its low water demand and moderate net benefit. However, under a mild water scarcity condition, the potato's water demand might be supplied first because of its higher net benefit than that of cucumber, in spite of its larger water demand.

[63] Figure 3b compares the results obtained for cucumber, as an example, under different agricultural conditions, that is, microirrigation in EFID and surface irrigation in DAID. Apart from the irrigation technology used, DAID

**Table 1.** Agronomic and Economic Properties of Winter Crops in the Irrigation Districts Located Downstream of Dasht-e-Abbas Tunnel

<table border="1">
<thead>
<tr>
<th rowspan="2">Crop</th>
<th rowspan="2">Type</th>
<th rowspan="2">Plant. Date</th>
<th rowspan="2"><math>T_{seas}</math> (day)</th>
<th rowspan="2"><math>ET_p</math> (<math>\text{cm d}^{-1}</math>)</th>
<th rowspan="2"><math>Z_r</math> (cm)</th>
<th rowspan="2"><math>k_{y,1}</math></th>
<th rowspan="2"><math>k_{y,2}</math> (<math>\text{g}^{-1} \text{L}</math>)</th>
<th rowspan="2"><math>C_{e,T}</math> (<math>\text{g L}^{-1}</math>)</th>
<th rowspan="2">Pot. Yield (kg/ha)</th>
<th rowspan="2">Price ($/kg)</th>
<th rowspan="2">Fixed Agri. Cost ($/ha)</th>
<th rowspan="2">Var. Irrig. Cost ($/mcm)</th>
<th colspan="3">Cultivation Area (ha)</th>
</tr>
<tr>
<th>DAID</th>
<th>EFID (sprinkler)</th>
<th>EFID (micro)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Wheat</td>
<td>Winter</td>
<td>Nov.</td>
<td>200</td>
<td>0.27</td>
<td>100</td>
<td>1</td>
<td>0.072</td>
<td>4.672</td>
<td>5000</td>
<td>0.27</td>
<td>362</td>
<td>1.09</td>
<td>4125</td>
<td>5109</td>
<td>0</td>
</tr>
<tr>
<td>Barley</td>
<td>Winter</td>
<td>Nov.</td>
<td>200</td>
<td>0.24</td>
<td>100</td>
<td>1</td>
<td>0.078</td>
<td>5.120</td>
<td>4500</td>
<td>0.24</td>
<td>214</td>
<td>0.76</td>
<td>2475</td>
<td>2555</td>
<td>0</td>
</tr>
<tr>
<td>Faba bean</td>
<td>Winter</td>
<td>Nov.</td>
<td>175</td>
<td>0.21</td>
<td>100</td>
<td>0.85</td>
<td>0.150</td>
<td>1.024</td>
<td>2500</td>
<td>1.50</td>
<td>222</td>
<td>1.67</td>
<td>1320</td>
<td>3832</td>
<td>0</td>
</tr>
<tr>
<td>Potato</td>
<td>Winter</td>
<td>Jan.</td>
<td>140</td>
<td>0.44</td>
<td>60</td>
<td>1.1</td>
<td>0.188</td>
<td>1.088</td>
<td>30,000</td>
<td>0.33</td>
<td>2701</td>
<td>0.61</td>
<td>0</td>
<td>3832</td>
<td>1801</td>
</tr>
<tr>
<td>Cucumber</td>
<td>Winter</td>
<td>Nov.</td>
<td>130</td>
<td>0.17</td>
<td>60</td>
<td>1.1</td>
<td>0.156</td>
<td>1.152</td>
<td>25,000</td>
<td>0.21</td>
<td>1604</td>
<td>1.37</td>
<td>825</td>
<td>0</td>
<td>1801</td>
</tr>
<tr>
<td>Tomato</td>
<td>Winter</td>
<td>Jan.</td>
<td>155</td>
<td>0.39</td>
<td>80</td>
<td>1.05</td>
<td>0.141</td>
<td>1.088</td>
<td>25,000</td>
<td>0.18</td>
<td>2344</td>
<td>2.35</td>
<td>825</td>
<td>0</td>
<td>1801</td>
</tr>
<tr>
<td>Watermelon</td>
<td>Winter</td>
<td>Mar.</td>
<td>110</td>
<td>0.47</td>
<td>60</td>
<td>1.1</td>
<td>0.191</td>
<td>1.280</td>
<td>40,000</td>
<td>0.08</td>
<td>818</td>
<td>1.37</td>
<td>0</td>
<td>0</td>
<td>1801</td>
</tr>
<tr>
<td>Sugar beet</td>
<td>Winter</td>
<td>Nov.</td>
<td>205</td>
<td>0.28</td>
<td>70</td>
<td>0.8</td>
<td>0.092</td>
<td>4.480</td>
<td>50,000</td>
<td>0.06</td>
<td>2207</td>
<td>1.67</td>
<td>1650</td>
<td>0</td>
<td>0</td>
</tr>
</tbody>
</table>![Figure 2: Variation of the water balance coefficients under different water deficit levels. (a) Barley cultivation in DAID. (b) Tomato cultivation in DAID. Both plots show Water Balance Coefficients (mm) on the y-axis versus Applied Water (mm) on the x-axis. The legend includes Rainfall, Irrigation, Capillary, ET, and Leakage. In (a), the y-axis ranges from 0 to 1200 and the x-axis from 30 to 320. In (b), the y-axis ranges from 0 to 1800 and the x-axis from 130 to 1270. Both plots show a positive correlation between applied water and water balance coefficients, with leakage being the largest component.](59c31bf76866231504ceba82d03de12f_2_img.webp)

**Figure 2.** Variation of the water balance coefficients under different water deficit levels; (a) Barley cultivation in DAID. (b) Tomato cultivation in DAID (see Table 1 for agronomic and economic data of barley and tomato; whereas other parameter values are  $\lambda' = 0.089\text{d}^{-1}$ ,  $\alpha = 1.118\text{cm}$ ,  $C_R = 3\text{mg L}^{-1}$ ,  $C_I = 704\text{mg L}^{-1}$ ,  $C_{CF} = 3160\text{mg L}^{-1}$ , and clay loam soil).

differs from EFID in terms of the presence of shallow water table effects; thus, needing an extra water demand for leaching. Under a SA irrigation scenario, although the maximum net benefits obtained are close, the water requirement in DAID is significantly more than that in EFID, because of their difference in irrigation technology. It is clear that in a MC situation, water will be allocated first to cucumber which is under microirrigation in EFID.

[64] Comparison of the results obtained for potato in EFID under microirrigation and sprinkler-irrigation technologies show that both the net benefit and the water demand in sprinkler irrigation are slightly more than those in microirrigation.

### 3.3. Multicrop Case

[65] One of the properties of the developed model essential to MC problems is related to the use of an

explicit simulation module, which provides a remarkable computational efficiency compared to a model in which the implicit approach of Monte Carlo simulation is used. To show this advantage, the computer run time resulted from the two approaches have been compared when considering only one model simulation (objective function evaluation) in a MC case consisting of 14 irrigation units using a high-speed personal computer (Quad CPU Q8400 at 2.67 GHz speed and 3.5 GB of RAM). The implicit model took 39.2 s while the explicit model consumed only 1.5 s to complete; so the latter was about 26 times faster than the implicit approach. Moreover, the PSO algorithm with a swarm size of 28 and 100 maximum number of iterations, combined with the explicit model, took about 104 min to solve the 14 crop DI optimization problem, whereas the implicit model consumed 2704 min to solve the problem.

![Figure 3: Comparison of the net benefit obtained for different DI technologies and crops. (a) Different crops under sprinkler-irrigation (SPI) technology in EFID. (b) Different irrigation conditions: microirrigation (MI) in EFID, SPI in EFID and surface irrigation (SFI) in DAID. Both plots show Net Benefit ($/ha) on the y-axis versus Total Applied Water (m³/ha) on the x-axis. The legend includes Potato, Cucumber, Tomato, Water melon, Potato-MI, Potato-SPI, Cucumber-MI, and Cucumber-SFI. In (a), the y-axis ranges from -2000 to 8000 and the x-axis from 0 to 8000. In (b), the y-axis ranges from -2000 to 8000 and the x-axis from 0 to 10000. Both plots show a positive correlation between total applied water and net benefit, with Potato and Cucumber showing the highest benefits.](59c31bf76866231504ceba82d03de12f_9_img.webp)

**Figure 3.** Comparison of the net benefit obtained for different DI technologies and crops; (a) Different crops under sprinkler-irrigation (SPI) technology in EFID; (b) Different irrigation conditions: microirrigation (MI) in EFID, SPI in EFID and surface irrigation (SFI) in DAID.[66] Before discussing the results of the MC case with 14 irrigation units (6 IUs in DAID and 8 IUs in EFID), the model results are analyzed for a simpler MC case with four irrigation units located in EFID under sprinkler irrigation including wheat, barley, faba bean, and potato crops. This analysis can help better understand the competition level for water between the crops. Figure 4a shows how the competition looks like at different levels of total water availability or DI characterized by the ratio of total applied water (TW) to its maximum value ( $TW_{max}$ ) associated with the SA strategy. Moreover, Figure 4b represents the net benefit obtained from each irrigation unit for different levels of DI. Comparing Figures 4a and 4b, one can find that the applied water variable has followed the same trend as that of the net benefit variable. While  $TW_{max}$  associated with potato and wheat crops are nearly the same in EFID area, for low values of water availability most of water is allocated to potato due to its higher economic value with more benefit per drop of water allocated. One can clearly see in Figure 4a that the lower the ratio of  $TW/TW_{max}$ , the higher will be the level of competition between the crops.

[67] The total net benefit obtained from agriculture in the region, that is, the MC case with 14 IUs, with respect to  $TW/TW_{max}$  ratio has been illustrated in Figure 4c. A greater total net benefit is expected to gain in the MC situation than that in the SC case. The difference has, however, become larger for a range of  $TW/TW_{max}$  between 0.5 and 0.8. For the MC case, it is worth mentioning that only an 18% decrease in the total net benefit has been resulted due to a 40% reduction in the total applied water.

[68] Water profitability (WP) index defined as the ratio of total net benefit to total applied water has been also analyzed. Figure 4c shows that the maximum value of WP in the SC case is equal to  $0.47 \text{ \$ m}^{-3}$ , which corresponds to a SA policy ( $TW/TW_{max} = 1$ ). However, much larger values of WP have been achieved for the MC case with a maximum WP corresponding to a DI condition with a  $TW/TW_{max} = 0.6$ .

[69] While the cultivated area in DAID is about 33% of the total area of the region, only 10% and 18% of the total net benefit have been obtained from DAID for  $TW/TW_{max}$  values equal to 0.6 and 1, respectively (corre-

sponding to total water applications of 32% and 42%, respectively). This agroeconomic situation in DAID is mainly because of relatively low-valued crops and adverse soil and shallow water conditions resulting in significant leaching water requirement and crops yield reduction. While 56%, 36%, and 8% of the total ET have been respectively supplied by rainfall, irrigation, and upflux components under DI with a  $TW/TW_{max} = 0.6$  in DAID, those percentages are respectively equal to 39%, 36%, and 25% under a SA condition. Also, in EFID and under DI with  $TW/TW_{max} = 0.6$ , 40%, and 60% of the total ET have been supplied by rainfall and irrigation, respectively. The irrigation share has, however, increased to 68% under a SA irrigation condition.

### 3.4. Sensitivity Analysis

[70] The presented model has taken temporal variability of rainfall as the only source of uncertainty. There are, however, other sources of uncertainty affecting irrigation management. To assess how significant rainfall uncertainty is compared to other sources of uncertainty, this section presents a sensitivity analysis with respect to different uncertain factors including rainfall, soil parameters, crop features, and socioeconomic parameters. A Monte Carlo-based simulation model of irrigation management including soil moisture dynamics (equation (11)), crop yield (equation (8)), and net benefit (equation (1)) is used considering a beta-type distribution, suited to double-bounded random variables, for the uncertain parameters.

[71] For each factor, two states of low and high variability, characterized respectively by coefficients of variation equal to 6% and 23%, are considered. Two climate conditions of semiarid and semihumid are also examined for each state resulting in four combinations of uncertainty and climate conditions (Table 2). For each combination, several cases are evaluated considering uncertainty of one parameter along with rainfall uncertainty. For instance, only rainfall uncertainty is evaluated first (forth row of Table 2) after which other uncertainties, one by one, have been added to rainfall uncertainty (fifth to fourteenth rows of Table 2). Finally, all the parameters are considered to vary simultaneously (last row of Table 2).

![Figure 4: Competition among the crops for water; (a and b) Multicrop (MC) case with four irrigation units in EFID under sprinkler irrigation; (c) The results of MC and single-crop (SC) models where total net benefit (TNB) and the water profitability obtained in the MC and SC cases are compared.](eeae2442c81f1e485c9e89ec0b5bf0dd_10_img.webp)

Figure 4 consists of three subplots labeled (a), (b), and (c).  
 Subplot (a) shows 'Applied Water (mcm)' on the y-axis (0 to 35) versus ' $TW/TW_{max}$ ' on the x-axis (0 to 1). It contains four lines representing different crops: Wheat (blue), Barley (red), Faba bean (green), and Potato (purple). Potato shows the highest water application, peaking around 30 mcm at  $TW/TW_{max} = 0.6$ . Wheat and Barley show lower, more fluctuating water application levels.  
 Subplot (b) shows 'Net Benefit (\$)' on the y-axis (0.0E+00 to 6.0E+07) versus ' $TW/TW_{max}$ ' on the x-axis (0 to 1). It contains four lines: Wheat (blue), Barley (red), Faba bean (green), and a 'Sum' line (cyan). The 'Sum' line shows the total net benefit, which increases steadily from approximately 1.5E+07 at  $TW/TW_{max} = 0.1$  to 5.0E+07 at  $TW/TW_{max} = 1.0$ .  
 Subplot (c) compares 'Total Net Benefit (\$)' and 'Net benefit per Unit Water (\$/m³)' on the y-axes (left: 0.0E+00 to 1.0E+08, right: -0.30 to 0.70) versus ' $TW/TW_{max}$ ' on the x-axis (0 to 1). It contains four lines: TNB-SC (blue), TNB-MC (red), WP-SC (green), and WP-MC (purple). TNB-MC is consistently higher than TNB-SC. WP-MC is consistently higher than WP-SC, with a peak around  $TW/TW_{max} = 0.6$ .

**Figure 4.** Competition among the crops for water; (a and b) Multicrop (MC) case with four irrigation units in EFID under sprinkler irrigation; (c) The results of MC and single-crop (SC) models where total net benefit (TNB) and the water profitability obtained in the MC and SC cases are compared.**Table 2.** Assessing Relative Importance of Uncertain Factors Affecting Key Variables in Irrigation Management<sup>a</sup>

<table border="1">
<thead>
<tr>
<th rowspan="3">Uncertainty Climate Parameter</th>
<th colspan="6">Low</th>
<th colspan="6">High</th>
</tr>
<tr>
<th colspan="3">Semiarid</th>
<th colspan="3">Semihumid</th>
<th colspan="3">Semiarid</th>
<th colspan="3">Semihumid</th>
</tr>
<tr>
<th>CV<sub>ID</sub></th>
<th>CV<sub>AY</sub></th>
<th>CV<sub>NB</sub></th>
<th>CV<sub>ID</sub></th>
<th>CV<sub>AY</sub></th>
<th>CV<sub>NB</sub></th>
<th>CV<sub>ID</sub></th>
<th>CV<sub>AY</sub></th>
<th>CV<sub>NB</sub></th>
<th>CV<sub>ID</sub></th>
<th>CV<sub>AY</sub></th>
<th>CV<sub>NB</sub></th>
</tr>
</thead>
<tbody>
<tr>
<td>Rainfall</td>
<td>23.3</td>
<td>1.7</td>
<td>1.9</td>
<td>70.2</td>
<td>1.5</td>
<td>1.6</td>
<td>24.8</td>
<td>1.9</td>
<td>2.0</td>
<td>64.7</td>
<td>1.4</td>
<td>1.5</td>
</tr>
<tr>
<td>Soil</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td><math>s^*</math></td>
<td>22.3</td>
<td>1.7</td>
<td>1.9</td>
<td>67.6</td>
<td>1.9</td>
<td>2.1</td>
<td>27.0</td>
<td>2.2</td>
<td>2.5</td>
<td>83.7</td>
<td>2.0</td>
<td>2.2</td>
</tr>
<tr>
<td><math>n</math></td>
<td>23.0</td>
<td>1.7</td>
<td>1.9</td>
<td>67.8</td>
<td>1.5</td>
<td>1.6</td>
<td>24.8</td>
<td>1.8</td>
<td>1.9</td>
<td>76.9</td>
<td>1.8</td>
<td>2.0</td>
</tr>
<tr>
<td><math>K_s</math></td>
<td>24.0</td>
<td>1.8</td>
<td>1.9</td>
<td>67.3</td>
<td>1.5</td>
<td>1.7</td>
<td>22.6</td>
<td>1.6</td>
<td>1.8</td>
<td>69.6</td>
<td>1.5</td>
<td>1.6</td>
</tr>
<tr>
<td><math>Z</math></td>
<td>21.3</td>
<td>1.6</td>
<td>1.8</td>
<td>63.3</td>
<td>2.0</td>
<td>2.1</td>
<td>26.0</td>
<td>2.0</td>
<td>2.2</td>
<td>75.4</td>
<td>2.0</td>
<td>2.1</td>
</tr>
<tr>
<td>Crop</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td><math>Z_r</math></td>
<td>22.9</td>
<td>1.7</td>
<td>1.9</td>
<td>67.6</td>
<td>1.5</td>
<td>1.6</td>
<td>23.2</td>
<td>1.6</td>
<td>1.8</td>
<td>66.4</td>
<td>1.8</td>
<td>1.9</td>
</tr>
<tr>
<td><math>ET_{max}</math></td>
<td>26.4</td>
<td>1.7</td>
<td>1.9</td>
<td>71.5</td>
<td>1.5</td>
<td>1.7</td>
<td>46.8</td>
<td>2.3</td>
<td>2.5</td>
<td>99.4</td>
<td>2.1</td>
<td>2.2</td>
</tr>
<tr>
<td><math>Y_p</math></td>
<td></td>
<td>6.0</td>
<td>6.5</td>
<td></td>
<td>6.0</td>
<td>6.6</td>
<td></td>
<td>22.6</td>
<td>24.7</td>
<td></td>
<td>22.4</td>
<td>24.3</td>
</tr>
<tr>
<td><math>k_{y,1}</math></td>
<td></td>
<td>1.9</td>
<td>2.1</td>
<td></td>
<td>1.5</td>
<td>1.6</td>
<td></td>
<td>3.5</td>
<td>3.9</td>
<td></td>
<td>1.9</td>
<td>2.0</td>
</tr>
<tr>
<td>Economy</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>Price</td>
<td></td>
<td></td>
<td>6.9</td>
<td></td>
<td></td>
<td>6.8</td>
<td></td>
<td></td>
<td>24.4</td>
<td></td>
<td></td>
<td>24.5</td>
</tr>
<tr>
<td>Cost</td>
<td></td>
<td></td>
<td>2.0</td>
<td></td>
<td></td>
<td>1.7</td>
<td></td>
<td></td>
<td>2.7</td>
<td></td>
<td></td>
<td>2.5</td>
</tr>
<tr>
<td>All parameters</td>
<td>25.9</td>
<td>6.2</td>
<td>9.7</td>
<td>69.4</td>
<td>6.3</td>
<td>9.5</td>
<td>50.9</td>
<td>22.7</td>
<td>35.9</td>
<td>116.7</td>
<td>22.3</td>
<td>33.9</td>
</tr>
</tbody>
</table>

<sup>a</sup>Faba bean under microirrigation cultivation has been assessed; two climate conditions of semiarid ( $\lambda' = 0.1, \alpha = 1$ ) and semihumid ( $\lambda' = 0.25, \alpha = 1.5$ ) are assumed; average values of soil parameters are  $s^* = 0.22, n = 0.35, K_s = 250 \text{ cm d}^{-1}$ , and  $Z = 300 \text{ cm}$ ; average value of crop parameters are  $Z_r = 80 \text{ cm}, ET_{max} = 0.38 \text{ cm d}^{-1}, Y_p = 2500 \text{ kg ha}^{-1}$ , and  $k_1 = 0.85$ ; average values of crop price and total production cost are respectively equal to 1.5 \$ kg<sup>-1</sup> and 280 \$ ha<sup>-1</sup>.

[73] There are three key variables including the required depth of seasonal irrigation application (ID), actual yield per unit area (AY), and net benefit achieved per unit area (NB), which are affected by the uncertain factors. It is worth noting that the e.v.s of ID, AY, and NB variables, respectively equal to 109 mm, 2205 kg ha<sup>-1</sup>, and 3028 \$ ha<sup>-1</sup> for the semiarid climate and also 21 mm, 2382 kg ha<sup>-1</sup>, and 3292 \$ ha<sup>-1</sup> for the semihumid climate, do not vary in different cases.

[74] Table 2 presents the effects of six uncertain factors including temporal variability of rainfall, stomatal closure threshold,  $s^*$ , soil porosity,  $n$ , saturated hydraulic conductivity,  $K_s$ , water table depth,  $Z$ , root depth,  $Z_r$ , and maximum evapotranspiration,  $ET_{max}$ , on coefficient of variation of ID,  $CV_{ID}$ . For the state of low variability and for both semiarid and semihumid climate conditions,  $CV_{ID}$  is relatively high (about 23% for semiarid and 68% for semihumid conditions) due to temporal variability of rainfall, while it is not affected that much by other sources of uncertainty. Nevertheless, variation of  $ET_{max}$  significantly affects the uncertainty of ID for the state of high variability. For instance,  $CV_{ID}$ , for semiarid climate, has increased from 24.8% to 46.8% due to the added effect of uncertainty of  $ET_{max}$  compared to the situation in which only temporal variability of rainfall has been considered. Observing the columns related to  $CV_{AY}$ , one can realize that the uncertainty of potential crop yield ( $Y_p$ ) affects significantly  $CV_{AY}$  and other sources of uncertainty, including temporal variability of rainfall, have minimal effects on the AY uncertainty. Moreover,  $Y_p$  and the crop price are the most influential parameters whose uncertainty affects the variations of the key variable of net benefit,  $CV_{NB}$ . Nevertheless, in a normal socioeconomic condition, the economic factors such as crop price and crop production are not highly uncertain in a short-term horizon of a growing season.

### 3.5. Specific Practical Considerations

[75] The following three steps may need to be taken to have such a modeling framework applied in a real irrigation practice.

[76] (1) Preprocessing which includes calibration and validation of the component modules of soil moisture, crop yield, and salt balance for the study region. This step should be used based on a suitable database including hydroclimatic observations, soil moisture measurements, actual crop yield observation, soil salt measurements, etc.

[77] (2) Processing which deals with the use of the developed stochastic optimization model to solve some specific problems related to irrigation management. The problems addressed in this study are (a) determining optimal policies associated with water allocation between different irrigation units, (b) determining optimal DI policies, (c) evaluating different crop pattern scenarios and selecting the best scenario, and (d) assessing the effects of different hydroclimate scenarios on the optimal irrigation policies including optimal water allocation between irrigation units and optimal DI level of each irrigation unit.

[78] (3) Postprocessing. Like any other optimization scheme, making some approximations and simplifications has been unavoidable in the presented modeling framework. A useful approach used to deal with these simplifications is the assessment of the results of the stochastic optimization model by means of more detailed simulation models with less approximation.

[79] The effort made in this study focuses on the second step and the scope of the work has been more related to build a new modeling framework and derive analytical expressions for statistics of stochastic soil moisture process to be used in stochastic optimization of DI, rather than explicitly taking the first and the third steps into full consideration. Therefore, we need to integrate the second step taken with two other steps considering more details of institutional and socioeconomic subsystems to put the results of such a modeling framework into a real practice. Moreover, while we have tried to assess how valid the simplifications and approximations made are, there is still a large room left to be done in future contributions regarding the third step.[80] Referring to the first step, because there were not enough data available in the region, that is, DAID and EFID, the parameters of the soil water, root-zone, salt, and crop yield modules of the model have been estimated using the available information and engineering judgment in a data-limited situation. While the problem of precisely calibrating and validating of those modules, although very important, has not been the main subject of this study; it, however, implies that the results presented are limited from an application point of view. Moreover, given that the presented optimization model includes an objective function of net benefit obtained from irrigation in several irrigation districts, it can be used for irrigation planning at the scale of a whole district as an integrated unit. Consequently, a proper institutional framework is needed to be established through which farmers can gather and cooperate.

#### 4. Conclusions

[81] In this study, rainfall uncertainty, as an integral part of deficit irrigation (DI) management, has been taken into account using an agrohydrological integrated simulation model coupled with the PSO meta-heuristic optimization algorithm for both single-crop (SC) and multi-crop (MC) problems. The simulation model consists of an explicit stochastic model of soil moisture dynamics in crop-root zone considering the shallow water table effects, a conceptual root-zone salt balance model, and finally the FAO crop yield model. The model can determine both the optimum water allocation scheme in an agricultural region between different irrigation units, with different features of crop, soil, economic factors and irrigation-drainage technology, and the optimum DI strategy under water scarcity conditions.

[82] The solution methodology was verified to be about 26 times faster than an alternative optimization approach employing Monte Carlo simulation technique; thus, suitable for solving MC stochastic optimization problems of irrigation management. Then, the model was applied in Dasht-e-Abbas Irrigation District (DAID) and Ein-khosh Fakkeh Irrigation District (EFID) of the Karkheh Basin in southwest of Iran, a MC case. It was found under DI strategy that a 40% decrease in the applied water resulted in only an 18% reduction in total net benefit. The maximum water profitability (WP) index achieved for the MC case was significantly greater than that for the SC case. Moreover, while the maximum WP of the SC case was for a stress avoidance (SA) policy, for the MC case it was associated with a DI strategy in which only 60% of total available water was applied.

[83] The results of a sensitivity analysis showed that the most influential uncertain parameters on the variable of seasonal irrigation requirement were respectively temporal variability of rainfall and evapotranspiration. For the variable of actual crop yield, the potential crop yield was the most influential parameter. Finally, net benefit was more affected by uncertainty in crop price and potential crop yield.

[84] Recognizing the limitations of the present study in explicitly modeling all the influential sources of uncertainty and the simplifying assumptions made, the presented model is a small step ahead in terms of using a state-of-the-art explicit stochastic simulation model of soil moisture dynamics within an irrigation management optimization framework.

[85] **Acknowledgments.** The help provided by Naser Hashemi of Department of Mathematics at Amirkabir University of Technology is greatly acknowledged. The authors have benefited a lot from ideas of Amilcare Porporato and Giulia Vico of Department of Civil and Environmental Engineering at Duke University. Their kind help is highly appreciated. We are grateful to P. Mujumdar and anonymous reviewers whose comments helped us considerably improve the quality of final work.

#### References

Ahmed, J., C. H. M. VanBavel, and E. A. Hiler (1976), Optimization of crop irrigation strategy under a stochastic weather regime a simulation study, *Water Resour. Res.*, 12(6), 1241–1247.

Alizadeh H., and S. J. Mousavi (2013a), Stochastic order-based optimal design of a surface reservoir–irrigation district system, *J. Hydroinform.*, 15(2), 591–606, doi:10.2166/hydro.2012.223.

Alizadeh, H., and S. J. Mousavi (2013b), Probabilistic estimation of irrigation requirement under climate uncertainty using dichotomous and renewal processes, *Adv. Water Resour.*, 53, 263–272, doi:10.1016/j.advwatres.2012.12.006.

Ayers, R. S., and D. W. Westcot (1985), Water quality for agriculture, FAO Irrigation and Drainage Papers 29.

Bras, R. L., and J. R. Cordova (1981), Intra-seasonal water allocation in deficit irrigation, *Water Resour. Res.*, 17, 866–874, doi:10.1029/WR017i004p00866.

Daly, E., and A. Porporato (2006), Impact of hydroclimatic fluctuations on the soil water balance, *Water Resour. Res.*, 42, W06401, doi:10.1029/2005WR00460.

Dudley, N. J., and O. R. Burt (1973), Stochastic reservoir management and system design for irrigation, *Water Resour. Res.*, 9(3), 507–522.

Dudley, N. J., O. R. Brut, and D. M. Reklis (1976), Reliability, trade-offs, and water resources development modeling with multiple crops, *Water Resour. Res.*, 12(6), 1101–1108.

Eagleson, P. S. (1978), Climate, soil and vegetation: 3. A simplified model of soil moisture movement in liquid phase, *Water Resour. Res.*, 14(5), 722–730.

Eberhart, R. C., P. Simpson, and R. Dobbins (1996), *Computational Intelligence PC Tools*, Academic Press, Boston, Mass.

English, M., K. Solomon, and G. Hoffman (2002), A paradigm shift in irrigation management, *J. Irrig. Drain. Eng.*, 128, 267–277, doi:10.1061/(ASCE)0733–9437(2002)128:5(267).

FAO (1998), Crop evapotranspiration—Guidelines for computing crop water requirements, FAO Irrigation and Drainage Paper 56, Rome, Italy.

Ganji, A., K. Ponnambalam, E. D. Khalili, and M. Karamouz (2006), A new stochastic optimization model for deficit irrigation, *Irrig. Sci.*, 25(1), 63–73.

Gates, T. K., and M. E. Grismer (1989), Irrigation and drainage strategies in salinity-affected regions, *J. Irrig. Drain. Eng.*, 115(2), 255–284.

Ghahraman, B. and A. R. Sepaskhah (2002), Optimal allocation of water from a single purpose reservoir to an irrigation project with pre-determined multiple cropping patterns, *Irrig. Sci.*, 21, 127–137.

Gini, M., and R. L. Bras (1991), Simulation of water allocation and salt movement in the root zone, *Water Resour. Manage.*, 5, 121–147.

Hale, M. G., and D. M. Orcutt (1987), *The Physiology of Plants Under Stress*, Wiley, New York.

Hexem, R. W., and E. O. Heady (1978), *Water Production Functions for Irrigated Agriculture*, Iowa State Univ. Press, Ames, Iowa.

Howitt, R. E. (1995), Positive mathematical programming, *Am. J. Agric. Econ.*, 77, 329–342.

Ines, A. V. M., K. Honda, A. D. Gupta, P. Droogers, and R. S. Clemente (2006), Combining remote sensing-simulation modeling and genetic algorithm optimization to explore water management options in irrigated agriculture, *Agric. Water Manage.*, 83, 221–232.

Kandil, H. M., and L. S. Willardson (1992), Relating crop-yield response to water-table fluctuations, *J. Irrig. Drain. Eng.*, 118(1), 113–121.

Kennedy, J., and R. C. Eberhart (1995), *Particle Swarm Optimization*, Proc. IEEE Int. Conf. Neural Networks, IV, 1942–1948, IEEE Serv. Cent.

Kirda, C. (2002), Deficit irrigation scheduling based on plant growth stages showing tolerance of water stress, in *Deficit Irrigation Practices*, pp. 3–10, FAO.

Laio, F., A. Porporato, L. Ridolfi, and I. Rodriguez-Iturbe (2001), Plants in water-controlled ecosystems: Active role in hydrologic processes and response to water stress: II. Probabilistic soil moisture dynamics, *Adv. Water Resour.*, 24, 707–723.

Mahab Ghodss Consulting Engineers (1999), Final Rep. on Dasht-e-Abbas Irrigation and Drainage System Phase 2 studies (in Persian).Mahab Ghodss Consulting Engineers (2000a), Irrigation and drainage project of Ein-khosh and Fakkeh district (in Persian), *Technical Rep. of Irrigation and Drainage District*.

Mahab Ghodss Consulting Engineers (2000b), Irrigation and drainage project of Ein-khosh and Fakkeh district (in Persian), *Economic Evaluation Rep.*

Mahab Ghodss Consulting Engineers (2001), Irrigation and drainage and agricultural studies of water resources allocation optimization in Kar-kheh River Basin (in Persian), *Final Rep.*

Ministry of Jihad-E-Agriculture (2007), Provincial Results on Production Cost of Agricultural Crops, vol. 2.

Mousavi, S. J., and Shourian, M. (2010a), Capacity optimization of hydro-power storage projects using particle swarm optimization algorithm, *J. Hydroinform.*, 12, 275–291, doi:10.2166/hydro.2009.039.

Mousavi, S. J., and Shourian, M. (2010b), Adaptive sequentially space filling meta-modeling for optimal water-quantity allocation at basin scale, *Water Resour. Res.*, 46, W03520, doi:10.1029/2008WR007076.

Paris Q., and R. E. Howitt (1998), An analysis of ill-posed production problems using maximum entropy, *Am. J. Agric. Econ.*, 80-1, 124–138.

Porporato, A., F. Laio, L. Ridolfi, and I. Rodriguez-Iturbe (2001), Plants in water-controlled ecosystems: Active role in hydrologic processes and response to water stress. III: Vegetation water stress, *Adv. Water Resour.*, 24(7), 725–744.

Rhenals, A. E., and R. L. Bras (1981), The irrigation scheduling problem and evapotranspiration uncertainty, *Water Resour. Res.*, 17(5), 1328–1338.

Rodriguez-Iturbe, I., and A. Porporato (2004), *Ecohydrology of Water Controlled Ecosystems: Soil Moisture and Plant Dynamics*, Cambridge Univ. Press, Cambridge, U. K.

Rodriguez-Iturbe, I., A. Porporato, L. Ridolfi, V. Isham, and D. R. Cox (1999), Probabilistic modelling of water balance at a point: The role of climate, soil and vegetation, *Proc. R. Soc. London, Ser. A: Math. Phys. Eng. Sci.*, 455, 3789–3805.

Rodriguez-Iturbe, I., V. Isham, D. R. Cox, S. Manfreda, and A. Porporato (2006), Space-time modeling of soil moisture: Stochastic rainfall forcing with heterogeneous vegetation, *Water Resour. Res.*, 42, W06D05, doi:10.1029/2005WR004497.

Russo, D. (1986), A stochastic approach to the crop yield-irrigation relationships in heterogeneous soils: I. Analysis of the field spatial variability, *Soil Sci. Soc. Am. J.*, 50, 736–745.

Sands, G. (2001), *Soil water concepts*, Agricultural Drainage Publication Series, Univ. of Minn.

Skaggs, R. W. (1978), A water management model for shallow water table soils, Rep. No. 134, Water Resour. Res. Inst. Univ. of N. C.

Teixeira, A. S., and M. A. Mariño (2002), Coupled reservoir operation-irrigation scheduling by dynamic programming, *J. Irrig. Drain. Eng.*, 128(2), 63–73.

Tsakiris, G., and M. Spiliotis (2006), Cropping pattern planning under water supply from multiple sources, *Irrig. Drain. Syst.*, 20, 57–68.

Vedula, S., and D. N. Kumar (1996), An integrated model for optimal reservoir operation for irrigation of multiple crops, *Water Resour. Res.*, 32(4), 1101–1108.

Vedula, S., P. P. Mujumdar, and G. C. Sekhar (2005), Conjunctive use modeling for multicrop irrigation, *Agric. Water Manage.*, 73, 193–221.

Vervoort, R. W., and S. E. A. T. M. van der Zee (2008), Simulating the effect of capillary flux on the soil water balance in a stochastic ecohydrological framework, *Water Resour. Res.*, 44, W08425, doi:10.1029/2008WR006889.

Vico, G., and A. Porporato (2010), Traditional and microirrigation with stochastic soil moisture, *Water Resour. Res.*, 46, W03509, doi:10.1029/2009WR008130.

Vico, G., and A. Porporato (2011), From rainfed agriculture to stress-avoidance irrigation: I. A generalized irrigation scheme with stochastic soil moisture, *Adv. Water Res.*, 34, 263–271.

Wright, J., and G. Sands (2001), Planning an agricultural subsurface drainage system, *Agric. Drain. Publ. Ser.*, Univ. of Minn.