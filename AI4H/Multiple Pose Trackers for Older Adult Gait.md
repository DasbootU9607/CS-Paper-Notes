---
title: "Concurrent validity of human pose tracking in video for measuring gait parameters in older adults: a preliminary analysis with multiple trackers, viewing angles, and walking directions"
authors: Mehdizadeh S, Nabavi H, Sabo A, Arora T, Iaboni A, Taati B
journal: Journal of NeuroEngineering and Rehabilitation
year: 2021
doi: https://doi.org/10.1186/s12984-021-00933-0
last_updated: 2026-06-02
github_user: DasbootU9607
priority: High
status: Read
---
 

# Concurrent validity of human pose tracking in video for measuring gait parameters in older adults

  

## 1. Overview

  

| Item               | Notes                                                                                                                                                            |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Relevance          | High                                                                                                                                                             |
| Main use           | Robustness analysis; parameter selection; video acquisition; limitations discussion                                                                              |
| One-sentence value | This paper shows that RGB-video pose tracking can estimate temporal gait variables in older adults, but spatial and variability measures are much less reliable. |

  

## 2. Study Design

  

| Item                       | Notes                                                                                                                                                                                                  |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Participants / sample size | 11 older adults were included in the final analysis; mean age = 85.2 years. The original target was 20, but recruitment stopped because of Covid-19.                                                   |
| Population type            | Retirement-home residents, age > 65 years, able to walk independently over 20 m.                                                                                                                       |
| Walking task               | Participants walked back and forth for 1 min along a flat room surface. Walking distance was about 13 m. They walked at their normal pace. Turns were excluded from analysis.                          |
| Tested system              | Standard RGB videos processed by three pose trackers: AlphaPose, OpenPose, and Detectron.                                                                                                              |
| Reference / ground truth   | Xsens MVN Awinda system with seven wireless IMUs, recorded at 100 Hz. The paper used it as the 3D motion capture reference / gold standard.                                                            |
| Video / acquisition setup  | Two Motorola Moto G5 Play phones, 13 MP camera, 30 fps, 1080p. Two camera heights: 111 cm eye-level and 205 cm top/ceiling-like view. Front-view and back-view walking clips were analyzed separately. |
| Comparison approach        | Video-derived gait variables were correlated with Xsens-derived gait variables across 24 conditions: 3 trackers x 2 camera heights x 2 walking views x 2 calculation methods.                          |

  

## 3. Tested Parameters

  

| Parameter                | Covered? | Notes / results                                                                                                                                                                                     |
| ------------------------ | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Gait speed               | No       |                                                                                                                                                                                                     |
| Step length              | No       |                                                                                                                                                                                                     |
| Step width               | Yes      | Weak to moderate correlations. Detectron performed relatively better for some front-view conditions, but step width remained much less reliable than cadence and step time.                         |
| Cadence                  | Yes      | Strongest result. Cadence had very high correlations with motion capture in most conditions, often R = 0.97-1.00.                                                                                   |
| Step time / support time | Yes      | Step time correlated well with motion capture, especially with eye-level camera: R = 0.71 for individual steps and about R = 1.00 after averaging over steps. Support time was not a main variable. |
| Joint angles             | No       |                                                                                                                                                                                                     |
| Other parameters         | Yes      | Step time CV, step width CV, and estimated margin of stability (eMOS). Variability measures and eMOS were generally weak and should be treated cautiously.                                          |

  

## 4. Statistical Metrics

  

| Metric                 | Used?        | Use / result                                                                                                                                     |
| ---------------------- | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| AE / MAE               | No           |                                                                                                                                                  |
| MAPE / MAE%            | No           |                                                                                                                                                  |
| RMSE                   | No           |                                                                                                                                                  |
| Bias / mean difference | No           |                                                                                                                                                  |
| ICC                    | No           |                                                                                                                                                  |
| Bland-Altman / LoA     | Yes, limited | Used to compare pairs of pose trackers for spatial variables. AlphaPose and Detectron had narrower agreement bands than OpenPose-vs-other pairs. |
| Pearson r              | Yes          | Main concurrent-validity metric. Correlations between video-derived variables and Xsens-derived variables were reported.                         |
| SEM / MDC              | No           |                                                                                                                                                  |
| CV                     | Yes          | Used for gait variability variables and for comparing precision between pose trackers.                                                           |

  

## 5. Key Results

  

- Temporal variables performed best. Cadence and step time calculated from video pose tracking had high correlation with Xsens motion capture.

- Spatial variables were weaker. Step width and eMOS had low to moderate correlations and were not consistently reliable.

- Variability measures were poor. Step time CV and step width CV often had near-zero or negative correlations.

- Averaging gait variables over all steps improved correlations. The authors warn that individual step-level values are less reliable and may not be suitable for clinical decision making.

- Camera height had limited impact. There were no major differences between eye-level and top camera views in terms of correlation with motion capture.

- Walking direction had limited impact. Front-view and back-view walks had broadly similar correlation patterns, though back view could suffer from leg occlusion.

- Algorithm choice mattered. AlphaPose and Detectron showed more agreement with each other; OpenPose had lower agreement with the other two.

  

## 6. Limitations and Risk Warnings

  

- This was a preliminary analysis with only 11 older adults. The sample size limits generalization.

- Participants were older adults who could walk independently for 20 m. The study did not include people with more severe mobility problems.

- Turns were excluded because pose tracking algorithms could not accurately estimate body landmarks during turns.

- The analysis used 2D pose estimation. The authors explicitly note that 3D pose estimation and joint angles still need validation.

- Spatial gait variables need accurate frame-by-frame joint localization, which current 2D pose trackers may not provide.

- Back-view videos can include occlusion: the trailing leg may obscure the leading leg, affecting foot contact time and foot position.

- Blurred frames, parallax/perspective issues, and mismatch between video keypoints and motion-capture landmarks can reduce agreement.

  

## 7. Implications

  

| Aspect                     | Implication                                                                                                                                                         |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Reference standard         | IMU-based motion capture such as Xsens can serve as a practical reference when optical motion capture is unavailable, but its status should be described carefully. |
| Parameter selection        | We should prioritize cadence and step time for early validation. Step width, eMOS, and variability metrics should be high-risk parameters.                          |
| Error metrics              | Pearson r alone is not enough for PosePro, but this paper supports using correlation as one part of concurrent-validity analysis.                                   |
| Video usability assessment | We should record camera height, walking direction, frame blur, occlusion, turn segments, and whether front/back view is used.                                       |
| Robustness grouping        | Strong support for grouping by pose tracker, camera height, front vs back view, and step-level vs participant-average output.                                       |
| Report discussion          | Cite this paper to explain why temporal gait parameters are more feasible from 2D video than spatial, variability, or stability measures.                           |
  

## 8. Final Judgment

  

| Question                       | Yes/No | Judgment                                                                                                                                                                      |
| ------------------------------ | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Core paper?                    | Yes    | Core paper for robustness analysis and parameter risk stratification.                                                                                                         |
| Should it be cited?            | Yes    | Especially useful for older adults, RGB video, multiple trackers, camera height, walking direction, and temporal-vs-spatial parameter differences.                            |
| Should it be reread carefully? | Yes    | Reread Abstract, Methods, Tables 3-6, Discussion, and Conclusions before designing robustness groups.                                                                         |
| One-sentence summary           | NA     | In older adults, 2D RGB-video pose tracking agrees well with motion capture for cadence and step time, but step width, eMOS, and variability measures are much less reliable. |

  

