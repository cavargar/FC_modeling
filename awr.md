![Elsevier logo featuring a tree and the word ELSEVIER](c808befabf3ca3e9d15a49460426a687_2_img.webp)
![Journal cover image for Advances in Water Resources](c808befabf3ca3e9d15a49460426a687_6_img.webp)

# Space-dependent continuous time random walk for soil moisture modeling

M.C. Bovier <sup>a,c</sup> , <sup>\*</sup>, S. Fedotov <sup>b</sup> , S. Ferraris <sup>c</sup> , A. Gentile <sup>c</sup> , B. Toaldo <sup>a</sup>

<sup>a</sup> Department of Mathematics “Giuseppe Peano” - Università degli Studi di Torino, Via Carlo Alberto 10, Torino, 10124, Italy

<sup>b</sup> Department of Mathematics, The University of Manchester, Oxford Road, Manchester, M13 9PL, UK

<sup>c</sup> Interuniversity, Department of Regional and Urban Studies and Planning (DIST), Politecnico e Università degli Studi di Torino, Viale Mattioli 39, Torino, 10125, Italy

## ARTICLE INFO

### Keywords:

Continuous time random walk

Soil moisture

Field soils

Evapotranspiration

Drought

Dry spells

Anomalous diffusion

## ABSTRACT

A space-dependent continuous time random walk, with waiting times between jumps following a Mittag-Leffler distribution, is considered to model soil moisture. The model is applied to daily soil moisture measurements taken as vertical average between the surface and the depths of 30, 60, and 100 cm, from an experimental site in Grugliasco (Turin, Italy), focusing on dry periods between rainfall events from 2006 to 2008. Our approach assumes that water particles in the soil start with an initial vertical distribution estimated from data after a rainfall. The waiting times between jumps are Mittag-Leffler distributed with a position-dependent parameter  $\alpha_k$  ( $k = 1, 2, 3$ ), that varies according to the layers (0–30 cm, 30–60 cm, 60–100 cm). The effect of evapotranspiration is taken into account in the first layer because the soil is covered by grass.

We simulate the movement of water particles, compute the daily proportion of water in each layer, and compare the results with measured data to estimate the parameters of the Mittag-Leffler distributions. The relationship between the estimated parameters and initial soil moisture and potential evapotranspiration is then investigated. These relationships make it possible to predict the  $\alpha_1$ ,  $\alpha_2$ ,  $\alpha_3$  values for each dry period and to validate the model through comparison between estimated and observed soil moisture. In conclusion, space-dependent continuous time random walks are useful for modeling soil moisture in field soils between rainfall events, requiring only a limited number of parameters and simple assumptions.

## 1. Introduction

Drought related to persistent lack of precipitation is emerging as one of the most pressing environmental challenges in Europe, because of consequences on drinking water, agriculture, fires among the others. The recent year 2022 stands as a reference point, marking one of the most severe and spatially extensive droughts in recent European history (Toreti et al., 2022). By combining observational data with model outputs, Bevacqua et al. (2024) showed that, in 2022, Central and Southern Europe experienced the highest observed total water storage deficit since the beginning of satellite observations, likely representing the most extensive and severe soil moisture deficit in the past 60 years. Accordingly, Zapata-Sierra et al. (2022), analyzing projected scenarios for 2020, 2030 and 2040 following a modeling approach based on the HEC-HMS model, found that the available water resources are expected to decrease for the Almería River catchment located in southern Europe (Spain). In addition, Dukat et al. (2022) investigated long-term trends in drought severity and frequency in six mid-latitude European sites from 1951 to 2015 using an approach based on the standardized precipitation index (SPI) and the Standardized

Precipitation Evapotranspiration Index (SPEI). Although no statistically significant trend was found in the overall frequency of dry months, the results of Dukat et al. (2022) revealed a clear intensification of the severity of summer drought over time. The issue of drought is not limited to Central and Southern Europe; Northern regions have also had to face this challenge throughout history. In this regard, the United Kingdom, and particularly southern England, experienced one such episode during the prolonged 2004–2006 drought. This event was marked by above-average temperatures, aligning with the broader trend of ongoing climate warming. However, what made this event rare was also the occurrence of dry winters (Marsh et al., 2009).

Italy, and particularly the Po River Basin, faced an unprecedented drought in 2022. Montanari et al. (2023) observed a decrease in the Po summer river flows, which was more pronounced than the reduction in precipitation. This was attributed to a combination of changes in the precipitation regime – leading to a reduced snow fraction and snowmelt – as well as to increased evaporation rates and the expansion of irrigated fields. Upon reaching northwestern Italy, the Piedmont region faced an acute hydrological crisis, documented by regional

\* Corresponding author.

E-mail address: [mariachiara.bovier@unito.it](mailto:mariachiara.bovier@unito.it) (M.C. Bovier).reports (Piemonte, 2022), which has presented significant challenges in understanding the proper allocation of water resources, especially for irrigation practices. However, the issue of water resource management in the Piedmont region has already emerged in the past. Brussolo et al. (2022) found that, over the 1959–2017 period, the westernmost catchments of the Piedmont region experienced significant declines in precipitation and drainage, while actual evapotranspiration increased across all catchments due to rising temperatures and irrigation. Climate projections to 2050 under RCP4.5 and RCP8.5 scenarios showed no significant annual trends in drainage but revealed substantial interannual variability and a consistent decrease in summer recharge across most models. These results point to a seasonal shift in recharge patterns and underscore the sensitivity of groundwater resources to both climatic drivers and land use.

Thus, the increasing recurrence of such dry spells needs greater investigation of precipitation data. In this regard, Baiamonte et al. (2024) improved the modeling of statistical distribution of wet and dry spells lengths (i.e., their duration) across some very different European climates. The authors proposed two methodologies: the first one adapts the discrete Lerch distribution to precipitation inter-arrival times, from which wet spells and dry spells lengths are derived; the second one adapts the Lerch distribution to wet and dry spells data separately. While understanding the statistical distribution of dry spells lengths is crucial, it is equally crucial to investigate the soil behavior during such periods. Soil moisture represents a key state variable for understanding hydrological processes (such as drainage, evaporation and plant uptake), and there are various approaches and techniques for monitoring and estimating soil moisture at local and plot scale in different field conditions (Raffelli et al., 2017). Different types of models have been proposed for soil moisture dynamics. Laio et al. (2001) proposed a stochastic model and investigated the analytical solution of the steady-state probability distributions to assess the role of the various components of the climate-soil-vegetation system in the temporal dynamics of soil moisture and water balance (see also Ridolfi et al., 2011). Furthermore, understanding groundwater flow and solute transport is also essential and represents a challenge, especially in field soils. In this context, it has been shown that, when high-resolution hydraulic conductivity data are used with a fractal stochastic method that produces fields with adequate connectivity, the classical advective-dispersive equation can successfully predict solute transport in highly heterogeneous alluvial aquifers (Dogan et al., 2014). For subsurface water flow in heterogeneous catchments, Bovier et al. (2025) proposed a stochastic model based on a random velocity process with rests, to estimate the empirical transit time distribution and the threshold age for the young water fraction, which was applied to 22 catchments in Switzerland.

Both bucket and physically based models, such as those governed by Richards' equation, are commonly used to simulate soil moisture dynamics (Porporato and Yin, 2022). Many of these models rely on the numerical solution of Richards' equation through different techniques (see, for example, Manzini and Ferraris (2004)). However, these models often require detailed parameterization and a large number of exogenous inputs.

Instead of relying on traditional formulations (based on Richards' equation or bucket models), we propose a stochastic model, specifically, a space-dependent continuous time random walk with heavy tailed waiting times between jumps, capable of accurately simulating the temporal evolution of average field scale soil moisture during dry spells. This model requires a minimal parameterization and limited exogenous input variables. In this regard, the model uses only the initial soil moisture content of various soil layers (at different depths) as input, and the potential evapotranspiration as boundary condition. A key novelty of our approach lies in the adoption of a Lagrangian perspective, i.e., the motion of individual water particles is explicitly tracked through time and space, that is new (to the best of our knowledge) in

soil moisture modeling during dry spells. To calibrate the model parameters and evaluate its performance, we use soil moisture data collected at the experimental site in Grugliasco (Turin, Italy) during dry spells that occurred between 2006 and 2008. A Lagrangian approach was also previously considered by Zehe and Jackisch (2016) for modeling water motion during rainfall-drive conditions. It is noteworthy that the process adopted in that study is a diffusion, whereas our approach is based on fractional dynamics, related to anomalous (slower) diffusion.

## 2. Materials and methods

### 2.1. Soil moisture data

The experimental site, previously investigated in past studies (Canone et al., 2008; Baudena et al., 2012; Raffelli et al., 2017), is located at the University of Turin in Grugliasco, in the western part of the Po plain. The area is approximately 1500 m<sup>2</sup>, covered with a permanent grass, and is monitored by an automatic Tektronix based Time Domain Reflectometry (TDR) station. The soil is loamy-sand to sandy, without any gravel, and with a slope of about 1%. In this monitored area, soil moisture is measured by 160 vertical TDR probes placed vertically from the surface to different depths (see Baudena et al., 2012). In particular there are 96 probes, clustered at different places of the site, measuring soil moisture at the depths 30, 60 and 100 cm. In this study we consider data from those probes. The TDR measurement is obtained as the arithmetic average of the volumetric soil water content  $\theta$  (m<sup>3</sup>/m<sup>3</sup>) along the length of the rod. The probes are vertical in order to measure the whole stock of water along the soil profile. The sampling time interval between TDR measurements can vary from one hour (during and after rainfall events) to one day. We remark that the experimental site is flat and spatially homogeneous and thus there is no horizontal gradient in the soil moisture measurements. It is also relevant that the water table in this experimental site is located at a depth of about 40 m, therefore there is no capillary rise at the considered depths (above 100 cm).

Data were collected between 2006 and 2008, and in this study we consider dry spells of approximately 10 days (in different seasons). A dry spell is a period of time during which no atmospheric precipitation (or irrigation) occurs. The dry spells considered here always start 24 h after the last rainfall because of the coarseness of the soil. Therefore, we use daily resolution measurements up to a depth of 1 m and the spatial average of the measurements on all the sensors in the monitored area. The soil moisture data used, from the surface to 30, 60 and 100 cm, are daily and start approximately 24 h after the end of a rainfall event, so that the rainwater has already been infiltrated into the soil. These measurements, denoted as  $\theta^{30}(s)$ ,  $\theta^{60}(s)$  and  $\theta^{100}(s)$ , are the measures of the soil moisture, i.e., the ratio of water volume to soil volume, at different time  $s$  (in days). In the same field, a meteorological station collects standard data at hourly intervals. The station is connected to the Regional Agro-Meteorological service of Piedmont region, Italy. The rainfall climatology in this area is characterized by two maxima, respectively, in spring (April–May) and fall (October–November), with relatively dry winter and summer (Baiamonte et al., 2018). In this area, the vegetation growing season lasts, on average, from late March to mid-October.

In the model proposed here, we consider three soil layers: the first from the surface to 30 cm depth, the second between 30 and 60 cm, and the third between 60 and 100 cm. For each layer, we compute the proportion of water, relative to the total across the three layers, using soil moisture measurements. This is done to compare the field data with the simulated layer-by-layer water proportions obtained from the model. Additionally, the initial vertical water distribution is computed from the data considering the proportion of water in the three layers after the rainfall. The evapotranspiration process is also taken into account, only in the first layer, due to evaporation and root uptake of water from grass. In fact, tensiometers, that measure the gradientof energy, have provided experimental evidence that upward fluxes, from approximately 24 h after rain onward, are confined to the layer from 0 to 30 cm depth. This is the so-called Zero Flux Plane, i.e., the depth above which the water movement will be upward and below will be downward, see Anderson and McDonnell (2005, page 591). In our case this level is about 30 cm because of the shallow roots of grass (this is confirmed by tensiometers data as shown in the Supplementary Materials section).

2.2. Mathematical model

A Continuous time random walk (CTRW) is a jumping processes (Metzler and Klafter, 2000), where a particle performs instantaneous jumps alternated with waiting pauses. The length of jumps and the waiting times are independent random variables. Continuous time random walks are very useful to describe a wide range of physical and biological phenomena involving stochastic transport phenomena, both Markovian and non-Markovian. Furthermore, they can represent different (anomalous) diffusive behaviors depending on the tail of the distribution of jump lengths and waiting times. In particular, when the distributions of jump lengths and waiting times are heavy-tailed, the motion deviates from classical diffusion and anomalous diffusion occurs (Méndez et al., 2010). They have been already used to describe anomalous behavior of water in several other articles (e.g., Elhanati et al. (2025) and Li and Berkowitz (2018)).

We consider here a continuous time random walk with space-dependent waiting times between jumps following Mittag-Leffler distributions to describe the movement of water particles in the soil. The waiting times represent the trapping effect acting on the particles during their movement, and due to the heterogeneity of the soil, the strength of this effect may differ depending on the depth. The trapping effect corresponds to the probability that, at random times and random depths, a water particle is slowed down near a certain position. This description is, of course, a discrete approximation of water motion that must be understood at a suitable scale. When the water particle is slowed down, this behavior is represented in the CTRW as a waiting pause. Jumps represent a rapid water transition occurring over a relatively short distance. In reality, water motion follows continuous trajectories, so describing such transitions as discrete represents a “conceptual discretization” (see Levy and Berkowitz (2003)) of an inherently continuous process. The level of discretization can be made at any chosen spatial resolution depending on the modeling framework.

The assumption underlying our model is that the motion of water particles can be approximated by a jump process performing 1-cm jumps paced by conditionally independent waiting times, and we assume that this model applies only far enough from rainfall events (1 day after) so that the perturbation of soil moisture induced by rainwater is ruled out. The waiting times follow a Mittag-Leffler distribution with position-dependent parameters  $\alpha_k$ ,  $k = 1, 2, 3$ , where  $k$  is the layer where the particle rests (Fig. 1). These parameters are the ones to be estimated from the experimental data.

We assume that the jumps have length 1 cm but run in opposite directions: in the first layer they are upward jumps, due to the evapotranspiration effect, and below they are downward jumps, because of pressure and gravity. The choice of jumps with length 1 cm is clearly an approximation of water motion, which is justified by the expected velocity of water in the soil. Indeed, the Darcy velocity obtained from Richards’ equation (e.g., via the software Hydrus) subject to the same initial conditions agrees with that of our process. It is possible to see that for our process the velocity is of the order  $10^0$  cm/day. This velocity approximation can be considered sufficiently far from the rainfall event, when water begins to move more slowly through the soil after an initial phase immediately following the rain, during which it infiltrates more rapidly. We therefore consider approximately 24 h after a rainfall, since tensiometer measurements, for a sandy soil like the one considered here, show that after this time water begins to move

upward in the top layer, while it moves slowly downward in the rest of the soil. Therefore, if the water particle starts from a depth less than 30 cm, it moves upward toward the surface, because evapotranspiration is predominant in the first layer. Conversely, if the particle starts from a depth greater than 30 cm, it moves downward up to 100 cm depth, since evapotranspiration is negligible in the second and third layers. The initial vertical water distribution is estimated using data one day after a rainfall event. We remark that the order of the velocity of the CTRW can be easily modified by choosing a different jump length, thus making our model suitable for further applications and generalizations to different soil types.

This space-dependent continuous time random walk, say  $X(t)$ ,  $t \geq 0$ , where  $t$  is measured in hours, can be viewed as a semi-Markov process in one dimension, in the sense of (Ricciuti and Toaldo, 2017):

$$X(t) = X_n, \quad T_n \leq t < T_{n+1}, \quad T_n = \sum_{k=0}^{n-1} \tau_k \tag{1}$$

where  $X_n$  is a discrete time Markov chain on the discrete state space  $S = \{0, 1, 2, \dots\}$ ,  $\tau_n$  are the waiting times, and  $T_n$  is the time of the  $n$ th jump with  $T_0 = 0$ . The transition probabilities from state  $i$  (depth in cm) to state  $j$  (depth in cm) are, for  $1 \leq i < 30$

$$h_{ij} = \begin{cases} 1, & j = i - 1 \\ 0, & \text{otherwise,} \end{cases} \tag{2}$$

for  $i \geq 30$

$$h_{ij} = \begin{cases} 1, & j = i + 1 \\ 0, & \text{otherwise,} \end{cases} \tag{3}$$

and finally, we assume that when the particles reach the surface (because of evapotranspiration) they cannot move further, i.e., we introduce the state zero, which is absorbing, and thus we set

$$h_{0j} = \begin{cases} 1, & j = 0, \\ 0, & \text{otherwise.} \end{cases} \tag{4}$$

We observe that the absorbing state zero represents water gone in the atmosphere or in plants. Furthermore, for the sake of simplicity, the definition of the theoretical process is given even below state 100; however the behavior of the process below 100 cm is never compared with data. The assumptions on the waiting times between jumps means that these are random variables  $\tau_n, n \in \mathbb{N}$ , conditionally independent with Mittag-Leffler distribution with a position-dependent parameter  $\alpha_k$ , for  $k = 1, 2, 3$ , which varies according to the soil layer:

$$P(\tau_n > t | X_n \in I_k) = E_{\alpha_k} \left( - \left( \frac{t}{\mathcal{T}_0} \right)^{\alpha_k} \right) \quad \alpha_k \in (0, 1), \text{ for } k = 1, 2, 3, \tag{5}$$

where  $I_k$  indicates the  $k$ th layer,  $\mathcal{T}_0$  is a constant scaling that is 1 h in our model, and  $E_\alpha(\cdot)$  denotes the Mittag-Leffler function of one parameter. The three soil layers, where the particles move, are defined as

$$\begin{aligned} I_1 &= \{i \in \mathbb{N} | 1 \leq i < 30\}, \\ I_2 &= \{i \in \mathbb{N} | 30 \leq i < 60\}, \\ I_3 &= \{i \in \mathbb{N} | 60 \leq i \leq 100\}, \end{aligned} \tag{6}$$

and the Mittag-Leffler function with one parameter  $\alpha$  is defined as

$$E_\alpha(x) = \sum_{k=0}^{\infty} \frac{x^k}{\Gamma(1 + \alpha k)}. \tag{7}$$

The one-parameter Mittag-Leffler function is a generalization of the exponential function which is very popular in the mathematical community working on fractional equations (see, e.g., Mainardi (2010) and Scalas (2006)). This is because, in particular, the survival function  $E_\alpha(-t^\alpha)$  is the eigenfunction of the (Caputo) fractional derivative of order  $\alpha$  and it reduces to the exponential in the case  $\alpha = 1$ . For  $\alpha \in (0, 1]$  the function  $E_\alpha(-t^\alpha)$  is completely monotone and is 1 for  $t = 0$ , this means that it is a legitimate survival function. For  $\alpha \in (0, 1)$ ,The diagram illustrates a soil profile with a vertical axis labeled  $i$  representing depth in centimeters. The soil surface is at the top. A vertical scale on the left shows depth markers at  $i = 30$  cm,  $i = 60$  cm, and  $i = 100$  cm. The soil is divided into three horizontal layers: layer  $k=1$  (0-30 cm), layer  $k=2$  (30-60 cm), and layer  $k=3$  (60-100 cm). Blue arrows indicate the movement of particles: upwards in layer  $k=1$  and downwards in layers  $k=2$  and  $k=3$ . At the top, there are roots and wavy lines representing evaporation. The soil surface is labeled 'soil surface' with an arrow pointing down.

**Fig. 1.** Soil profile scheme. Index  $i$  indicates the depth from the soil surface, ranging from 0 to 100 cm in 1 cm increments. Index  $k$  identifies the layer in which the particle resides. Three layers are considered in this study: the first layer ( $k = 1$ ) spans 0–30 cm, the second layer ( $k = 2$ ) spans 30–60 cm, and the third layer ( $k = 3$ ) spans 60–100 cm. These layer boundaries correspond to the depths of the TDR rods employed (30, 60, and 100 cm).

the function  $E_\alpha(-t^\alpha)$  behaves, see Baleanu et al. (2016), as a stretched exponential for  $t \rightarrow 0$

$$1 - E_\alpha(-t^\alpha) \simeq 1 - e^{-Ct^\alpha} \quad (8)$$

and has a power law tail for  $t \rightarrow \infty$

$$E_\alpha(-t^\alpha) \simeq \frac{t^{-\alpha}}{\Gamma(1-\alpha)}. \quad (9)$$

Since  $\alpha \in (0, 1)$  the Mittag-Leffler distribution is a heavy tailed distribution (see more on fractional calculus and the corresponding heavy-tailed distributions in Meerschaert and Sikorskii (2012); see Meerschaert and Toaldo (2019) for recent generalizations). The distribution function is differentiable on  $(0, +\infty)$  and the density is singular at zero. The behavior of the survival function makes clear that it has infinite mean. The density of the Mittag-Leffler distribution is shown in Fig. 2 for different values of the parameter  $\alpha$ . The Mittag-Leffler distribution of the waiting times is chosen to model the trapping effect to which water particles are subjected during their motion through heterogeneous porous media. Because of the properties of the Mittag-Leffler distribution, the traps tend to be either very short, due to the singularity of the density at zero (see (8)), or very long, since the distribution is heavy tailed with infinite mean (see (9)). The parameter  $\alpha$  of the Mittag-Leffler distribution is related to the duration of the trapping times: for small  $\alpha$  values, the waiting times are very long, meaning that the particles move slowly; whereas for large  $\alpha$  values, the waiting

times decrease, and the particles move more quickly. Heterogeneous porous media such as soils naturally produce heavy-tailed residence or waiting time distributions due to long trapping events and their fractal-like structural organization. Real soils display multiscale heterogeneity without a single dominant timescale governing water transport. This arises from complex pore geometries, dead ends, preferential flow paths, and low-permeability zones. Water particles may travel rapidly through well-connected paths, but they can also remain trapped for long periods in very low-velocity or stagnant regions. Consequently, a power-law distribution for waiting times between jumps defined by the Mittag-Leffler function (5) emerges naturally with the anomalous exponent  $\alpha$  varying in the range  $(0, 1)$ .

The behavior of this process can be described by probability fluxes that, in our context, represent the flux of water particles. The proportion of outgoing water particles at time  $t$  from the position  $i$  represent the outgoing water flux that we denote  $J_i^-(t)$ . It can be represented probabilistically as the following probability

$$J_i^-(t) = P(X(t+dt) \neq i, X(t) = i), \quad (10)$$

and consequently the ingoing water flux can be represented probabilistically as

$$J_i^+(t) = P(X(t+dt) = i, X(t) \neq i). \quad (11)$$

Conservation of mass is represented, in this context, by probability masses that must always sum to one. Indeed, by suitable manipulations,![Mittag-Leffler Density for different alpha. A line graph showing four probability density functions for the Mittag-Leffler distribution with alpha values 0.3, 0.5, 0.7, and 0.9. The x-axis is time t from 0 to 10, and the y-axis is Density from 0.0 to 1.5. All curves start at (0, 1.5) and decay towards zero. Higher alpha values result in curves that decay more slowly.](12b83f7cf46e69b26d8407b405eb1b7a_3_img.webp)

Fig. 2. Probability density of the Mittag-Leffler distribution. In the plot, the density of Mittag-Leffler distribution is shown for different values of the parameter  $\alpha$ .

using the total probability law and the conservation of probability masses, it is not hard to obtain, for the outgoing flux,

$$J_i^-(t) = \partial_t^{1-\alpha(i)} p_{li}(t) \quad \text{for } \alpha(i) = \begin{cases} \alpha_1, & i \in I_1, \\ \alpha_2, & i \in I_2, \\ \alpha_3, & i \in I_3, \end{cases} \quad (12)$$

where  $\partial_t^\alpha$  is the Riemann–Liouville fractional derivative, i.e., for  $\alpha \in (0, 1)$

$$\partial_t^\alpha u(t) = \frac{1}{\Gamma(1-\alpha)} \frac{d}{dt} \int_0^t u(w)(t-w)^{-\alpha} dw.$$

The state probabilities  $p_{li}(t) = P(X(t) = i | X(0) = l)$  (proportion of water in the state  $i$ ) solve the system of fractional Kolmogorov forward equations

$$\begin{aligned} \frac{d}{dt} p_{li}(t) &= -\partial_t^{1-\alpha_1} p_{li}(t) + \partial_t^{1-\alpha_1} p_{li+1}(t) & 1 \leq i < 29 \\ \frac{d}{dt} p_{li}(t) &= -\partial_t^{1-\alpha_2} p_{li}(t) + \partial_t^{1-\alpha_2} p_{li-1}(t) & 30 < i < 60 \\ \frac{d}{dt} p_{li}(t) &= -\partial_t^{1-\alpha_3} p_{li}(t) + \partial_t^{1-\alpha_3} p_{li-1}(t) & 60 < i \leq 100 \end{aligned} \quad (13)$$

while for the state  $i = 29$  one has  $\frac{d}{dt} p_{l29}(t) = -\partial_t^{1-\alpha_1} p_{l29}(t)$  because there is only the outgoing upward flux,  $\frac{d}{dt} p_{l30}(t) = -\partial_t^{1-\alpha_2} p_{l30}(t)$  for state  $i = 30$  because there is only the outgoing downward flux, since the water in the first layer does not reach the second, which is below the Zero Flux Plane, and  $\frac{d}{dt} p_{l60}(t) = -\partial_t^{1-\alpha_3} p_{l60}(t) + \partial_t^{1-\alpha_2} p_{l59}(t)$  for state  $i = 60$  because the parameter  $\alpha$  changes from the second to the third layer. The reader can consult (Ricciuti and Toaldo, 2017, eqs (4.14) and (4.15)) for the details about the computation. We remark that the interplay between space dependent continuous time random walks and variable order fractional equation is also investigated in Kolokoltsov (2023), Fedotov and Han (2019) and Straka (2018); for a comprehensive review on fractional calculus methods in hydrology see Benson et al. (2013).

We can rewrite Eq. (13) in terms of soil moisture  $\theta_i(t)$  in state  $i$  (depth  $i$  cm) at time  $t$ , where soil moisture is the volumetric water content in the soil, that is, the ratio of water volume to soil volume ( $\text{m}^3/\text{m}^3$ ) in an ideal parallelepiped with a height of one centimeter and a square base with a side of one meter, extending from  $i$  to  $i - 1$  centimeters of depth. Since the mass balance equation holds in each state  $i$ , we have for  $1 \leq i < 30$

$$\frac{d\theta_i(t)}{dt} = -J_i(t) + J_{i+1}(t), \quad (14)$$

and for  $30 \leq i \leq 100$

$$\frac{d\theta_i(t)}{dt} = -J_i(t) + J_{i-1}(t), \quad (15)$$

where  $J_i(t)$  is the flux of water from the state  $i$ . Then, considering that the Mittag-Leffler distribution parameter varies depending on the soil layer, we have for each state  $i$

$$\begin{aligned} \frac{d\theta_i(t)}{dt} &= -\partial_t^{1-\alpha_1} \theta_i(t) + \partial_t^{1-\alpha_1} \theta_{i+1}(t) & 1 \leq i < 29 \\ \frac{d\theta_i(t)}{dt} &= -\partial_t^{1-\alpha_2} \theta_i(t) + \partial_t^{1-\alpha_2} \theta_{i-1}(t) & 30 < i < 60 \\ \frac{d\theta_i(t)}{dt} &= -\partial_t^{1-\alpha_3} \theta_i(t) + \partial_t^{1-\alpha_3} \theta_{i-1}(t) & 60 < i \leq 100 \end{aligned} \quad (16)$$

with boundary conditions:  $\frac{d\theta_i(t)}{dt} = -\partial_t^{1-\alpha_1} \theta_i(t)$  for  $i = 29$ ,  $\frac{d\theta_i(t)}{dt} = -\partial_t^{1-\alpha_2} \theta_i(t)$  for  $i = 30$ ,  $\frac{d\theta_i(t)}{dt} = -\partial_t^{1-\alpha_3} \theta_i(t) + \partial_t^{1-\alpha_2} \theta_{i-1}(t)$  for  $i = 60$ .

### 2.3. Computational methods for parameters calibration

We simulate the movement of  $10^5$  water particles starting from an initial vertical distribution, estimated from data, and moving according to the process introduced in Section 2.2, see Fig. 3 for some sampled trajectories. To obtain the initial vertical water distribution, we compute from soil moisture measurements the proportion of water, relative to the total water content up to a depth of 1 m, in each of the three layers at the initial time that is, approximately, 24 h after a rainfall. Soil moisture represents the volumetric water content in the soil, i.e., the volume of water in relation to the total volume of the soil. So, starting from soil moisture measurements from the surface to 30, 60 and 100 cm depths (the data explained in Section 2.1), i.e. the time series, with daily resolution,  $\theta^{30}(s)$ ,  $\theta^{60}(s)$  and  $\theta^{100}(s)$  respectively, where  $s$  are days, the proportions of water in each layer  $I_k$  (see Eq. (6)), for  $k = 1, 2, 3$ , at time  $s$  can be obtained. Indeed, the data described in Section 2.1 provide us the times series  $\theta^{30}(s)$ ,  $\theta^{60}(s)$  and  $\theta^{100}(s)$ : these quantities represent the volumetric proportion of water with respect to the volume of soil at the depths 30, 60, 100 cm, i.e.,

$$\theta^{30}(s) = \frac{W^{30}(s)}{V^{30}}, \quad \theta^{60}(s) = \frac{W^{60}(s)}{V^{60}}, \quad \theta^{100}(s) = \frac{W^{100}(s)}{V^{100}} \quad (17)$$

where  $V^{30} = 0.3 \text{ m}^3$ ,  $V^{60} = 0.6 \text{ m}^3$  and  $V^{100} = 1 \text{ m}^3$  while  $W^{30}(s)$ ,  $W^{60}(s)$  and  $W^{100}(s)$  are the corresponding volumes of water in cubic meters. It follows that the volumes of water in the three layers (from 0 to 30 cm, from 30 to 60 cm and from 60 to 100 cm, in a reference![Figure 3: Simulated trajectories of water particles. The plot shows multiple colored step-like lines representing the vertical position (y-axis, 0 to 100 cm) of individual particles over time (x-axis, 0 to 250 hours). The trajectories start at various depths and move upwards in discrete steps, with some particles reaching the surface and others remaining at lower depths.](7e15556bdf37f071a5147c33ca1050d3_3_img.webp)

Fig. 3. Simulated trajectories of water particles where the position is measured in centimeters and the time in hours.

parallelepiped with a square base with a side length of 1 m) can be computed as

$$\begin{aligned} W_1(s) &:= W^{30}(s) = 0.3 \theta^{30}(s), \\ W_2(s) &:= W^{60}(s) - W^{30}(s) = 0.6 \theta^{60}(s) - 0.3 \theta^{30}(s), \\ W_3(s) &:= W^{100}(s) - W^{60}(s) = \theta^{100}(s) - 0.6 \theta^{60}(s). \end{aligned} \tag{18}$$

Following the same argument we denote  $W_{\text{tot}} = W^{100}(0)$  the initial (1 day after the end of a rain) amount of water in the soil down to a depth of 1 m. Therefore, the proportion of water in each layer  $I_k$ , for  $k = 1, 2, 3$ , are obtained as

$$p_{I_1}(s) = \frac{W_1(s)}{W_{\text{tot}}}, \quad p_{I_2}(s) = \frac{W_2(s)}{W_{\text{tot}}}, \quad p_{I_3}(s) = \frac{W_3(s)}{W_{\text{tot}}}. \tag{19}$$

The proportions in the three layers at the initial time  $p_{I_1}(0), p_{I_2}(0), p_{I_3}(0)$  are the percentage of particles that start from each layer, and within each layer we assume that the initial states are randomly generated from a uniform distribution. Note that, in this framework, the interplay between  $W_1(s), W_2(s), W_3(s)$ , obtained from the observed data, and the soil moisture  $\theta_i(s)$  introduced in previous Section 2.2 is given by

$$\sum_{i=1}^{30} 0.01 \theta_i(s) = W_1(s), \quad \sum_{i=31}^{60} 0.01 \theta_i(s) = W_2(s), \quad \sum_{i=61}^{100} 0.01 \theta_i(s) = W_3(s). \tag{20}$$

Once the initial vertical water distribution is generated, we simulate the trajectories of  $N = 10^5$  particles moving according to the proposed model. The particles perform jumps of 1 cm, either upward or downward depending on the soil layer, with waiting times following the Mittag-Leffler distribution. This distribution has parameter  $\alpha_1$  in the first layer  $I_1$ ,  $\alpha_2$  in the second layer  $I_2$ , and  $\alpha_3$  in the third layer  $I_3$ , so we denote with  $X^{\alpha_1 \alpha_2 \alpha_3}(t)$  the process parametrized by  $\alpha_1, \alpha_2, \alpha_3$ . We use as estimates of distributions the proportions of water particles in each layer with daily resolution computed as follows. Indicating with  $N_i(t)$  the number of particles in the state  $i$  at time  $t$  (in hours) and with  $N$  the total number of particles, we have

$$\begin{aligned} \hat{P}(X^{\alpha_1 \alpha_2 \alpha_3}(t) \in I_1) &= \sum_{i=1}^{30} \frac{N_i(t)}{N} \\ \hat{P}(X^{\alpha_1 \alpha_2 \alpha_3}(t) \in I_2) &= \sum_{i=31}^{60} \frac{N_i(t)}{N} \\ \hat{P}(X^{\alpha_1 \alpha_2 \alpha_3}(t) \in I_3) &= \sum_{i=61}^{100} \frac{N_i(t)}{N} \end{aligned} \tag{21}$$

where  $\hat{P}(X^{\alpha_1 \alpha_2 \alpha_3}(t) \in I_k)$  indicates the estimated probability that the process is in the layer  $I_k$  at time  $t$ .

Then we compare these proportions of water particles in each layer, with daily resolution, with the proportions obtained from the observed data  $p_{I_1}(s), p_{I_2}(s), p_{I_3}(s), s = 1, 2, \dots$ , where  $s$  are days, to estimate the three parameters  $\alpha_1, \alpha_2, \alpha_3$  of the Mittag-Leffler distributions by minimizing the total variation distance between the simulated proportions and those measured from the data. Since we need to compare the (simulated) distribution of the CTRW process at different times  $t = 24 s, s = 1, \dots, n_d$ , we minimize the sum over  $s$  of the absolute distance between the simulated and observed distributions. To reduce the computational complexity, since the motion in the first layer does not affect the layers below, and similarly, the motion in the third layer does not affect the layers above, we fit the parameters separately. So we first consider layer 1, ignoring layers 2 and 3. Then we fit layer 2, ignoring layer 3, and finally, with the first two parameters  $\alpha_1$  and  $\alpha_2$  fixed, we fit layer 3. Formally, we proceed in the following three steps:

$$\hat{\alpha}_1 = \operatorname{argmin}_{\alpha \in \mathbb{D}} \frac{1}{2} \sum_{s=1}^{n_d} |\hat{P}(X^{\alpha \alpha \alpha}(24 s) \in I_1) - p_{I_1}(s)|, \tag{22}$$

$$\hat{\alpha}_2 = \operatorname{argmin}_{\alpha \in \mathbb{D}} \frac{1}{2} \sum_{s=1}^{n_d} |\hat{P}(X^{\hat{\alpha}_1 \alpha \alpha}(24 s) \in I_2) - p_{I_2}(s)|, \tag{23}$$

$$\hat{\alpha}_3 = \operatorname{argmin}_{\alpha \in \mathbb{D}} \frac{1}{2} \sum_{s=1}^{n_d} |\hat{P}(X^{\hat{\alpha}_1 \hat{\alpha}_2 \alpha}(24 s) \in I_3) - p_{I_3}(s)|, \tag{24}$$

where  $\mathbb{D} = \{0.01, 0.02, \dots, 0.99\}$ ,  $\hat{P}(X^{\alpha_1 \alpha_2 \alpha_3}(t) \in I_k)$  are the probabilities estimated from simulations (21),  $p_{I_k}(s)$  are the proportions of water obtained from the data (19) for a number of days equal to  $n_d$  (approximately 10) and  $I_k$  indicates the  $k$ th layer. Therefore, we first estimate the parameter  $\alpha_1$  for the first layer, which does not influence the trajectories of the other two layers since the particles move upward. Then we estimate the parameter  $\alpha_2$  for the second layer, and finally, we estimate the parameter  $\alpha_3$  for the third layer using the previously estimated  $\alpha_2$ . To directly compare with the soil moisture measurements  $\theta^{30}(s), \theta^{60}(s), \theta^{100}(s)$ , we compute also the estimated soil moisture from the surface to 30, 60, and 100 cm depths from (19) and (18) considering the estimated quantities, as follows

$$\begin{aligned} \hat{\theta}^{30}(t) &= \frac{\hat{P}(X^{\hat{\alpha}_1 \hat{\alpha}_2 \hat{\alpha}_3} \in I_1) W_{\text{tot}}}{0.3} = \sum_{i=1}^{30} \frac{N_i(t)}{N} \frac{W_{\text{tot}}}{0.3}, \\ \hat{\theta}^{60}(t) &= \frac{\hat{P}(X^{\hat{\alpha}_1 \hat{\alpha}_2 \hat{\alpha}_3} \in I_2) W_{\text{tot}} + 0.3 \hat{\theta}^{30}(t)}{0.6} = \sum_{i=1}^{60} \frac{N_i(t)}{N} \frac{W_{\text{tot}}}{0.6}, \\ \hat{\theta}^{100}(t) &= \hat{P}(X^{\hat{\alpha}_1 \hat{\alpha}_2 \hat{\alpha}_3} \in I_3) W_{\text{tot}} + 0.6 \hat{\theta}^{60}(t) = \sum_{i=1}^{100} \frac{N_i(t)}{N} W_{\text{tot}}, \end{aligned} \tag{25}$$using these for  $t = 24 s, s = 1, \dots, n_d$ .

We consider various periods between rainfall events during different seasons of the years 2006, 2007, and 2008. For each of these periods, we estimate the parameters  $\alpha_1, \alpha_2$ , and  $\alpha_3$ , and analyze the relationship between these parameters and the initial soil water content in the three layers, as well as the average potential evapotranspiration for the first layer. Finally, we validate the model using the estimated values of the three parameters through a leave-one-out cross-validation procedure, considering the initial conditions to estimate soil moisture, as explained in the next paragraph.

### 3. Results and soil moisture forecast

In this section, we present the results of the parameter estimation procedure introduced in Section 2.3, applied to several dry periods of the dataset. We also explain how the model can be used for soil moisture forecast, using a clear linear relationship between the estimated parameters and quantitatively observable variables.

#### 3.1. Parameters estimation

We apply the methods of Section 2.3 to twenty dry spells of approximately ten days during the years 2006, 2007 and 2008. For each period, we estimate the three parameters  $\alpha_1, \alpha_2, \alpha_3$  (the Mittag-Leffler distribution parameters for each soil layer), which are reported in Table 1. The parameter estimation is carried out by minimizing, in each soil layer, the distance between the proportion of water particles estimated with simulations and the proportion of water obtained from soil moisture measurements with daily resolution (see Eqs. (22), (23), (24)). Table 1 reports the periods without rainfall considered, the average potential evapotranspiration (ET) for each period for the first layer, and the soil water content in the three layers at the initial time ( $W_1(0), W_2(0), W_3(0)$ ), that is, the first day of each period, as well as the estimated parameters for the three layers  $\hat{\alpha}_1, \hat{\alpha}_2, \hat{\alpha}_3$ . Specifically, the average potential evapotranspiration is obtained from daily meteorological data taken in Grugliasco (Turin), at the same experimental site of soil moisture data measured by the University of Turin. Simulated (in black) and measured (in red) soil moisture values from the surface to depths of 30, 60 and 100 cm, with daily resolution, for three dry periods are shown in Fig. 4. We compare the estimated time series  $\hat{\theta}^{30}(24 s), \hat{\theta}^{60}(24 s), \hat{\theta}^{100}(24 s)$  with the corresponding measured time series  $\theta^{30}(s), \theta^{60}(s), \theta^{100}(s)$  over a period of approximately 10 days.

Once the parameters  $\alpha_1, \alpha_2$ , and  $\alpha_3$  have been estimated for all periods considered, we fit linear regressions between the obtained  $\alpha$  values and the initial water volumes  $W_2(0)$  and  $W_3(0)$  (see formula (18) for  $t = 0$ ), for layers 2 and 3, considering summer (from April to September) and winter periods (from October to March) separately. For layer 2 we obtain  $R^2 = 0.47$  for the summer periods and  $R^2 = 0.9$  for the winter periods, whereas for layer 3 we obtain  $R^2 = 0.4$  for the summer periods and  $R^2 = 0.46$  for the winter periods. For the first layer, instead, since the evapotranspiration phenomenon is crucial, we fit a multiple linear regression between the values of  $\alpha_1$  and those of  $W_1(0)$  and ET, obtaining  $R^2 = 0.53$  for summer periods and  $R^2 = 0.73$  for winter periods. Therefore, for the second and third layers, there is a positive correlation between the values of the Mittag-Leffler distribution parameters, related to the duration of the trapping times, and the initial water content in the layer, both for the summer and winter periods. This means that, given the initial soil moisture, it is possible to estimate the parameters  $\alpha_2$  and  $\alpha_3$  using the coefficients obtained from linear regressions. Instead, for the first layer it is possible to estimate  $\alpha_1$  given the initial soil moisture condition in the layer and the average potential evapotranspiration over the period considered. In particular, there is a positive correlation ( $r = 0.69$ ) between the values of  $\alpha_1$  and those of the average potential evapotranspiration for the summer periods and a positive correlation ( $r = 0.73$ ) between the values of  $\alpha_1$  and those of the initial soil moisture for the winter periods.

**Table 1**

Parameters estimation: dry spells (dd-mm-yy) of the data, average potential evapotranspiration ET (mm/day), initial water volume  $W_i(0), i = 1, 2, 3$ , for the three layers (0–30 cm, 30–60 cm, 60–100 cm), and the estimated parameters  $\hat{\alpha}_1, \hat{\alpha}_2, \hat{\alpha}_3$  of Mittag-Leffler distributions for the three layers.

<table border="1">
<thead>
<tr>
<th>Dry spells</th>
<th>ET</th>
<th><math>W_1(0)</math></th>
<th><math>W_2(0)</math></th>
<th><math>W_3(0)</math></th>
<th><math>\hat{\alpha}_1</math></th>
<th><math>\hat{\alpha}_2</math></th>
<th><math>\hat{\alpha}_3</math></th>
</tr>
</thead>
<tbody>
<tr><td>31/01/06–11/02/06</td><td>0.934</td><td>0.080</td><td>0.073</td><td>0.059</td><td>0.49</td><td>0.36</td><td>0.44</td></tr>
<tr><td>26/02/06–08/03/06</td><td>1.351</td><td>0.054</td><td>0.068</td><td>0.061</td><td>0.25</td><td>0.35</td><td>0.48</td></tr>
<tr><td>22/05/06–01/06/06</td><td>4.569</td><td>0.029</td><td>0.046</td><td>0.051</td><td>0.45</td><td>0.29</td><td>0.40</td></tr>
<tr><td>25/06/06–05/07/06</td><td>5.341</td><td>0.052</td><td>0.029</td><td>0.033</td><td>0.52</td><td>0.10</td><td>0.29</td></tr>
<tr><td>27/09/06–07/10/06</td><td>2.268</td><td>0.052</td><td>0.059</td><td>0.066</td><td>0.35</td><td>0.33</td><td>0.53</td></tr>
<tr><td>25/10/06–04/11/06</td><td>1.518</td><td>0.044</td><td>0.042</td><td>0.044</td><td>0.26</td><td>0.10</td><td>0.10</td></tr>
<tr><td>19/12/06–26/12/06</td><td>0.648</td><td>0.052</td><td>0.055</td><td>0.057</td><td>0.22</td><td>0.16</td><td>0.10</td></tr>
<tr><td>09/03/07–19/03/07</td><td>2.471</td><td>0.038</td><td>0.043</td><td>0.046</td><td>0.28</td><td>0.10</td><td>0.16</td></tr>
<tr><td>05/04/07–14/04/07</td><td>3.238</td><td>0.058</td><td>0.058</td><td>0.048</td><td>0.36</td><td>0.14</td><td>0.14</td></tr>
<tr><td>16/06/07–26/06/07</td><td>4.825</td><td>0.053</td><td>0.061</td><td>0.064</td><td>0.41</td><td>0.40</td><td>0.56</td></tr>
<tr><td>01/09/07–09/09/07</td><td>3.841</td><td>0.044</td><td>0.047</td><td>0.046</td><td>0.47</td><td>0.21</td><td>0.43</td></tr>
<tr><td>19/09/07–25/09/07</td><td>2.942</td><td>0.037</td><td>0.040</td><td>0.038</td><td>0.39</td><td>0.22</td><td>0.17</td></tr>
<tr><td>08/10/07–18/10/07</td><td>1.906</td><td>0.046</td><td>0.045</td><td>0.039</td><td>0.22</td><td>0.10</td><td>0.31</td></tr>
<tr><td>27/10/07–06/11/07</td><td>1.263</td><td>0.060</td><td>0.058</td><td>0.042</td><td>0.30</td><td>0.25</td><td>0.10</td></tr>
<tr><td>17/01/08–27/01/08</td><td>0.924</td><td>0.060</td><td>0.065</td><td>0.065</td><td>0.40</td><td>0.32</td><td>0.42</td></tr>
<tr><td>22/04/08–28/04/08</td><td>3.626</td><td>0.059</td><td>0.065</td><td>0.070</td><td>0.43</td><td>0.41</td><td>0.64</td></tr>
<tr><td>01/05/08–10/05/08</td><td>4.022</td><td>0.039</td><td>0.046</td><td>0.047</td><td>0.51</td><td>0.20</td><td>0.40</td></tr>
<tr><td>01/07/08–11/07/08</td><td>5.223</td><td>0.050</td><td>0.041</td><td>0.037</td><td>0.50</td><td>0.13</td><td>0.38</td></tr>
<tr><td>19/07/08–28/07/08</td><td>5.067</td><td>0.049</td><td>0.044</td><td>0.037</td><td>0.48</td><td>0.31</td><td>0.49</td></tr>
<tr><td>24/09/08–04/10/08</td><td>2.280</td><td>0.046</td><td>0.053</td><td>0.048</td><td>0.35</td><td>0.19</td><td>0.37</td></tr>
</tbody>
</table>

This confirms that evapotranspiration is the crucial phenomenon in the first soil layer during summer, while it is less dominant in winter, when there is instead a strong relationship with initial soil moisture, as in the 30–60 cm and 60–100 cm layers. Therefore, the proposed model to simulate vertical water flow in the soil has three parameters and requires the initial condition of soil moisture and the average potential evapotranspiration. Given these initial conditions, it is possible to estimate the three parameters  $\alpha_1, \alpha_2$ , and  $\alpha_3$  of the Mittag-Leffler distributions for waiting times in the three soil layers and simulate the movement of water particles according to the proposed model to obtain soil moisture in the absence of rainfall events. The application of this model and the estimation of its parameters were carried out using the data described in the Section 2.1, which refers to the loamy-sandy soil covered with meadow of the experimental site. In the next paragraph, we present the leave-one-out cross-validation of the model, applying this procedure to the same dataset.![Figure 4: A 3x3 grid of plots showing soil moisture (0-30 cm, 0-60 cm, 0-100 cm) over time for three dry periods (2006, 2007, 2008). Each plot compares simulated values (black dots) with measured values (red dots). The plots show a gradual decrease in soil moisture over time, with the rate of decrease varying by soil depth and dry period.](bb69b7611e0481f6a15df68ac54b0a43_3_img.webp)

**Fig. 4.** Parameters estimation: soil moisture from the surface to 30, 60, and 100 cm depths with daily resolution for three dry periods, obtained using the parameters  $\hat{\alpha}_1$ ,  $\hat{\alpha}_2$ ,  $\hat{\alpha}_3$  of the Mittag-Leffler distributions, estimated through the optimization procedure with simulations. The black points represent the soil moisture simulated with the model whereas the red points are the corresponding measurements.

$\alpha_2$  values, and finally, we predict  $\bar{\alpha}_3$  using the regression coefficients with  $W_3(0)$  fitted to the remaining  $\alpha_3$  values. Once the values of  $\bar{\alpha}_1$ ,  $\bar{\alpha}_2$ , and  $\bar{\alpha}_3$  for the three soil layers and for each period are obtained, we run the model simulations (with  $10^4$  or  $10^5$  trajectories) using these three parameters together to obtain  $\hat{\theta}^{30}(24\text{ s})$ ,  $\hat{\theta}^{60}(24\text{ s})$ ,  $\hat{\theta}^{100}(24\text{ s})$  and compute the corresponding errors with respect to the observed soil moisture at each depth  $\theta^{30}(s)$ ,  $\theta^{60}(s)$ ,  $\theta^{100}(s)$ . In Fig. 5 simulated (in black) and measured (in red) soil moisture values from the surface to depths of 30, 60 and 100 cm are compared for three dry periods. Table 2 reports the predicted values of  $\bar{\alpha}_1$ ,  $\bar{\alpha}_2$  and  $\bar{\alpha}_3$  for each dry period, together with the corresponding Root Mean Square Errors computed on simulated soil moisture from the surface to depths of 30, 60 and 100 cm ( $RMSE_1$ ,  $RMSE_2$ , and  $RMSE_3$ , respectively). As shown in Table 2, the RMSE values depend on dry periods and soil depths and range from a minimum of 0.002 to a maximum of 0.023.

We remark that the previously described procedure can be meant as a forecast procedure of soil moisture. Indeed, the observed dry spells are treated as a sample and their chronological order has no relevance: soil moisture evolution during a dry spell can be assumed independent of previous dry spells, conditionally on its current (initial) value, since all dry spells are separated by rainfall events.

**4. Conclusions**

In this study, daily soil moisture measurements collected with vertical TDR rods from the surface to depths of 30, 60 and 100 cm during dry periods in 2006, 2007 and 2008 at an experimental site in Grugliasco (Turin, Italy) are used. A space-dependent continuous time random walk is proposed as a stochastic model to simulate soil moisture between rainfall events, and the results are compared with observed data. The proposed model uses only the initial water content in the various soil layers, approximately 24 h after a rainfall event, as input to estimate the initial vertical water distribution. It is assumed that water particles in the soil move by jumping in 1-cm steps upward (in the layer from 0 to 30 cm) because of grass evapotranspiration or downward (between 30 and 100 cm), with waiting times between jumps following the Mittag-Leffler distribution. In particular, the parameter of the Mittag-Leffler distribution depends on the particle's position:  $\alpha_1$  in

**Table 2**

Model validation: dry spells (dd-mm-yy) of the data, the parameters  $\bar{\alpha}_1, \bar{\alpha}_2, \bar{\alpha}_3$  of Mittag-Leffler distributions predicted with linear regressions for the three layers, and the Root Mean Square Errors (RMSE) computed using  $\bar{\alpha}_1, \bar{\alpha}_2, \bar{\alpha}_3$  in the simulations (using  $N = 10^5$  trajectories) of soil moisture from the surface to depths of 30, 60 and 100 cm.

<table border="1">
<thead>
<tr>
<th>Dry spells</th>
<th><math>\bar{\alpha}_1</math></th>
<th><math>\bar{\alpha}_2</math></th>
<th><math>\bar{\alpha}_3</math></th>
<th><math>RMSE_1</math></th>
<th><math>RMSE_2</math></th>
<th><math>RMSE_3</math></th>
</tr>
</thead>
<tbody>
<tr><td>31/01/06–11/02/06</td><td>0.46</td><td>0.41</td><td>0.36</td><td>0.008</td><td>0.01</td><td>0.006</td></tr>
<tr><td>26/02/06–08/03/06</td><td>0.31</td><td>0.34</td><td>0.38</td><td>0.006</td><td>0.008</td><td>0.011</td></tr>
<tr><td>22/05/06–01/06/06</td><td>0.53</td><td>0.22</td><td>0.43</td><td>0.017</td><td>0.011</td><td>0.01</td></tr>
<tr><td>25/06/06–05/07/06</td><td>0.48</td><td>0.12</td><td>0.27</td><td>0.022</td><td>0.01</td><td>0.011</td></tr>
<tr><td>27/09/06–07/10/06</td><td>0.36</td><td>0.24</td><td>0.42</td><td>0.009</td><td>0.006</td><td>0.01</td></tr>
<tr><td>25/10/06–04/11/06</td><td>0.23</td><td>0.08</td><td>0.22</td><td>0.006</td><td>0.006</td><td>0.003</td></tr>
<tr><td>19/12/06–26/12/06</td><td>0.24</td><td>0.22</td><td>0.39</td><td>0.016</td><td>0.01</td><td>0.012</td></tr>
<tr><td>09/03/07–19/03/07</td><td>0.25</td><td>0.10</td><td>0.23</td><td>0.021</td><td>0.007</td><td>0.006</td></tr>
<tr><td>05/04/07–14/04/07</td><td>0.42</td><td>0.36</td><td>0.43</td><td>0.009</td><td>0.01</td><td>0.002</td></tr>
<tr><td>16/06/07–26/06/07</td><td>0.48</td><td>0.31</td><td>0.52</td><td>0.016</td><td>0.02</td><td>0.01</td></tr>
<tr><td>01/09/07–09/09/07</td><td>0.43</td><td>0.24</td><td>0.38</td><td>0.008</td><td>0.004</td><td>0.005</td></tr>
<tr><td>19/09/07–25/09/07</td><td>0.42</td><td>0.18</td><td>0.34</td><td>0.012</td><td>0.01</td><td>0.005</td></tr>
<tr><td>08/10/07–18/10/07</td><td>0.29</td><td>0.12</td><td>0.07</td><td>0.012</td><td>0.006</td><td>0.003</td></tr>
<tr><td>27/10/07–06/11/07</td><td>0.35</td><td>0.24</td><td>0.20</td><td>0.023</td><td>0.011</td><td>0.007</td></tr>
<tr><td>17/01/08–27/01/08</td><td>0.30</td><td>0.31</td><td>0.45</td><td>0.007</td><td>0.006</td><td>0.005</td></tr>
<tr><td>22/04/08–28/04/08</td><td>0.39</td><td>0.33</td><td>0.52</td><td>0.011</td><td>0.016</td><td>0.014</td></tr>
<tr><td>01/05/08–10/05/08</td><td>0.44</td><td>0.23</td><td>0.39</td><td>0.011</td><td>0.007</td><td>0.006</td></tr>
<tr><td>01/07/08–11/07/08</td><td>0.49</td><td>0.21</td><td>0.29</td><td>0.014</td><td>0.007</td><td>0.008</td></tr>
<tr><td>19/07/08–28/07/08</td><td>0.49</td><td>0.20</td><td>0.27</td><td>0.017</td><td>0.01</td><td>0.009</td></tr>
<tr><td>24/09/08–04/10/08</td><td>0.30</td><td>0.20</td><td>0.23</td><td>0.012</td><td>0.006</td><td>0.005</td></tr>
</tbody>
</table>

the first soil layer (0–30 cm),  $\alpha_2$  in the second layer (30–60 cm), and  $\alpha_3$  in the third layer (60–100 cm). The waiting times between jumps represent the trapping effect of water caused by soil heterogeneity. Therefore, unlike other physically-based models (e.g. bucket models or Richards' equation ones), the proposed model relies on a limited number of assumptions and involves only three parameters, i.e. the parameters of Mittag-Leffler distributions, to estimate by comparing the results of simulations with soil moisture measurements.

The three parameters of the model,  $\alpha_1$ ,  $\alpha_2$ , and  $\alpha_3$ , are estimated for each dry spell considered using an optimization procedure based on the proportions of water in each soil layer obtained from the measured data. Moreover, we show that these parameters are related to two observable variables. In particular, we fit a multiple linear regression![Figure 5: A 3x3 grid of plots showing soil moisture (0-30 cm, 0-60 cm, 0-100 cm) over time for three dry periods. Each plot compares simulated data (black points with error bars) to measurements (red points with error bars). The plots are titled with parameters: top row (alpha1=0.23, alpha2=0.08, alpha3=0.22), middle row (alpha1=0.42, alpha2=0.36, alpha3=0.43), and bottom row (alpha1=0.3, alpha2=0.2, alpha3=0.23).](e5600a5b1d7331913a56d2fc7ce8cadf_3_img.webp)

**Fig. 5.** Model validation: soil moisture from the surface to 30, 60, and 100 cm depths with daily resolution for three dry periods, obtained using the parameters  $\bar{\alpha}_1$ ,  $\bar{\alpha}_2$ ,  $\bar{\alpha}_3$  of the Mittag-Leffler distributions, estimated through linear regressions for each layer for model validation. The black points represent the soil moisture simulated with the model (with  $N = 10^4$  simulated trajectories) and the corresponding confidence intervals obtained by a classical Gaussian approximation. The red points represent the corresponding measurements, shown with confidence intervals computed by considering the measurement error ( $\pm 0.013$ , see Topp et al. (1980), divided by  $\sqrt{32}$  where 32 is the number of probes used for the spatial mean at each depth).

between  $\alpha_1$  and both the average potential evapotranspiration and the initial water content for the first layer. For the other two layers, we fit a simple linear regression between  $\alpha_2$  and  $\alpha_3$  and the initial water content in layers 2 and 3, respectively. These regressions are fitted separately for winter and summer drought periods. Finally, using a leave-one-out cross-validation procedure, we predict the three parameters for each period by fitting the regression parameters to the remaining values of  $\alpha$  and calculating the error between the simulated soil moisture and the measured data. The obtained root mean squared errors (RMSE) for the three layers indicate a good fit between the simulations and the observed data. We obtain, in the worst case, a RMSE of 0.023 but, in almost all cases, the RMSE is strictly less than 0.01.

In conclusion, this study demonstrates that a space-dependent continuous time random walk with fractional dynamics (with power law waiting times) provides an effective stochastic model for simulating field-scale soil moisture dynamics during dry spells between rainfall events, based on simple assumptions. The proposed model requires only a limited number of parameters and enables the prediction of field-scale soil moisture using solely the initial soil moisture profile and average potential evapotranspiration. A key novelty of the model lies in its Lagrangian perspective, which explicitly follows the trajectories of individual water particles within the soil profile, which seems new in soil moisture modeling during dry spells. This particle-based perspective leads to a set of linear and analytically tractable equations, which are easier to handle than Richards' equation. Overall, the results highlight the considerable potential of this alternative modeling approach and point to promising directions for future developments. For example, we believe it would be worthwhile to clarifying and strengthening the physical connections with the parameters of the model, e.g., understanding the relationship between the jump's length and the soil type.

**5. Supplementary materials**

In this section we report, in Table 3, the relative Root Mean Square Error (rRMSE) and the Mean Error (ME) computed using  $\bar{\alpha}_1, \bar{\alpha}_2, \bar{\alpha}_3$  (see Table 2) in the simulations of soil moisture from the surface to depths

**Table 3**

Errors of model validation: dry spells (dd-mm-yy) of the data, relative Root Mean Square Errors (rRMSE) and Mean Error (ME) computed using  $\bar{\alpha}_1, \bar{\alpha}_2, \bar{\alpha}_3$  in the simulations of soil moisture from the surface to depths of 30, 60 and 100 cm.

<table border="1">
<thead>
<tr>
<th>Dry spells</th>
<th>rRMSE<sub>1</sub></th>
<th>rRMSE<sub>2</sub></th>
<th>rRMSE<sub>3</sub></th>
<th>ME<sub>1</sub></th>
<th>ME<sub>2</sub></th>
<th>ME<sub>3</sub></th>
</tr>
</thead>
<tbody>
<tr><td>31/01/06-11/02/06</td><td>0,044</td><td>0,052</td><td>0,034</td><td>0</td><td>0,009</td><td>0,002</td></tr>
<tr><td>26/02/06-08/03/06</td><td>0,045</td><td>0,047</td><td>0,072</td><td>-0,001</td><td>-0,004</td><td>-0,009</td></tr>
<tr><td>22/05/06-01/06/06</td><td>0,265</td><td>0,101</td><td>0,091</td><td>0,017</td><td>0,01</td><td>0,009</td></tr>
<tr><td>25/06/06-05/07/06</td><td>0,222</td><td>0,098</td><td>0,122</td><td>-0,011</td><td>-0,001</td><td>-0,004</td></tr>
<tr><td>27/09/06-07/10/06</td><td>0,067</td><td>0,047</td><td>0,076</td><td>0,008</td><td>-0,004</td><td>-0,01</td></tr>
<tr><td>25/10/06-04/11/06</td><td>0,043</td><td>0,04</td><td>0,023</td><td>0</td><td>0,004</td><td>0,002</td></tr>
<tr><td>19/12/06-26/12/06</td><td>0,101</td><td>0,057</td><td>0,077</td><td>0,016</td><td>0,01</td><td>0,012</td></tr>
<tr><td>09/03/07-19/03/07</td><td>0,202</td><td>0,058</td><td>0,048</td><td>-0,018</td><td>-0,005</td><td>-0,004</td></tr>
<tr><td>05/04/07-14/04/07</td><td>0,063</td><td>0,066</td><td>0,017</td><td>0,007</td><td>0,01</td><td>0,002</td></tr>
<tr><td>16/06/07-26/06/07</td><td>0,14</td><td>0,14</td><td>0,075</td><td>-0,007</td><td>-0,016</td><td>-0,007</td></tr>
<tr><td>01/09/07-09/09/07</td><td>0,075</td><td>0,03</td><td>0,039</td><td>0,003</td><td>0,001</td><td>0,004</td></tr>
<tr><td>19/09/07-25/09/07</td><td>0,125</td><td>0,094</td><td>0,047</td><td>-0,01</td><td>-0,008</td><td>-0,004</td></tr>
<tr><td>08/10/07-18/10/07</td><td>0,094</td><td>0,044</td><td>0,029</td><td>0,01</td><td>0,004</td><td>0</td></tr>
<tr><td>27/10/07-06/11/07</td><td>0,132</td><td>0,064</td><td>0,042</td><td>0,022</td><td>0,011</td><td>0,006</td></tr>
<tr><td>17/01/08-27/01/08</td><td>0,045</td><td>0,033</td><td>0,027</td><td>0,005</td><td>0,001</td><td>0</td></tr>
<tr><td>22/04/08-28/04/08</td><td>0,078</td><td>0,095</td><td>0,089</td><td>0,009</td><td>-0,013</td><td>-0,012</td></tr>
<tr><td>01/05/08-10/05/08</td><td>0,13</td><td>0,062</td><td>0,051</td><td>0,001</td><td>0,002</td><td>-0,001</td></tr>
<tr><td>01/07/08-11/07/08</td><td>0,148</td><td>0,064</td><td>0,072</td><td>-0,008</td><td>0,003</td><td>-0,004</td></tr>
<tr><td>19/07/08-28/07/08</td><td>0,154</td><td>0,076</td><td>0,078</td><td>0,005</td><td>0,003</td><td>0,005</td></tr>
<tr><td>24/09/08-04/10/08</td><td>0,097</td><td>0,042</td><td>0,039</td><td>-0,009</td><td>-0,001</td><td>-0,004</td></tr>
<tr><td>Average</td><td>0,114</td><td>0,066</td><td>0,057</td><td>0,002</td><td>0,001</td><td>-0,001</td></tr>
</tbody>
</table>

of 30, 60 and 100 cm. The rRMSE is computed as the ratio of the RMSE relative to the mean of the soil moisture measurements.

In Fig. 6 is shown the hydraulic head (positive because the reference level is located below the soil surface) over the soil depth, obtained by tensiometers during a dry spell. Water will flow from locations of higher hydraulic head to locations of lower hydraulic head. It is plain that the Zero Flux Plane is almost exactly 30 cm.![Scatter plot showing hydraulic head (cm) versus depth from the surface (cm). The x-axis represents hydraulic head in cm, ranging from 0 to 120. The y-axis represents depth from the surface in cm, ranging from 0 to 180. The data points show a clear trend where hydraulic head is highest at shallow depths and decreases as depth increases, with a notable plateau around 30 cm depth.](5a6c1186b90e1c07994de53a8998e00d_3_img.webp)

<table border="1">
<caption>Data points estimated from Figure 6</caption>
<thead>
<tr>
<th>Depth from the surface (cm)</th>
<th>Hydraulic head (cm)</th>
</tr>
</thead>
<tbody>
<tr>
<td>10</td>
<td>35</td>
</tr>
<tr>
<td>25</td>
<td>90</td>
</tr>
<tr>
<td>30</td>
<td>95</td>
</tr>
<tr>
<td>50</td>
<td>70</td>
</tr>
<tr>
<td>80</td>
<td>85</td>
</tr>
<tr>
<td>85</td>
<td>80</td>
</tr>
<tr>
<td>120</td>
<td>50</td>
</tr>
<tr>
<td>160</td>
<td>15</td>
</tr>
</tbody>
</table>

**Fig. 6.** Tensiometers data. The hydraulic head is shown over the soil depth, obtained by tensiometers during a dry spell. It is plain that the ZFP is almost exactly 30 cm.

#### CRediT authorship contribution statement

**M.C. Bovier:** Writing – review & editing, Writing – original draft, Validation, Software, Methodology, Formal analysis, Data curation, Conceptualization. **S. Fedotov:** Writing – review & editing, Writing – original draft, Validation, Supervision, Methodology, Conceptualization. **S. Ferraris:** Writing – review & editing, Writing – original draft, Validation, Supervision, Methodology, Funding acquisition, Data curation, Conceptualization. **A. Gentile:** Writing – review & editing, Writing – original draft, Validation, Methodology, Data curation, Conceptualization. **B. Toaldo:** Writing – review & editing, Writing – original draft, Validation, Supervision, Methodology, Funding acquisition, Formal analysis, Conceptualization.

#### Declaration of competing interest

The authors declare that they have no known competing financial interests or personal relationships that could have appeared to influence the work reported in this paper.

#### Acknowledgments

The authors M.C. Bovier, A. Gentile and S. Ferraris have been supported by the project NODES, which has received funding from the MUR-M4C2 1.5 of PNRR with grant agreement no. ECS00000036, by the PRIN MIUR 2017SL7ABC 005 WATZON Project, by the PRIN 2022 202295PFKP SUNSET Project, and by the Fondazione CRT, Italy

projects 2022.0998, 2023.0369, 2025.0780. The author B. Toaldo acknowledge financial support under the National Recovery and Resilience Plan (NRRP), Mission 4, Component 2, Investment 1.1, Call for tender No. 104 published on 2.2.2022 by the Italian Ministry of University and Research (MUR), funded by the European Union – NextGenerationEU– Project Title “Non-Markovian Dynamics and Non-local Equations” – 202277N5H9 - CUP: D53D23005670006 - Grant Assignment Decree No. 973 adopted on June 30, 2023, by the Italian Ministry of University and Research (MUR).

#### Data availability

Data will be made available on request.

#### References

- Anderson, M.G., McDonnell, J.J., 2005. *Encyclopedia of Hydrological Sciences*, first ed. J. Wiley.
- Baiamonte, G., Agnese, C., Cammalleri, C., Di Nardo, E., Ferraris, S., Martini, T., 2024. Applying different methods to model dry and wet spells at daily scale in a large range of rainfall regimes across Europe. *Adv. Stat. Climatol. Meteorol. Oceanogr.* 10 (1), 51–67. <http://dx.doi.org/10.5194/ascmo-10-51-2024>, URL: <https://ascmo.copernicus.org/articles/10/51/2024/>.
- Baiamonte, G., Mercalli, L., Berro, D.C., Agnese, C., Ferraris, S., 2018. Modelling the frequency distribution of inter-arrival times from daily precipitation time-series in North-West Italy. *Hydrol. Res.* 50 (1), 339–357. <http://dx.doi.org/10.2166/nh.2018.042>, arXiv:<https://iwaponline.com/hr/article-pdf/50/1/339/524985/nh0500339.pdf>.Baleanu, D., Diethelm, K., Scalas, E., Trujillo, J.J., 2016. FRACTIONAL CALCULUS Models and Numerical Methods, second ed. World Scientific, <http://dx.doi.org/10.1142/10044>.

Baudena, M., Bevilacqua, I., Canone, D., Ferraris, S., Previati, M., Provenzale, A., 2012. Soil water dynamics at a midlatitude test site: Field measurements and box modeling approaches. *J. Hydrol.* 414–415, 329–340. <http://dx.doi.org/10.1016/j.jhydrol.2011.11.009>, URL: <https://www.sciencedirect.com/science/article/pii/S0022169411007827>.

Benson, D.A., Meerschaert, M.M., Revielle, J., 2013. Fractional calculus in hydrologic modeling: A numerical perspective. *Adv. Water Resour.* 51, 479–497. <http://dx.doi.org/10.1016/j.advwatres.2012.04.005>, URL: <https://www.sciencedirect.com/science/article/pii/S0309170812000899>, 35th Year Anniversary Issue.

Bevacqua, E., Rakovec, O., Schumacher, D.L., Zink, M., Orth, R., Samaniego, L., 2024. Direct and lagged climate change effects intensified the 2022 European drought. *Nat. Geosci.* <http://dx.doi.org/10.1038/s41561-024-01559-2>.

Bovier, M., Fedotov, S., Ferraris, S., Gentile, A., Toaldo, B., 2025. Stochastic model for subsurface water flow in Swiss catchments. *Adv. Water Resour.* 196, 104883. <http://dx.doi.org/10.1016/j.advwatres.2024.104883>, URL: <https://www.sciencedirect.com/science/article/pii/S0309170824002707>.

Brussolo, E., Palazzi, E., von Hardenberg, J., Masetti, G., Vivaldo, G., Previati, M., Canone, D., Gisolo, D., Claps, P., Laio, F., 2022. Aquifer recharge in the piedmont alpine zone: historical trends and future scenarios. *Hydrol. Earth Syst. Sci.* 26 (2), 407–427. <http://dx.doi.org/10.5194/hess-26-407-2022>, URL: <https://hess.copernicus.org/articles/26/407/2022/>.

Canone, D., Ferraris, S., Sander, G., Haverkamp, R., 2008. Interpretation of water retention field measurements in relation to hysteresis phenomena. *Water Resour. Res.* 44 (4), <http://dx.doi.org/10.1029/2008WR007068>, URL: <https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1029/2008WR007068>, arXiv:<https://agupubs.onlinelibrary.wiley.com/doi/pdf/10.1029/2008WR007068>.

Dogan, M., Van Dam, R.L., Liu, G., Meerschaert, M.M., Butler, Jr., J.J., Bohling, G.C., Benson, D.A., Hyndman, D.W., 2014. Predicting flow and transport in highly heterogeneous alluvial aquifers. *Geophys. Res. Lett.* 41 (21), 7560–7565. <http://dx.doi.org/10.1002/2014GL061800>, URL: <https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1002/2014GL061800>, arXiv:<https://agupubs.onlinelibrary.wiley.com/doi/pdf/10.1002/2014GL061800>.

Dukat, P., Bednorz, E., Ziemblinska, K., Urbaniak, M., 2022. Trends in drought occurrence and severity at mid-latitude European stations (1951–2015) estimated using standardized precipitation (SPI) and precipitation and evapotranspiration (SPEI) indices. *Meteorol. Atmos. Phys.* 134, 20. <http://dx.doi.org/10.1007/s00703-022-00858-w>.

Elhanati, D., Zehe, E., Dror, I., Berkowitz, B., 2025. Transport behavior displayed by water isotopes and potential implications for assessment of catchment properties. *Hydrol. Earth Syst. Sci.* 29 (22), 6577–6587. <http://dx.doi.org/10.5194/hess-29-6577-2025>.

Fedotov, S., Han, D., 2019. Asymptotic behavior of the solution of the space dependent variable order fractional diffusion equation: Ultraslow anomalous aggregation. *Phys. Rev. Lett.* 123 (5), 050602.

Kolokoltsov, V.N., 2023. In: Mengesha, T., Salgado, A.J. (Eds.), CTRW Approximations for Fractional Equations with Variable Order. Springer International Publishing, Cham, pp. 3–25. [http://dx.doi.org/10.1007/978-3-031-34089-5\\_1](http://dx.doi.org/10.1007/978-3-031-34089-5_1).

Laio, F., Porporato, A., Ridolfi, L., Rodriguez-Iturbe, I., 2001. Plants in water-controlled ecosystems: active role in hydrologic processes and response to water stress: II. Probabilistic soil moisture dynamics. *Adv. Water Resour.* 24 (7), 707–723. [http://dx.doi.org/10.1016/S0309-1708\(01\)00005-7](http://dx.doi.org/10.1016/S0309-1708(01)00005-7), URL: <https://www.sciencedirect.com/science/article/pii/S0309170801000057>.

Levy, M., Berkowitz, B., 2003. Measurement and analysis of non-Fickian dispersion in heterogeneous porous media. *J. Contam. Hydrol.* 64 (3–4), 203–226. [http://dx.doi.org/10.1016/S0169-7722\(02\)00204-8](http://dx.doi.org/10.1016/S0169-7722(02)00204-8).

Li, P., Berkowitz, B., 2018. Controls on interactions between resident and infiltrating waters in porous media. *Adv. Water Resour.* 121, 304–315. <http://dx.doi.org/10.1016/j.advwatres.2018.09.002>, URL: <https://www.sciencedirect.com/science/article/pii/S0309170818301660>.

Mainardi, F., 2010. Fractional Calculus and Waves in Linear Viscoelasticity. Imperial College Press.

Manzini, G., Ferraris, S., 2004. Mass-conservative finite volume methods on 2-D unstructured grids for the Richards' equation. *Adv. Water Resour.* 27 (12), 1199–1215. <http://dx.doi.org/10.1016/j.advwatres.2004.08.008>, URL: <https://www.sciencedirect.com/science/article/pii/S0309170804001204>.

Marsh, T., Booker, D., Fry, M., 2009. The 2004–06 Drought. Centre for Ecology and Hydrology Report NERC Open Research Archive No. 10830, National Hydrological Monitoring Programme, URL: <https://nora.nerc.ac.uk/id/eprint/10830/>.

Meerschaert, M.M., Sikorskii, A., 2012. Stochastic Models for Fractional Calculus. De Gruyter, Berlin, Boston, <http://dx.doi.org/10.1515/9783110258165>.

Meerschaert, M.M., Toaldo, B., 2019. Relaxation patterns and semi-Markov dynamics. *Stochastic Process. Appl.* 129 (8), 2850–2879. <http://dx.doi.org/10.1016/j.spa.2018.08.004>, URL: <https://www.sciencedirect.com/science/article/pii/S0304414918304095>.

Méndez, V., Fedotov, S., Horsthemke, W., 2010. Reaction-Transport Systems: Mesoscopic Foundations, Fronts, and Spatial Instabilities. Springer Science & Business Media.

Metzler, R., Klafter, J., 2000. The random walk's guide to anomalous diffusion: a fractional dynamics approach. *Phys. Rep.* 339 (1), 1–77. [http://dx.doi.org/10.1016/S0370-1573\(00\)00070-3](http://dx.doi.org/10.1016/S0370-1573(00)00070-3), URL: <https://www.sciencedirect.com/science/article/pii/S0370157300000703>.

Montanari, A., Nguyen, H.T.T., Rubinetti, S., Ceola, S., Galelli, S., Rubino, A., Zanchettin, D., 2023. Why the 2022 Po River drought is the worst in the past two centuries. *Sci. Adv.* 9 (32), eadg8304. <http://dx.doi.org/10.1126/sciadv.adg8304>, URL: <https://www.science.org/doi/10.1126/sciadv.adg8304>.

Piemonte, A., 2022. Rapporto