![](_page_0_Picture_1.jpeg)

### Special Section: UZIG Research: Land-Use and Climate Change Impacts on Vadose Zone Processes

#### **Core Ideas**

- We evaluated approaches based on machine learning and soil water dynamic principles.
- We compared automated analysis of soil moisture sensor time series for estimating field capacity.
- Approaches accurately estimated field capacity compared with expert values.
- Automated approaches needed to leverage temporally dynamic field capacity.

Dep. of Agricultural and Biological Engineering, Univ. of Florida, Gainesville, FL 32611. \*Corresponding author (ezbean@ufl.edu).

Received 11 Apr. 2018. Accepted 28 July 2018. Supplemental material online.

Citation: Bean, E.Z., R.G. Huffaker, and K.W. Migliaccio. 2018. Estimating field capacity from volumetric soil water content time series using automated processing algorithms. Vadose Zone J. 17:180073. doi:10.2136/vzj2018.04.0073

© Soil Science Society of America.
This is an open access article distributed under the CC BY-NC-ND license (http://creativecommons.org/licenses/by-nc-nd/4.0/).

## Estimating Field Capacity from Volumetric Soil Water Content Time Series Using Automated Processing Algorithms

Eban Z. Bean,\* Ray G. Huffaker, and Kati W. Migliaccio

Vadose zone measurements of volumetric soil water content (θ) using soil moisture sensors (SMSs) have become more common due to advances in technology and reduction of costs. Soil moisture sensor data exhibit a characteristic cyclical pattern reflecting water flux dynamics into and out of the observed soil volume. Expert review of SMS datasets to distinguish valid from corrupt or incomplete soil water cycles is arguably the most precise method for determining field capacity  $(\theta_{EC})$  but is impractically cumbersome and time consuming for increasingly large SMS datasets. We evaluated competing approaches for automated soil water cycles analysis that use widely available R packages based on pattern recognition and machine learning (findpeaks [R-FP], symbolic aggregate approximation [R-SAX], and density histogram [R-DH]), and a MATLAB code based on soil water dynamic principles (SWDP). These approaches were applied to three SMS datasets. Our empirical results showed superiority of R-SAX for identifying valid soil water cycles, probably due to benefiting from training sets to calibrate to correct cycles. Two other approaches (SWDP and R-FP) provided similar results without need of training sets or preprocessing data. Three approaches for estimating field capacity were applied to valid cycles, R-FP, regression of exponential decay (SWDP-R), and estimated "knee" of curve (SWDP-K). Each performed similarly to the expert defined values, with R-FP and SWDP-R generally performing best across analyses. Results of this study also show temporal dynamics of  $\theta_{\text{FC}}$  within datasets used here. There is potential for optimizing  $\theta_{\mbox{\scriptsize FC}}$  and a need for automated, objective analysis to leverage dynamics in irrigation management and modeling.

Abbreviations: CCS, citrus grower orchard with conventional irrigation scheduling; ET, evapotranspiration; MAD, maximum allowable depletion; R-DH, density histogram in R; R-FP, R package *findpeaks*; R-SAX, symbolic aggregate approximation in R; SAX, symbolic aggregate approximation; SMS, soil moisture sensor; SWDP, soil water dynamic principles; SWDP-K, "knee" of curve for estimating field capacity; SWDP-R, regression of exponential decay for estimating field capacity; TCS, turfgrass with conventional irrigation scheduling; TET, turfgrass with evapotranspiration controller.

Soil moisture sensors (SMSs) provide high-frequency in situ vadose zone measurements of volumetric soil water content ( $\theta$ ) (Topp, 2003; Blonquist et al., 2005; Evett and Parkin, 2005). Soil moisture sensor data provide greater insight into complex interactions among environmental, climatic, soil, topological, and vegetation factors essential to a wide variety of endeavors (Cardell-Oliver et al., 2005; Schaefer et al., 2007; Bogena et al., 2010; Dobbs et al., 2014). For example,  $\theta$  measurements have been used to identify field saturation, field capacity, initiation of plant water stress, and plant extraction limits that are pivotal to determining irrigation triggers and the onset of deficit water conditions (Chandler et al., 2017), and to ascertain soil texture using the range in soil water contents observed in the field-collected data (Ladson et al., 2006; Yang et al., 2016). Soil moisture sensor data have been used to develop process models for various purposes. Examples include predicting  $\theta$ at different depths in the soil profile (Aljoumani et al., 2012); calibrating van Genuchten parameters (i.e., residual water content,  $\alpha$ , and n) in the agroenvironmental model WAVE (Water and Agrochemicals in the Soil, Crop, and Vadose Environment) using two inverse modeling methods (Ritter et al., 2003); and evaluating model performance by assessing quality of fit between sensor measurements and model output (Pan et al., 2011).

Soil moisture sensor data exhibit a characteristic cyclical pattern reflecting water flux dynamics into and out of the observed soil volume (Pan et al., 2011; Figueroa and Pope, 2017). Infiltration resulting from a wetting event causes q to increase in response to soil water potential gradients within vadose zone soil (Daly and Porporato, 2005). Maximum q is generally reached as losses due to drainage and evapotranspiration (ET) surpass additions from infiltration. For well-drained soils, these losses continue until a subsequent wetting event occurs, initiating another wetting and drying cycle (Figueroa and Pope, 2017). Rates of these processes vary based on soil properties and drainage conditions.

Inclusion of invalid q cycles for identification of soil vadose zone characteristics, such as field capacity (q FC), may bias understanding of real-world soil water processes increasing the likelihood of unreliable field recommendations and unintended consequences. Prematurely terminated q cycles can result in insufficient data for cycle analyses, as the drying or ET losses after wetting may not deplete to or below an anticipated level, such as q FC. For example, the drying processes after a precipitation or irrigation event for a q cycle may be truncated due to a subsequent event in close succession. A q cycle with insufficient would be considered invalid for analysis. Additionally, invalid q cycles may occur due to sensor malfunction or unexpected irrigation patterns caused by irrigation system failure or irrigation management mishaps (Rosenbaum et al., 2011; Figueroa and Pope, 2017). Identifying q cycles that do not meet a full wetting and drying flux according to expected system characteristics is needed for screening and exclusion from further analyses that require complete q cycles.

For example, efficient irrigation management optimizes q cycling by maintaining q between q FC and a minimum acceptable soil water content to minimize drainage losses and provide adequate water to plants (USDA–NRCS, 2005). The q FC can be determined by visual review of soil drying in SMS records after large irrigation or precipitation events and managed as a temporally constant value for a soil (USDA–NRCS, 2005). Thus, accurate determination of q FC from valid q cycles is critical to irrigation efficiency and water conservation.

Expert manual labeling—visually inspecting SMS datasets to distinguish valid from corrupted (invalid) q cycles—is arguably the most precise method but is impractically cumbersome and time consuming for increasingly large SMS datasets. Labeling is the process of identifying critical q values among the time series relative to individual wetting and drying cycles, and then classifying cycles as valid or invalid. Figueroa and Pope (2017) recently evaluated the use of machine learning methods to automatically label q cycles and to estimate the wetting (water entering the system due to irrigation or precipitation), fall (or drainage), and consumption (or ET) portions of valid q cycles. They assessed the performance of four machine-learning approaches against five SMS datasets.

Three of the approaches used symbolic aggregate approximation (SAX) and differed by information provided to improve labeling performance—in particular, initial rules used to prescreen q cycles before SAX and subsequent rules used to post-screen q

cycles after SAX. In brief, SAX converted numerical time series observations into a word document composed of sequences of letters ("words"). Powerful information retrieval methods were then applied to assess correspondence with document "wordbags" created from other time series. A q cycle was validated if its document corresponds best with documents from a library of prevalidated q cycles. Figueroa and Pope (2017) included a detailed explanation of SAX.

The fourth machine-learning approach applied by Figueroa and Pope (2017) computed the density histogram (whose underlying area is unity) for a candidate q cycle, measured its overlapping area with the density histogram computed for each member of a set of valid q cycles, and averaged the overlapping areas. The candidate q cycle was labeled as valid if the average overlapping area exceeded a selected critical value.

Figueroa and Pope (2017) found that the SAX-based approaches performed best in labeling q cycles in all five SMS datasets with the highest precision and the fewest false positives. Alternatively, the density histogram approach performed adequately in only one dataset and poorly in the others by these metrics.

In this study, we tested whether the empirical results of Figueroa and Pope (2017) favoring SAX as an automated q cycle labeling method held true against competing approaches of our own design and applied to three new SMS datasets. Whereas the approaches compared in Figueroa and Pope (2017) emphasize computing efficiency (processing time) and numerical precision, several of our competing approaches emphasized computing convenience and accessibility of code to practitioners with limited knowledge of computer science. Three of the approaches that we compare used freely available R packages (including SAX and density histogram approaches). We further compared the performance of R-based approaches against that of numerical based approach developed within MATLAB code using soil water dynamic principles (SWDP).

We also used automatically validated q cycles to estimate q FC based on existing R packages, regression, and soil water dynamics. The q FC represents the amount of water the soil can hold after gravity losses have occurred and before ET losses have started. The q FC is a key parameter in hydrologic models used in irrigation scheduling and is arguably a fundamental characteristic of the vadose zone water balance. Previous researchers have shown the ability to extract additional soil water relationships from high-frequency SMS data (Ladson et al., 2006; Yang et al., 2016; Chandler et al., 2017) but have not fully investigated the ability to use such series and automated procedures to estimate site-specific q FC.

## 6Materials and Methods

We followed conventional procedures for testing the performance of automated labeling approaches. Three SMS datasets were initially reviewed by Dr. Migliaccio, deemed an expert due their extensive experience working with soil water research data. Dr. Migliaccio used a conventional approach to identify and label q cycles as "valid" if (i) the increase in q corresponded to a rainfall

or irrigation event and there were no additional inputs of rainfall or irrigation between 10:00 PM and the scheduled irrigation time (6:00 or 7:00 AM) the following day, and (ii) the drying was characterized by a steady decline during this period. Following convention for analyzing soil moisture time series for these soils, field capacity was considered achieved after one night of drainage. Thus, the field capacity value was determined to be the value preceding the scheduled irrigation time.

Next, the success of each automated approach in matching expert manual labeling was assessed with a confusion matrix summarizing the approach's accuracy and precision. Three of the automated approaches estimated  $\theta_{FC}$ , which were compared with expert estimates with a variety of methods described below.

#### Soil Moisture Sensor Datasets

The three datasets (Table 1) were previously collected in Florida research trials where irrigation was managed. Although the data were collected for other research objectives, they provide a range of circumstances to evaluate our automated techniques. The three datasets represent different field management conditions. The citrus grower orchard with conventional irrigation scheduling (CCS) data were collected in a commercial citrus orchard where the grower managed irrigation (Fig. 1). The turfgrass with conventional irrigation scheduling (TCS) data and the turfgrass with ET controller (TET) data were from a controlled experimental plot where irrigation was specifically managed (Fig. 1). The TCS treatment received more irrigation water than TET. Thus, conditions were maintained at a higher θ in the TCS dataset.

# Expert Manual Labeling of Volumetric Soil Water Content Cycles

Volumetric soil water content cycles are composed of two phases, a wetting phase where water enters the soil profile and  $\theta$  increases, and a drying phase where water leaves the soil profile and  $\theta$  decreases. Expert manual labeling used raw data values and plots to identify the initiation of a wetting event  $(\theta_A)$ , the peak water content from the wetting event  $(\theta_B)$ , and the end of the soil drying

period  $(\theta_C)$  initiating the next wetting event (Fig. 2). Valid  $\theta$  cycles were identified as  $\theta$  data series with a wetting event characterized by a sharp rise in  $\theta$  and a following  $\theta$  decrease due to drainage losses. Using visual examination of tabular data and plotted data,  $\theta$  cycles were considered valid if the change in drainage slope to near zero during a nighttime (i.e., limited to no ET losses) was achieved. The primary reason this was not achieved was additional rainfall or irrigation entering the soil profile before drainage losses were complete. For each SMS dataset, expert manual labeling results were outputted to a matrix including (i) timestamps for candidate  $\theta$  cycles; (ii) corresponding  $\theta_A$ ,  $\theta_B$ ,  $\theta_C$ , and  $\theta_{FC}$  points; and (iii) labels. Finally, the expert identified  $\theta_{FC}$  for valid  $\theta$  cycles. Given the high infiltration rate of the soils in the SMS datasets,  $\theta_{FC}$  was considered to be the  $\theta$  level after one overnight drainage cycle with no additional water input (e.g., rainfall).

# Automated Labeling of Volumetric Soil Water Content Cycles

Soil Water Dynamic Principles

We formulated a SWDP model in MATLAB combining numerical methods and principles from soil science to compute estimate  $\theta$  cycle parameters and assign labels (i.e.,  $\theta_A, \theta_B,$  and  $\theta_C$ ). Peaks of  $\theta$  cycles, or local maxima ( $\theta_B$ ), were identified as values exceeding both prior and later values by a determined threshold,  $\alpha$ , which was set at 0.006 for this study:  $\theta_i > \theta_{i+1} + \alpha$  and  $\theta_i > \theta_{i-1} + \alpha$ .

The beginning of a cycle  $(\theta_A)$  was identified by identifying local minima that preceded each peak  $(\theta_B)$ . This point  $(\theta_{Ai})$  was also identified as the end of the preceding cycle  $(\theta_{Ci-1})$ . Figure 2 shows an example of two  $\theta$  cycles with time indices A,B, and C corresponding  $\theta_A,\theta_B,$  and  $\theta_C,$  respectively. To screen out invalid cycles from further analysis, candidate  $\theta$  cycles identified by SWDP were required to satisfy both the peak-wetting and drying-duration criteria. The first criterion was implemented to ensure that valid cycles had sufficient wetting to exceed a minimum threshold to eliminate noise in  $\theta$  time series, whereas the second criterion was established to ensure that sufficient drying occurred after the wetting event that approaches could be applied for  $\theta_{FC}$  analysis.

| T.1.1. 1 D           | - C - L L J J               |                                       |
|----------------------|-----------------------------|---------------------------------------|
| Lable L. Describtion | of the three datasets lised | to evaluate the automated approaches. |

| Dataset name† | Date range                   | Time step | Soil type                                                                                                     | Location       | Sensor depth | Crop                                                          | Sensor used                        |
|---------------|------------------------------|-----------|---------------------------------------------------------------------------------------------------------------|----------------|--------------|---------------------------------------------------------------|------------------------------------|
|               |                              | h         |                                                                                                               |                | cm           |                                                               |                                    |
| CCS           | 1 July–2 Dec.<br>2016        | 1         | Deep, well drained, very rapidly permeable sandy soils                                                        | Fort Meade, FL | 15.2         | Citrus                                                        | Campbell<br>Scientific<br>SC161    |
| TCS           | 20 Nov. 2013–16<br>Nov. 2014 | 1         | Krome, very gravelly loam,<br>classified as a<br>loamy-skeletal, carbonatic,<br>hyperthermic Lithic Udorthent | Homestead, FL  | 7.6          | St. Augustine grass [Stenotaphrum secundatum (Walter) Kuntze] | Decagon Ech <sub>2</sub> o<br>EC-5 |
| TET           | 20 Nov. 2013–16<br>Nov. 2014 | 1         | Krome, very gravelly loam,<br>classified as a<br>loamy-skeletal, carbonatic,<br>hyperthermic Lithic Udorthent | Homestead, FL  | 7.6          | St. Augustine grass                                           | Decagon Ech <sub>2</sub> o<br>EC-5 |

 $\dagger$  CCS, citrus grower orchard with conventional irrigation scheduling; TCS, turfgrass with conventional irrigation scheduling; TET, turfgrass with evapotranspiration controller.

![](_page_3_Figure_1.jpeg)

Fig. 1. Time series of volumetric soil water content (q) used to evaluate the automated approaches.

### R Routine indpeaks

We used R routine findpeaks(pracma) (Borchers, 2018) to identify q cycle parameters q<sup>A</sup> , q<sup>B</sup> , and q<sup>C</sup> and their corresponding time indices. This routine (which we denote as R-FP) identifies the time and value of a local maximum within a time series, along with the beginning point of the rise to the maximum and the end point of the descent from the peak, which typically is the first plateau in the declining data. The beginning and end points designated potential q cycles. To be labeled valid, candidate q cycles identified by R-FP needed to satisfy the peak-wetting and dryingduration restrictions used in expert manual labeling. An annotated wraparound R code applying the R-FP routine to the three SMS datasets is available in the supplemental material.

### Machine-Learning Approaches

We used R to execute two machine-learning methods to label q cycles: SAX (R-SAX) and density histograms (R-DH). We ran R-SAX with routines in R package jmotif (Senin, 2018), and R-DH with R routine overlap(overlapping), which computes overlapping areas of two density plots (Pastore 2017). Annotated wraparound R code applying R-DH and R-SAX routines to the three SMS datasets is available in the supplemental material.

Unlike the preceding SWDP and R-FP automated approaches, which labeled q cycles valid or invalid according to peak-wetting

and drying-duration restrictions, R-SAX and R-DH were calibrated to identify valid q cycles using expert manual labels as training sets. We used a rotating cross-validation scheme that partitions q cycles into a "test" group to be labeled with machine learning against a "training" group that is further partitioned into valid or invalid groups according to expert labeling. The scheme rotates until each group takes a turn as the unlabeled test group, and each q cycle has been labeled. This is illustrated in Fig. 3 using an example with nine candidate q cycles.

In R-DH, we computed the density histogram (whose underlying area is unity) for a selected test q cycle, measured its overlapping area with that computed for each training q cycle in the valid group, and averaged the overlapping areas across training sequences. Figure 4 illustrates an overlapping area shared by two density histograms (dashed lines). A q cycle is labeled as valid if the average overlapping area exceeds a selected critical value ("crit. dh"). Since there are no firm rules for selecting a critical value, we ran R-DH over several values to evaluate how the accuracy and precision of labeling change.

We illustrated R-SAX with a simple hypothetical example. We first converted a time series into a character string ("word") of selected length w. Initially, the time series was divided into w equal-length segments, and the mean value of the observations in each segment was taken. In Fig. 5, we divided a representative q cycle (dotted curve) into

![](_page_4_Figure_1.jpeg)

Fig. 2. Example data showing two complete wetting (irrigation events) followed by 3-d drying cycles with points indicating the initiation of a wetting event  $(\theta_A)$ , the peak water content from the wetting event  $(\theta_B)$ , and the end of the soil drying period  $(\theta_C)$  initiating the next wetting event. Sensor data from turfgrass with conventional irrigation scheduling at the 7.6-cm depth on gravelly loam soil.

w=6 equal segments whose mean values are plotted as the horizontal black bars. Next, each bar was assigned a letter from an  $\alpha$ -length alphabet, which in our illustration contained  $\alpha=3$  letters: a, b, and c. Letters were assigned to bars with equiprobability. If the time series is standardized—by subtracting the mean value from each observations and dividing by the SD—then we can use breakpoints from a standard normal distribution, N(0,1). We illustrated this with the distribution along the vertical axis. Given that  $\alpha=3$ , the standard normal breakpoints divided the vertical axis into three equiprobable intervals given by (0.43, -0.43). We assigned bars in the upper tail "a," the middle interval "b," and the lower tail "c." As a result, the  $\theta$  cycle sequence was converted into the word "aabbcc." Multiple words (a "wordbag") can be created by doing the above conversion for sliding intervals of observations ("window") through a single time series.

We next formulated a "word frequency" matrix composed of "word count" values to compare multiple time series by quantifying the number of occurrences of various "words" (e.g., "aabbcc," "cbbaa," and "bacab") within each time series. Each word count in the matrix was converted into a "term frequency-inverse document frequency" ("tf.idf") index, with the following formula:

$$tf.idf = \log(1 + tf) \times \log(N/N_{word})$$
 [1]

where tf is the term frequency or word count, N is the number of documents, and  $N_{\rm word}$  is the number of documents containing the word.

The matrix of these values are three-dimensional vectors of indices for each document. The cosine similarity of two normalized index vectors can be compared by calculating the inner product of the two vectors. Larger cosine values indicate greater similarity. This was applied to the documents to evaluate how well each corresponded to the valid (i.e., training) sequences. A more detailed explanation of this method is included in Supplement 1.

#### **Confusion Matrices**

We computed confusion matrices to evaluate the performance of the automated approaches in matching expert manual labeling for each dataset, similar to Figueroa and Pope (2017). A  $\theta$  cycle that was labeled as valid or invalid by an automated approach in agreement with expert manual labeling was classified as a true positive (TP) or true negative (TN), respectively. A  $\theta$  cycle that was incorrectly validated or invalidated in automated labeling was

![](_page_4_Figure_10.jpeg)

Fig. 3. Example of rotating cross validation applied to nine volumetric soil water content cycles. C1 and C2 represent valid and invalid cycles, respectively.

![](_page_5_Figure_1.jpeg)

Fig. 4. Overlapped area shared by two density histograms.

classified as a false positive (FP) or false negative (FN), respectively. This information was used to calculate the accuracy and precision of automated labeling:

$$Accuracy = (TP + TN)/(P+N)$$
 [2]

$$Precision = TP/(TP + FP)$$
 [3]

where P and N are the total number of valid and invalid  $\theta$  cycles identified with expert manual labeling, respectively. Perfect performance (P = TP, N = TN, and FP = 0) would result in an accuracy and precision values of 1.0, whereas completely incorrect performance (TP = 0, TN = 0) would result in accuracy and precision values of 0.0. The accuracy statistic accounts for the correctness of both the positive and negative values together, whereas the precision statistic only accounts for the correctness of the positive values.

### **Estimating Field Capacity**

We estimated  $\theta_{FC}$  for true positive  $\theta$  cycles detected by the SWDP and R-FP automated labeling approaches. During the wetting event of a  $\theta$  cycle resulting from infiltration, macropores fill initially, and depending on the duration of the infiltration, unfilled or partially filled soil voids fill as well, with maximum water content saturating all pores if sufficient duration and water are available. At saturation, the weight of water exceeds the matric suction. Without ET, drainage will continue to deplete the  $\theta$  until matric forces equal gravity, although plants contribute to the matric potential during the day. This  $\theta$  is field capacity, or  $\theta_{FC}$ . Evapotranspiration will further deplete  $\theta$  as long as sufficient energy is available and plant roots can access the water and overcome the matric forces. As ET generally occurs only during daylight hours, any decrease in  $\theta$  overnight is predominantly due to drainage processes. Once  $\theta$  is below  $\theta_{FC}$ , drainage processes are expected to cease.

We estimated  $\theta_{FC}$  in SWDP following two approaches. The "knee" approach (SWDP-K) estimates  $\theta_{FC}$  based on how  $\theta$  changes

![](_page_5_Figure_10.jpeg)

Fig. 5. Conversion of wetting and drying cycle sequence (dotted line) to symbolic representation. Each step of the black line is the average volumetric soil water content ( $\theta$ ) value over the respective cycle time increments. The dashed lines (-0.43, 0.43) are "breakpoints" that divide a standard normal distribution into three equiprobable intervals for labeling the average  $\theta$  values. Values labeled above, between, and below the breakpoints are assigned the letters a, b, and c, respectively. As a result, the  $\theta$  cycle is converted into the word "aabbcc."

with time. In some soils, the  $\theta_{FC}$  can be reached before ET begins on the following day. Thus, one approach is to estimate  $\theta_{FC}$  as the  $\theta$  when the rate  $(d\theta/dt)$  decreases sharply. After a cycle peak, the  $\theta$  rate should continuously decrease through any remaining part of the day and overnight until ET rates increase during the morning. This point can be thought of as the first "knee" of the drying curve. In Fig. 6, seven separate cycles are identified (1–7). Field capacity estimates using the knee approach are shown for four cycles that met the validation criteria: Cycles 1, 4, 6, and 7. Cycles 2, 3, and 5 were determined to be invalid due to insufficient drying duration.

A second regression approach (SWDP-R) estimates  $\theta_{FC}$  using the principle that without ET losses and infinite time,  $\theta$  will exponentially decay toward a constant, which we assume here to be  $\theta_{FC}$ . Should soil wetting not exceed the  $\theta_{FC}$  or ET diminish the  $\theta$  below  $\theta_{FC}$ , then  $\theta$  would remain constant, with no redistribution in the soil profile. Therefore, the overnight time series should follow a decay curve until the following morning when ET begins depleting  $\theta$ . This assumes that peak  $\theta$  exceeds the field capacity and soil water distribution is negligible overnight.

Given these processes, we isolated the overnight time series subset of a cycle after a peak. For our study, we used data between 11:00 PM and 6:00 AM. The rate of water content decrease in soil was assumed to be proportional to the water content exceeding field capacity (Hillel, 1998).

$$\theta_i = (\theta_B - \theta_{FC})e^{-\lambda t_i} + \theta_{FC}$$
 [4]

where  $\lambda$  is the decay constant, and  $t_i$  is the time since  $\theta_{\rm B}$ . With this model, as time tends toward infinity,  $\theta_i$  approaches  $\theta_{\rm FC}$ . To estimate  $\theta_{\rm FC}$ , the inverse times  $(t_i^{-1})$  and corresponding water content values were then regressed, with the intercept estimating the water content at an infinite time since the peak  $\theta$ . See the example regression of transformed data in Fig. 7.

We also investigated whether R routine *findpeaks(pracma)* (Borchers 2018), used in the R-FP automated approach, might

![](_page_6_Figure_1.jpeg)

Fig. 6. A series of wetting and drying cycles with field capacity (FC) estimated as the first knee of the curve for cycles with sufficient data using the soil water dynamic principles (SWDP) automated technique. Although the first knee is between 0.33 and 0.36, the overnight drainage only ceases below 0.30, as seen in Cycle 4.

provide a highly expedient method for identifying q FC. The routine identifies when the descent from a peak is completed, which we observed tends to be the first plateau in the drying phase of a q cycle. We compare the performance of this "quick and dirty" plateau estimate of q FC in matching expert estimates with that of the more computationally intensive SWDP approach.

We compared q FC estimated by the R-FP, SWDP-K, and SWDP-R approaches with expert values by (i) comparing the distributions of estimates with box-and-whisker plots, (ii) observing the scatter of the different estimates in time plots, (iii) computing the goodness of fit when automated estimates were linearly regressed against expert values for identical q cycles, and (iv) comparing the cumulative distributions of automated estimates with expert values. More information on the code used in the SWDP-K and SWDP-R approaches is provided in the supplemental material.

### 6Results

### **Cycle Identiication**

We evaluated the performance of the four automated approaches in matching expert manual labeling of q cycles as valid or invalid in the three SMS datasets with confusion tables (Tables 2–4). Consistent with Figueroa and Pope (2017), R-SAX performed best in terms of accuracy (0.681–0.899), precision (0.8–0.857), and false positives (4–6, rate = 0.143–0.2), where the numbers in parentheses are the minimum and maximum values across the three datasets. The SWDP approach performed second best in terms of accuracy (0.571–0.808), precision (0.61–0.818), and false positives (16–23, rate = 0.182–0.390). Both R-FP and R-DH lagged behind as the third and fourth best performers, respectively.

### **Field Capacity**

We estimated q FC for valid q cycles detected by SWDP and R-FP. For the SWDP cycles, q FC was estimated by the regression (SWDP-R) and knee approaches (SWDP-K), and the R routine findpeaks(pracma) (Borchers, 2018) was applied to R-FP cycles. In general, each of the automated methods reflected similar fluctuations over time as the true values and were typically within 0.03 of the true value.

### Box and Whisker Plots

The distributions of q FC are compared via box-and-whisker plots in Fig. 8 for TCS, TET, and CCS datasets. For the CCS dataset, the R-FP distribution most closely matches the distribution of true data. However, SWDP-R had the most consistent estimates, whereas SWDP-K had the greatest range and least consistency. For the TCS dataset, the box-and-whisker plots are similar in range with overlap among each series. However, each approach, including the true values, included an abundance of outliers. The box plots suggest that the R-FP and SWDP-K approaches slightly overestimated q FC, whereas the SWDP-R slightly underestimated q FC. Each of the interquartile boxes were between the values of 0.390 and 0.451, with the upper limit of the lower outliers ~0.05 below the lower inclusive limit of each box plot. Synchronous outliers may indicate changes in rainfall or irrigation patters for each plot. Similarly, the TET data also had very narrow distributions, with notable clusters of low-value outliers for each approach. The medians for TET q FC were all between 0.256 and 0.262. The R-FP and SWDP-K approaches were very similar in distribution relative to the true values.

### Field Capacity over Time

The q FC estimates for the CCS dataset are shown in Fig. 9A. Of the three datasets, this was the shortest in duration and resulted

![](_page_7_Figure_1.jpeg)

Fig. 7. Example regression of overnight volumetric water content against inverse time since peaks for estimating field capacity (Est.  $\theta_{FC}$ ) using the regression of exponential decay (SWDP-R) automated technique.

in the least variation in  $\theta_{FC}$  over time. The true  $\theta_{FC}$  ranged from 0.073 to 0.096, with most of values being between 0.08 and 0.09. The relationship over time of automated  $\theta_{FC}$  estimates to the true values was consistent for each approach. The SWDP-R approach consistently underestimated  $\theta_{FC}$ , whereas the SWDP-K and R-FP approaches consistently overestimated  $\theta_{FC}$ . In general, the SWDP-K approach estimated higher  $\theta_{FC}$  than R-FP and typically had the highest  $\theta_{FC}$  estimates along with the overall maximum.

The TCS dataset had the largest range in true  $\theta_{FC}$  values, from a minimum of 0.139 to a maximum of 0.475 (Fig. 9B). Overall, the automated  $\theta_{FC}$  estimates were similar to the true values, with SWDP-R estimates typically underestimating  $\theta_{FC}$  and the R-FP and SWDP-K approaches overestimating  $\theta_{FC}$ . The initially low  $\theta_{FC}$  values through November and December 2013 correspond to the clustered outliers for each approach shown in Fig. 8B. However, the automated approaches noticeably missed relatively low true values twice in April and once in September, with all automated estimates overestimating  $\theta_{FC}$ . Additionally,  $\theta_{FC}$  values were noticeably less variable over time before May than after.

Table 2. Results of analysis comparing cycle identification for the citrus grower orchard with conventional irrigation scheduling dataset (CCS).

| Method†     | Accuracy | Precision | True positives | False positives | False<br>negatives | True negatives |
|-------------|----------|-----------|----------------|-----------------|--------------------|----------------|
|             |          |           |                | n               | 0. ———             |                |
| SWDP        | 0.571    | 0.610     | 25             | 16              | 14                 | 15             |
| R-FP        | 0.671    | 0.786     | 22             | 6               | 17                 | 25             |
| R-SAX       | 0.681    | 0.833     | 20             | 4               | 18                 | 27             |
| R-DH (0.06) | 0.638    | 0.603     | 38             | 25              | 0                  | 6              |

<sup>†</sup> SWDP, soil water dynamic principles; R-FP, R package *findpeaks*; R-SAX, symbolic aggregate approximation in R; R-DH, density histogram in R with the critical histogram overlap value included in parentheses.

Similar to the previous two datasets, the R-FP and SWDP-K approaches generally overestimated the true  $\theta_{FC}$  for the TET dataset (Fig. 9C). The five highest  $\theta_{FC}$  estimates were from the SWDP-K approach. However, the SWDP-R estimates agreed with the True values during several periods of the dataset. The relatively low  $\theta_{FC}$  values through November and December 2013 also correspond to the clustered outliers for each dataset shown in Fig. 9C. Unlike the previous two datasets, the SWDP-R  $\theta_{FC}$  values did not consistently underestimate true values. Similar to the TCS results in Fig. 9B, the TET dataset reflects a pattern of more consistent  $\theta_{FC}$  values leading up to May and a more dynamic  $\theta_{FC}$  afterward. As the difference between these sites was primarily how irrigation was applied, it is probable that this is due to changes in rainfall patterns from before to after May and, potentially, increased ET.

#### Regression of True and Estimated Cycles

Next, the  $\theta_{FC}$  estimates were regressed against corresponding true values from the same cycles. The regression plots for CCS, TCS, and TET are shown in Fig. 10A, 10B, and 10C, respectively. In Fig. 10A, the general trend of R-FP and

Table 3. Results of analysis comparing cycle identification for the turf-grass with conventional irrigation scheduling dataset (TCS).

| Method†     | Accuracy | Precision | True positives | False<br>positives | False negatives | True negatives |
|-------------|----------|-----------|----------------|--------------------|-----------------|----------------|
|             |          |           | no.            |                    |                 |                |
| SWDP        | 0.757    | 0.791     | 87             | 23                 | 27              | 69             |
| R-FP        | 0.549    | 0.678     | 40             | 19                 | 74              | 73             |
| R-SAX       | 0.768    | 0.800     | 20             | 5                  | 11              | 33             |
| R-DH (0.05) | 0.676    | 0.655     | 19             | 10                 | 12              | 27             |

<sup>†</sup> SWDP, soil water dynamic principles; R-FP, R package *findpeaks*; R-SAX, symbolic aggregate approximation in R; R-DH, density histogram in R with the critical histogram overlap value included in parentheses.

Table 4. Results of analysis comparing cycle identification for the turfgrass with evapotranspiration controller dataset (TET).

| Method†           | Accuracy | Precision | True<br>positives       | False<br>positives | False<br>negatives | True<br>negatives |
|-------------------|----------|-----------|-------------------------|--------------------|--------------------|-------------------|
|                   |          |           | ————————— no. ————————— |                    |                    |                   |
| SWDP              | 0.808    | 0.818     | 90                      | 20                 | 24                 | 95                |
| R-FP              | 0.533    | 0.559     | 33                      | 26                 | 81                 | 89                |
| R-SAX             | 0.899    | 0.857     | 36                      | 6                  | 1                  | 26                |
| R-DH (0.01) 0.406 |          | 0.464     | 26                      | 30                 | 11                 | 2                 |

<sup>†</sup> SWDP, soil water dynamic principles; R-FP, R package findpeaks; R-SAX, symbolic aggregate approximation in R; R-DH, density histogram in R with the critical histogram overlap value included in parentheses.

SWDP-K approaches overestimating true q FC can be seen, as the data points are generally above the 1:1 dashed line, whereas the underestimates of the SWDP-R approach are all below the 1:1 line. The R-FP results had the lowest R 2 value of 0.24. The SWDP-R results had a higher R 2 (0.48) with the smallest slope, whereas the SWDP-K approach had the highest R 2 value (0.90). The CCS dataset had the least consistency among the dataset. The regression of results for the TCS data were all very similar (Fig. 10B), with R 2 values all exceeding 0.97, slopes between 0.98 and 1.02, and intercepts between −0.009 and 0.012. All three approaches aligned best with the true values for the TCS data compared with the other two datasets. The regression shows that the R-FP and SWDP-K approaches were slightly greater than the SWDP-R values. Although results of the TET analyses were similar to those for TCS, the estimates did not match the true values as closely as the TCS dataset (Fig. 10C). The R 2 values ranged from 0.89 to 0.97, whereas the slopes ranged from 0.95 to 0.96 and intercepts ranged from 0.007 to 0.020. The overestimation by the R-FP and SWDP-K approaches are noted, as well as underestimates by the SWDP-R approach.

### Regression of Distributions

The cumulative distribution of the q FC values for each estimation method was plotted against the cumulative distribution of the true values for CCS, TCS, and TET in Fig. 11A, 11B, and 11C, respectively. In contrast with the previous analysis, this analysis does not consider whether the estimates correspond to the same or similar cycles as the true values. This analysis only compares the relative probability of estimating a value for the true value.

For the CCS dataset (Fig. 11A) the regression slopes ranged from 0.55 to 1.7, with intercepts ranging from −0.053 to 0.032. The R-FP approach had the closest distribution to the distribution of the true values, with data closest to the 1:1 line and the highest R 2 value of 0.95. The SWDP-R values had the smallest slope, indicating that the values were more consistent, with a slope of 0.55, indicating that the range was approximately half of the true value distribution.

For the TCS dataset (Fig. 11B), the distributions were all very similar, with slopes ranging from 0.84 to 0.97, intercepts ranging

![](_page_8_Figure_9.jpeg)

Fig. 8. Box-and-whisker plots of true (manual) and automated (R package findpeaks [R-FP], regression of exponential decay [SWDP-R], and "knee" of curve [SWDP-K]) field capacities for (A) citrus grower orchard with conventional irrigation scheduling (CCS), (B) turfgrass with conventional irrigation scheduling (TCS), and (C) turfgrass with evapotranspiration controller (TET) datasets.

from 0.0051 to 0.076, and R 2 values from 0.98 to 0.99. Although distributions generally matched the true distributions equally well, the SWDP-R is most consistent across the range of values for the TCS dataset. The SWDP-K and SWDP-R approaches tracked the true values similarly, with the R-FP converging with the SWDP-K and SWDP-R distributions at greater true q FC values.

The estimated q FC distributions followed the true value distribution closest for the TET dataset (Fig. 11C). The slopes ranged from 0.97 to 1.00, with intercepts ranging from 0.003 to 0.006 and R 2 ranging from 0.98 to >0.99. Each of the approaches matched the true values across the range of estimates between 0.22 and 0.29, with greater deviation beyond this range. The

![](_page_9_Figure_1.jpeg)

Fig. 9. True (manual) and automated (R package findpeaks [R-FP], regression of exponential decay [SWDP-R], and "knee" of curve [SWDP-K]) estimates of field capacity for (A) citrus grower orchard with conventional irrigation scheduling (CCS), (B) turfgrass with conventional irrigation scheduling (TCS), and (C) turfgrass with evapotranspiration controller (TET) datasets.

high estimated values from the SWDP-K approach are clearly indicated by the deviation from the 1:1 line toward the upper end of the range. Greater variability and deviation from the 1:1 line toward the low end of the range correspond to the initially low true and estimated values during November and December of the time series.

### 6Discussion

In this study, we demonstrated the effectiveness of multiple automated approaches for estimating q FC from SMS time series. Our empirical results largely confirm the superiority of SAX as an automated q cycle labeling approach, identifying valid (or invalid) cycles relative to expert labeled, as also reported by Figueroa and Pope (2017). We further demonstrated that approaches relying on expedient R packages (R-SAX and R-FP) and the numerically based SWDP approach performed well. The R-SAX approach performed best of the three expedient approaches, probably because it benefits from a training set to calibrate to correct cycles. By comparison, the SWDP and R-FP approaches can be applied without prior information about the dataset or preprocessing with similar results.

The R-FP and SWDP-R approaches performed well in estimating q FC similar to the true values. In general, the SWDP-K approach more consistently overestimated q FC than the other two methods, whereas the SWDP-R approach tended to underestimate q FC values. The differentiation among the methods was most notable for the CCS dataset. The range of the SWDP-R q FC values was relatively consistent compared with the true, SWDP-K, and R-FP values. This may be attributed to a fundamental difference in this approach of estimating

q FC based on an extrapolated regression vs. an actual recorded value, as is the case for the true, SWDP-K, and R-FP approaches.

Although q FC is conventionally assumed to be static, the true values and automated estimates suggest that q FC may have a dynamic range under certain conditions. The observed dynamic nature of q FC could be attributed to the antecedent q conditions of the soil. Merdun and Demirkiran (2008) showed that antecedent q influenced water retention when water was added to soils due to preferential flow patterns. Preferential flows were found to contribute to increased drainage and less soil water retention in soils with lower antecedent q, resulting in a lower q FC. Similarly, Hardie et al. (2011) found that although morphology and chemistry had little influence on infiltration tests in soils, the antecedent q affected the infiltration characteristics of the soil, with dryer soil experiencing deeper and faster infiltration of water. Thus, water additions as irrigation or rainfall in our datasets occurred when the q was at different values. Given the results of Merdun and Demirkiran (2008) and Hardie et al. (2011), we could then expect that the estimated q FC, when considered to be the value of q when drainage losses due to gravity become negligible, would vary.

The concept that q FC varies depending on antecedent q has implications for irrigation management. Although not typically introduced as a management approach to minimize a potentially diminishing q FC due to decreasing antecedent q, the use of maximum allowable depletion (MAD) in irrigation provides a mechanism that minimizes the potential for low q FC. The MAD values set a limit of allowed minimum q. Once this minimum q is reached, irrigation is added. Whereas MAD management practices have traditionally been promoted as a means to minimize

![](_page_10_Figure_1.jpeg)

Fig. 10. Automated estimates (R package findpeaks [R-FP], regression of exponential decay [SWDP-R], and "knee" of curve [SWDP-K]) of field capacity (q FC) vs. true (manual) values from common wetting–drying cycles for (A) citrus grower orchard with conventional irrigation scheduling (CCS), (B) turfgrass with conventional irrigation scheduling (TCS), and (C) turfgrass with evapotranspiration controller (TET) datasets.

plant water stress and associated yield losses (USDA-NRCS, 2005), MAD practices also provide a protection against creating soil environments where low antecedent q occurs, leading to a reduced ability to capture and store water from rainfall or irrigation in soils.

As q FC fluctuations generally occurred during multiple wetting and drying cycles, this suggests probable hysteretical processes. For the TCS and TET data, the increase in q FC between wetting events was generally <2.0% d−1, with a maximum single-day increase of 6.2%, whereas decreases between wetting events were typically <1.5% d−1, with the largest decrease of 6.8% over 2 d. Although gross antecedent q seems to influence the functional q FC, the varying importance of different pore size and structure on the conductivity, diffusion, and retention of water is not captured. Preferential flow and development of flow through fingers are important processes in soil–water dynamics (Doerr et al., 2000; Ritsema and Dekker, 2000; Šimůnek et al., 2003). One of the overarching challenges is linking soil–water dynamics to mechanistic soil structure, and how to integrate biological and ecological processes (Vereecken et al., 2016). As soil water is one of the fundamental determinants of soil biology (Assouline, 2013), further understanding the drivers affecting the dynamic soil–water

![](_page_10_Figure_5.jpeg)

Fig. 11. Distributions of automated (R package findpeaks [R-FP], regression of exponential decay [SWDP-R], and "knee" of curve [SWDP-K]) estimates of field capacity (q FC) values vs. distribution of true (manual) field capacity values for (A) citrus grower orchard with conventional irrigation scheduling (CCS), (B) turfgrass with conventional irrigation scheduling (TCS), and (C) turfgrass with evapotranspiration controller (TET) datasets.

relationship has broad implications on ecological and biogeochemical processes and modeling.

In conclusion, as manual determination involves judgement, subjectivity, and time, automated approaches provide objective, repeatable, and efficient processes for estimating q FC. Although our findings provide promising results for automating the determination of q FC from data-intensive SMS time series and investigating potential implications, the data used in this evaluation were from two locations that have relatively coarse soil texture and are well drained. Our analysis also did not include the potential of upflux or capillary movement of water into the soil profile from shallow water tables. Other studies have noted that these upflux contributions can influence q (Gardner et al., 1970; Jaber et al., 2006). Soil water data measured from finer soil textures (e.g., clay and silt) or overlying shallow confining layers may produce less promising results with the algorithms presented. Thus, these approaches should be used with caution until they have been validated across a broader set of conditions.

### Data Availability

The dataset "Turfgrass with ET Control Turfgrass with Conventional Irrigation Citrus Orchard with Conventional Irrigation Scheduling" is available through the Dryad Digital Repository (Bean et al., 2018).

### References

- Aljoumani, B., J.A. Sànchez-Espigares, N. Canameras, R. Josa, and J. Moserrat. 2012. Time series outlier and intervention analysis: Irrigation management influences on soil water content in silty loam soil. Agric. Water Manage. 111:105–114. [doi:10.1016/j.agwat.2012.05.008](http://dx.doi.org/10.1016/j.agwat.2012.05.008)
- Assouline, S. 2013. Infiltration into soils: Conceptual approaches and solutions. Water Resour. Res. 49:1755–1772. [doi:10.1002/wrcr.20155](http://dx.doi.org/10.1002/wrcr.20155)
- Bean, E.Z., R.G. Huffaker, and K.W. Migliaccio. 2018. Data from: Estimating field capacity from volumetric soil water content time series using automated processing algorithms. Dryad Digital Repository. doi:<10.5061/dryad>.f5220r3
- Blonquist, J.M., S.B. Jones, and D.A. Robinson. 2005. A time domain transmission sensor with TDR performance characteristics. J. Hydrol. 314:235–245. [doi:10.1016/j.jhydrol.2005.04.005](http://dx.doi.org/10.1016/j.jhydrol.2005.04.005)
- Bogena, H.R., M. Herbst, J.A. Huisman, U. Rosenbaum, A. Weuthen, and H. Vereecken. 2010. Potential of wireless sensor networks for measuring soil water content variability. Vadose Zone J. 9:1002–1013. [doi:10.2136/vzj2009.0173](http://dx.doi.org/10.2136/vzj2009.0173)
- Borchers, H. 2018. Package 'pracma': Practical numerical math functions. R Found. Stat. Comput., Vienna. [https://cran.r-project.org/web/pack](https://cran.r-project.org/web/packages/pracma/pracma.pdf)[ages/pracma/pracma.pdf](https://cran.r-project.org/web/packages/pracma/pracma.pdf) (accessed 18 Jan. 2018).
- Cardell-Oliver, R., M. Kranz, K. Smettem, and K. Mayer. 2005. A reactive soil moisture sensor network: Design and field evaluation. Int. J. Distrib. Sens. Netw. 1:149–162. [doi:10.1080/15501320590966422](http://dx.doi.org/10.1080/15501320590966422)
- Chandler, D.G., M.S. Seyfried, J.P. McNamara, and K. Hwang. 2017. Inference of soil hydrologic parameters from electronic soil moisture records. Front. Earth Sci. 5:25. [doi:10.3389/feart.2017.00025](http://dx.doi.org/10.3389/feart.2017.00025)
- Daly, E., and A. Porporato. 2005. A review of soil moisture dynamics: From rainfall infiltration to ecosystem response. Environ. Eng. Sci. 22:9–24. [doi:10.1089/ees.2005.22.9](http://dx.doi.org/10.1089/ees.2005.22.9)
- Dobbs, N.A., K.W. Migliaccio, Y. Li, M.D. Dukes, and K.T. Morgan. 2014. Evaluating irrigation applied and nitrogen leached using different smart irrigation technologies on bahiagrass (Paspalum notatum). Irrig. Sci. 32:193–203. [doi:10.1007/s00271-013-0421-1](http://dx.doi.org/10.1007/s00271-013-0421-1)
- Doerr, S.H., R.A. Shakesby, and R.P.D. Walsh. 2000. Soil water repellency: Its causes, characteristics and hydro-geomorphological significance. Earth Sci. Rev. 51:33–65. [doi:10.1016/S0012-8252\(00\)00011-8](http://dx.doi.org/10.1016/S0012-8252(00)00011-8)
- Evett, S.R., and G.W. Parkin. 2005. Advances in soil water content sensing: The continuing maturation of technology and theory. Vadose Zone J. 4:986–991. [doi:10.2136/vzj2005.0099](http://dx.doi.org/10.2136/vzj2005.0099)
- Figueroa, M., and C. Pope. 2017. Root system water consumption pattern identification on time series data. Sensors 17:1410. [doi:10.3390/s17061410](http://dx.doi.org/10.3390/s17061410)
- Gardner, W.R., D. Hillel, and Y. Benyamini. 1970. Post‐irrigation movement of soil water: 1. Redistribution. Water Resour. Res. 6:851–861. [doi:10.1029/WR006i003p00851](http://dx.doi.org/10.1029/WR006i003p00851)
- Hardie, M.A., W.E. Cotching, R.B. Doyle, G. Holz, S. Lisson, and K. Mattern. 2011. Effect of antecedent soil moisture on preferential flow in a texture-contrast soil. J. Hydrol. 398:191–201. [doi:10.1016/j.jhydrol.2010.12.008](http://dx.doi.org/10.1016/j.jhydrol.2010.12.008)
- Hillel, D. 1998. Environmental soil physics. Academic Press, San Diego.

- Jaber, F.H., S. Shukla, and S. Srivastava. 2006. Recharge, upflux and water table response for shallow water table conditions in southwest Florida. Hydrol. Processes 20:1895–1907. [doi:10.1002/hyp.5951](http://dx.doi.org/10.1002/hyp.5951)
- Ladson, A.R., J.R. Lander, A.W. Western, R.B. Grayson, and L. Zhang. 2006. Estimating extractable soil moisture content for Australian soils from field measurements. Aust. J. Soil Res. 44:531–541. [doi:10.1071/SR04180](http://dx.doi.org/10.1071/SR04180)
- Merdun, H.R.M., and A.R. Demirkiran. 2008. Effect of the initial soil moisture content on the spatial distribution of the water retention. Eurasian Soil Sci. 41:1098–1106. [doi:10.1134/S1064229308100128](http://dx.doi.org/10.1134/S1064229308100128)
- Pan, F., Y.A. Pachepsky, A.K. Guber, and R.L. Hill. 2011. Information and complexity measures applied to observed and simulated soil moisture time series. Hydrol. Sci. J. 56:1027–1039. [doi:10.1080/02626667.2011.595374](http://dx.doi.org/10.1080/02626667.2011.595374)
- Pastore, M. 2017. Package 'overlapping': Estimation of overlapping in empirical distributions. R Found. Stat. Comput., Vienna. [https://cran.r-project.](https://cran.r-project.org/web/packages/overlapping/index.html) [org/web/packages/overlapping/index.html](https://cran.r-project.org/web/packages/overlapping/index.html) (accessed 26 Jan. 2018).
- Ritsema, C.J., and L.W. Dekker. 2000. Preferential flow in water repellent sandy soils: Principles and modeling implications. J. Hydrol. 231– 232:308–319. [doi:10.1016/S0022-1694\(00\)00203-1](http://dx.doi.org/10.1016/S0022-1694(00)00203-1)
- Ritter, A., F. Hupet, R. Munoz-Carpena, S. Lambot, and M. Vanclooster. 2003. Using inverse methods for estimating soil hydraulic properties from field data as an alternative to direct methods. Agric. Water Manage. 59:77–96. [doi:10.1016/S0378-3774\(02\)00160-9](http://dx.doi.org/10.1016/S0378-3774(02)00160-9)
- Rosenbaum, U., J.A. Huisman, J. Arba, H. Vereeken, and H.R. Bogena. 2011. Correction of temperature and electrical conductivity effects on dielectric permittivity measurements with ECH2O sensors. Vadose Zone J. 10:582–593. [doi:10.2136/vzj2010.0083](http://dx.doi.org/10.2136/vzj2010.0083)
- Schaefer, G.L., M.H. Cosh, and T.J. Jackson. 2007. The USDA Natural Resources Conservation Service Soil Climate Analysis Network (SCAN). J. Atmos. Ocean. Technol. 24:2073–2077. [doi:10.1175/2007JTECHA930.1](http://dx.doi.org/10.1175/2007JTECHA930.1)
- Senin, P. 2018. Package 'jmotif': Time series analysis toolkit based on symbolic aggregate discretization, i.e., SAX. R Found. Stat. Comput., Vienna. <https://cran.r-project.org/web/packages/jmotif/jmotif.pdf> (accessed 13 Jan. 2018).
- Šimůnek, J., N.J. Jarvis, M.Th. van Genuchten, and A. Gardenas. 2003. Review and comparison of models for describing non-equilibrium and preferential flow and transport in the vadose zone. J. Hydrol. 272:14–35. [doi:10.1016/S0022-1694\(02\)00252-4](http://dx.doi.org/10.1016/S0022-1694(02)00252-4)
- Topp, G.C. 2003. State of the art of measuring soil water content. Hydrol. Processes 17:2993–2996. [doi:10.1002/hyp.5148](https://dx.doi.org/10.1002/hyp.5148)
- USDA–NRCS. 2005. Chapter 9: Irrigation water management. In: Irrigation guide. Part 652. USDA–NRCS, Washington, DC. [https://www.nrcs.usda.](https://www.nrcs.usda.gov/Internet/FSE_DOCUMENTS/nrcs141p2_017781.pdf) [gov/Internet/FSE\\_DOCUMENTS/nrcs141p2\\_017781.pdf](https://www.nrcs.usda.gov/Internet/FSE_DOCUMENTS/nrcs141p2_017781.pdf) (accessed 3 Apr. 2018).
- Vereecken, H., A. Schnepf, J.W. Hopmans, M. Javaux, D. Or, T. Roose, J. Vanderborght, et al. 2016. Modeling soil processes: Review, key challenges, and new perspectives. Vadose Zone J. 15(5). [doi:10.2136/vzj2015.09.0131](http://dx.doi.org/10.2136/vzj2015.09.0131)
- Yang, R.M., F. Liu, G. Zhang, Y. Zhao, D. Li, J. Yang, et al. 2016. Mapping soil texture based on field soil moisture observations at a high temporal resolution in an oasis agricultural area. Pedosphere 26:699–708. [doi:10.1016/S1002-0160\(15\)60078-9](http://dx.doi.org/10.1016/S1002-0160(15)60078-9)