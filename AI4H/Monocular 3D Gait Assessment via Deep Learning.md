---
title: Algorithm based on one monocular video delivers highly valid and reliable gait parameters
authors: Arash Azhand, Sophie Rabe, Swantje Müller, Igor Sattler,  Anika Heimann‐Steinert
journal: Scientific Reports
year: "2021"
doi: https://doi.org/10.1038/s41598-021-93530-z
last_updated: 2026-06-01
github_user: DasbootU9607
priority: High
status: Read
---
# Algorithm based on one monocular video delivers highly valid and reliable gait parameters

  

## 1. Overview

  

| Item               | Notes                                                                                                                                                            |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Relevance          | High                                                                                                                                                             |
| Main use           | Reference standard / Parameter selection / Error metrics / Video acquisition / Robustness analysis / Limitations discussion                                      |
| One-sentence value | This paper validates a monocular smartphone-camera gait algorithm against GAITRite and shows high agreement for gait speed, cadence, step length, and step time. |

  

## 2. Study Design

  

| Item                       | Notes                                                                                                                                                                                           |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Participants / sample size | The paper reports 44 healthy adults, age mean 73.9 years, SD 6.0, range 65-91. After exclusions, Methods states 514 videos by 43 subjects were included.                                        |
| Population type            | Healthy older adults recruited from former contacts of the Geriatrics Research Group, Charite-Universitatsmedizin Berlin.                                                                       |
| Walking task               | Six walks per participant: three preferred gait speed walks and three fast gait speed walks over the GAITRite carpet.                                                                           |
| Tested system              | Smartphone camera application (SCA): monocular video plus 2D skeleton tracker, 3D skeleton tracker, 3D skeleton optimization, and gait parameter calculation.                                   |
| Reference / ground truth   | GAITRite pressure-sensitive walkway system (GS), described as a gold-standard clinical gait assessment tool and previously validated against Vicon.                                             |
| Video / acquisition setup  | Two videos per walk: SCA Hand using a hand-held smartphone and SCA Stand using a smartphone fixed on a stand. The algorithm currently applies to frontal-view videos, with a stationary camera. |
| Comparison approach        | SCA Hand and SCA Stand outputs were compared with simultaneous GAITRite measurements. Results were averaged over preferred and fast gait speed trials.                                          |

  

## 3. Tested Parameters

  

| Parameter                | Covered?           | Notes / results                                                                                                                     |
| ------------------------ | ------------------ | ----------------------------------------------------------------------------------------------------------------------------------- |
| Gait speed               | Yes                | GS mean 1.42 m/s. ICC(2,k): 0.982 for SCA Hand and 0.981 for SCA Stand. Mean difference: 0.28% and 2.5% of mean.                    |
| Step length              | Yes                | GS mean 69.22 cm. ICC(2,k): 0.961 for SCA Hand and 0.958 for SCA Stand. Mean difference: 0.23% and 1.77% of mean.                   |
| Step width               | No                 |                                                                                                                                     |
| Cadence                  | Yes                | GS mean 121.77 steps/min. ICC(2,k): 0.983 for SCA Hand and 0.980 for SCA Stand. Mean difference: 0.52% and 0.84% of mean.           |
| Step time / support time | Partly             | Step time was validated; support time was not. GS mean step time was 0.500 s. ICC(2,k): 0.987 for SCA Hand and 0.984 for SCA Stand. |
| Joint angles             | No for validation  | The system can calculate kinematical angle parameters, but this validation reports only GAITRite ground-level parameters.           |
| Other parameters         | No main validation | The authors mention foot heights and angle parameters as possible outputs, but they are not validated here.                         |



## 4. Statistical Metrics

  

| Metric                 | Used?  | Use / result                                                                                                                                               |
| ---------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AE / MAE               | Partly | Bland-Altman plots include mean absolute differences as measurement error. Reported error was about 0.5-2% of corresponding parameter mean.                |
| MAPE / MAE%            | No     |                                                                                                                                                            |
| RMSE                   | No     |                                                                                                                                                            |
| Bias / mean difference | Yes    | Mean differences between SCA and GS were transformed into percentage of GS means. No parameter differed by more than 3.25% of the corresponding mean.      |
| ICC                    | Yes    | Concurrent validity used ICC(2,k), ranging 0.958-0.987. Test-retest repeatability used ICC(3,1), ranging 0.915-0.950.                                      |
| Bland-Altman / LoA     | Yes    | Bland-Altman plots were used for gait speed, cadence, average step length, and average step time. Wider intervals appeared for gait speed and step length. |
| Pearson r              | No     |                                                                                                                                                            |
| SEM / MDC              | No     |                                                                                                                                                            |

  

## 5. Key Results

  

- All measured gait parameters showed excellent concurrent validity against GAITRite.

- ICC(2,k) ranged from 0.958 to 0.987 for gait speed, cadence, step length, and step time.

- Test-retest repeatability of SCA was on the same level as GAITRite, with ICC(3,1) from 0.915 to 0.950.

- Mean differences were small: SCA Hand bias was about 0.2-0.7%; SCA Stand bias was about 0.6-2.8%.

- Bland-Altman error was narrower for step time and cadence, and wider for gait speed and step length.

- The authors note step length had some larger errors, including cases above 10 cm.

  

## 6. Limitations and Risk Warnings

  

- The system was tested in healthy older adults.

- Current applicability is limited to frontal-view videos; walking toward and away from the camera can work, but side-view evidence is not provided.

- The camera should be stationary. If the person recording walks toward or away from the participant, validity and reliability may deteriorate.

- Errors may arise from clothing, background, lighting, lower-body key-point detection, parallax, and field-of-view edge effects.

  

## 7. Implications

  

| Aspect                     | Implication                                                                                                                                                                   |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Reference standard         | GAITRite is a strong comparator for PosePro basic spatiotemporal parameters, especially gait speed, cadence, step length, and step time.                                      |
| Parameter selection        | First-stage validation can prioritize gait speed, cadence, step length, and step time. Step width, support time, and joint angles need separate evidence.                     |
| Error metrics              | PosePro should report ICC, mean difference/bias, confidence intervals, and Bland-Altman limits of agreement. Test-retest ICC is useful if repeated trials are available.      |
| Video usability assessment | Record whether the view is frontal, whether the camera is stationary, whether the whole lower body is visible, and whether lighting/background/clothing may affect keypoints. |
| Robustness grouping        | Group errors by hand-held vs fixed camera, walking direction, speed condition, video quality, and parameter type.                                                             |
| Report discussion          | This paper supports monocular video feasibility, but only for selected ground-level gait parameters under controlled conditions.                                              |

  

## 8. Final Judgment

  

| Question                       | Yes/No | Judgment                                                                                                                                                                                                 |
| ------------------------------ | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Core paper?                    | Yes    |                                                                                                                                                                                                          |
| Should it be cited?            | Yes    |                                                                                                                                                                                                          |
| Should it be reread carefully? | Yes    | Yes, especially Table 1, Fig. 2, Methods, and Discussion limitations.                                                                                                                                    |
| One-sentence summary           | NA     | A monocular smartphone-video algorithm can estimate gait speed, cadence, step length, and step time with excellent agreement against GAITRite, but step length and recording conditions require caution. |
