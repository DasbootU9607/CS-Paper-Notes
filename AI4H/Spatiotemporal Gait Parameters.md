---
title: "Agreement Between Spatiotemporal Gait Parameters Measured by a Markerless Motion Capture System and Two Reference Systems—a Treadmill-Based Photoelectric Cell and High-Speed Video Analyses: Comparative Study"
authors: Felipe García-Pinillos, Diego Jaén-Carrillo, Victor Soto Hermoso, Pedro Latorre Román, Pedro Delgado, Cristian Martinez, Antonio Carton, Luis Roche Seruendo
journal: JMIR mHealth and uHealth
year: "2020"
doi: 10.2196/19498
priority: High
status: Read
---
# Agreement Between Spatiotemporal Gait Parameters Measured by a Markerless Motion Capture System and Two Reference Systems—a Treadmill-Based Photoelectric Cell and High-Speed Video Analyses: Comparative Study



## 1. Overview



| Item                       | Notes                                                                                                                                                                                                                                        |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Relevance to PosePro       | High                                                                                                                                                                                                                                         |
| Main use                   | Reference standard, parameter selection, error metrics, video acquisition, robustness analysis, limitations discussion                                                                                                                       |
| One-sentence value         | This paper compares a marker-less gait system with two reference systems and shows that agreement is parameter-dependent on step frequency and step length are valid. Additionally, contact time and especially flight time require caution. |
| Abbreviations in the paper | CV: coefficient of variation <br>ICC: intraclass correlation coefficient<br>LED: light-emitting diode <br>SPM: steps per minute                                                                                                              |

  

## 2. Study Design

  

| Item                       | Notes                                                                                                                                                                                                                                                                                      |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Participants / sample size | 25 amateur endurance runners: 22 male and 3 female; age mean 24 years, SD 6; height mean 1.75 m, SD 0.07; body mass mean 71 kg, SD 7.4.                                                                                                                                                    |
| Population type            | Healthy amateur endurance runners. Inclusion required: <br>(1) age >=18 years; <br>(2) ability to run 10 km in less than 50 min;<br>(3) Absence of any injury.<br>Points 2 and 3 are valid for the 6 months before data collection.                                                        |
| Walking task               | Treadmill running. Speed increased from 8 km/h by 1 km/h each minute until 12 km/h, followed by an 8-min accommodation period at 12 km/h. Recording lasted 3 min at 12 km/h, with 30 s analyzed.                                                                                           |
| Tested system              | Microsoft Kinect version 1.0 with MotionMetrix software. Two Kinect sensors were set on either side of the treadmill. The paper states that Kinect can locate 20 body joints in 3D at 30 Hz, and the two-sensor setup can reach 60 Hz if both sensors track the same point simultaneously. |
| Reference / ground truth   | Two reference systems: OptoGait treadmill-based photoelectric cells and high-speed video analysis at 1000 Hz. Both reference systems had temporal accuracy of +/-1 ms.                                                                                                                     |
| Video / acquisition setup  | High-speed camera was placed perpendicular to the treadmill from a posterior view, 2 m from the treadmill center and 0.80 m high. Video was recorded at 1000 fps with 784 x 144 resolution and analyzed in Kinovea 0.8.27.                                                                 |
| Comparison approach        | Kinect+MotionMetrix spatiotemporal parameters were compared with OptoGait and high-speed video analysis. The study assessed absolute reliability with CV and concurrent validity with Pearson r, ICC, and Bland-Altman limits of agreement.                                                |

  

## 3. Tested Parameters

  

| Parameter                | Covered? | Notes / results                                                                                                                                                                                                                  |
| ------------------------ | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Gait speed               | Yes      | Running velocity was fixed at 12 km/h to control the influence of speed on spatiotemporal parameters. Gait speed itself was not validated as an output.                                                                          |
| Step length              | Yes      | Kinect+MotionMetrix was very close to both references: 115.44 cm vs 115.53 cm for OptoGait and 116.58 cm for video analysis. Differences were -0.1% vs OptoGait and -1.0% vs video.                                              |
| Step width               | No       |                                                                                                                                                                                                                                  |
| Cadence                  | Yes      | Cadence was represented as step frequency in this paper which was reported in steps per minute. Kinect+MotionMetrix was 167.23 SPM vs 166.60 SPM for OptoGait and 165.76 SPM for video analysis. Differences were 0.4% and 0.9%. |
| Step time / support time | Partly   | Contact time and flight time were measured. <br>Contact time was slightly overestimated; <br>flight time was strongly underestimated. <br>Step time was used in equations but was not the main reported comparison variable.     |
| Joint angles             | No       |                                                                                                                                                                                                                                  |
| Other parameters         | Yes      | Contact time and flight time were central temporal parameters. <br>Contact time: Kinect 0.273 s, OptoGait 0.265 s, video 0.262 s. <br>Flight time: Kinect 0.082 s, OptoGait 0.089 s, video 0.097 s.                              |

  

## 4. Statistical Metrics

  

| Metric                 | Used? | Use / result                                                                                                                                                                                          |
| ---------------------- | ----- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AE / MAE               | No    |                                                                                                                                                                                                       |
| MAPE / MAE%            | No    |                                                                                                                                                                                                       |
| RMSE                   | No    |                                                                                                                                                                                                       |
| Bias / mean difference | Yes   | Mean differences were reported in Table 1 and Bland-Altman analysis. Temporal parameters showed larger bias than step frequency and step length.                                                      |
| ICC                    | Yes   | ICCs were calculated with a two-way random-effects model, mean of measurements, and absolute agreement definition. Step frequency and step length showed almost perfect ICCs. Contact time was lower. |
| Bland-Altman / LoA     | Yes   | Bland-Altman plots were used to examine systematic bias, random error, and 95% limits of agreement. Heteroscedasticity was defined as r2 > 0.1.                                                       |
| Pearson r              | Yes   | Pearson correlations were used for concurrent validity. Most parameters had very high or almost perfect correlations; contact time was weaker.                                                        |
| SEM / MDC              | No    |                                                                                                                                                                                                       |

  

## 5. Key Results

  

- The Kinect+MotionMetrix system had higher CVs than the two reference systems for all reported spatiotemporal parameters.

- Flight time had the highest CV regardless of system: 16.4% for OptoGait, 17.3% for video analysis, and 23.2% for Kinect+MotionMetrix. All other CVs were below 8.1%.

- Compared with OptoGait, Kinect+MotionMetrix overestimated contact time by 3.0% and underestimated flight time by 7.9%.

- Compared with high-speed video analysis, Kinect+MotionMetrix overestimated contact time by 4.2% and underestimated flight time by 11.3%.

- Step frequency and step length were the most reliable outputs for the markerless system. Differences were lower than 1% for both parameters when compared with reference systems.

- Pearson r and ICC results were strong for most variables. For MotionMetrix vs OptoGait, contact time had r=0.645 and ICC=0.712, while flight time, step frequency, and step length had r>0.901 and ICCs>0.89.

- For MotionMetrix vs video analysis, contact time had r=0.664 and ICC=0.667, while the other variables had r>0.928 and ICCs>0.84.

- Bland-Altman analysis showed small systematic bias and random error for step frequency and step length, but larger bias and error for contact time and flight time.

- Heteroscedasticity was found for temporal parameters in the OptoGait comparison. In the video comparison, only step frequency was homoscedastic; the other parameters showed heteroscedasticity.

  

## 6. Limitations and Risk Warnings

  

- Participants were limited to healthy amateur endurance runners evaluated at a treadmill speed of 12 km/h. 

- There is difference in system precision: OptoGait and high-speed video captured at 1000 Hz, while Kinect+MotionMetrix worked at 60 Hz.

- The paper explains that 60 Hz corresponds to about 0.017 s precision, while the reference systems have 0.001 s precision. This might contribute to temporal-parameter errors.

- Contact time had only moderate/substantial agreement, while flight time had high correlation but CV and clear underestimation.

- Manufacturer recommendations were strict: dynamic calibration, tight clothes, no shiny black fabric or reflections, no moving shoelaces, no moving hair, no sunlight, and no treadmill parts blocking the runner.

- The study does not validate step width, gait speed estimation, joint angles, turning, start/stop phases, outdoor conditions, or smartphone video.



## 7. Implications

  

| Aspect                     | Implication                                                                                                                                                                                                                     |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Reference standard         | A validation study should use a strong reference system. This paper supports using photoelectric-cell systems, high-speed video, or other validated systems as comparators, but the reference precision must be reported.       |
| Parameter selection        | First-stage validation should separate spatial parameters from temporal parameters. Step length and cadence/step frequency may be lower risk; contact time, flight time, and support-phase metrics require stricter validation. |
| Error metrics              | We should report CV or another reliability metric, Pearson r, ICC with confidence intervals, mean difference/bias, and Bland-Altman limits of agreement.                                                                        |
| Video usability assessment | The video intake should record clothing, occlusion, lighting, shadows/reflections, full-body visibility, camera view, frame rate, and whether any body or treadmill parts are blocked.                                          |
| Robustness grouping        | Error analysis should be grouped by parameter type, walking/running speed, camera setup, video quality, and population. Temporal parameters should be reviewed separately from step length/cadence.                             |
| Report discussion          | The report should avoid saying that a markerless system is globally valid. The more defensible wording is that validity depends on the measured variable, the software, the reference system, and the test protocol.            |

  

## 8. Final Judgment

  

| Question                       | Yes/No | Judgment                                                                                                                                                                                                                                        |
| ------------------------------ | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Core paper?                    | Yes    |                                                                                                                                                                                                                                                 |
| Should it be cited?            | Yes    |                                                                                                                                                                                                                                                 |
| Should it be reread carefully? | Yes    | Reread Methods, Tables 1-3, Figure 1, and the final Discussion paragraphs when designing the PosePro validation metrics.                                                                                                                        |
| One-sentence summary           | NA     | Kinect+MotionMetrix can validly measure step frequency and step length during controlled treadmill running, but it overestimates contact time and underestimates flight time, showing why PosePro must validate each gait parameter separately. |
