---
title: "Clinical gait analysis using video-based pose\r

  estimation: Multiple perspectives, clinical\r

  populations, and measuring change"
authors: Stenum J, Hsu MM, Pantelyat AY, Roemmich RT
journal: PLOS Digital Health
year: "2024"
doi: https://doi.org/10.1371/journal.pdig.0000467
priority: High
status: Read
---
# Clinical gait analysis using video-based pose estimation: Multiple perspectives, clinical populations, and measuring change

  

## 1. Overview
  

| Item               | Notes                                                                                                                                |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| Relevance          | High                                                                                                                                 |
| Main use           | Reference standard, parameter selection, error metrics, video acquisition, robustness analysis, limitations discussion               |
| One-sentence value | This paper shows how a low-cost video and OpenPose workflow can be validated against 3D motion capture in clinical gait populations. |

  

## 2. Study Design

  

| Item                       | Notes                                                                                                                                                                                                                                                                       |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Participants / sample size | 44 individuals post-stroke, 19 individuals with Parkinson's Disease (PD), and a public dataset of 32 unimpaired adults.                                                                                                                                                     |
| Population type            | Neurological gait impairment plus unimpaired adults. Some stroke participants used a cane.                                                                                                                                                                                  |
| Walking task               | (1) Preferred-speed and fast-speed ten-meter walk tests<br>(2) Eight overground walking trials across a 4.83 m walkway.                                                                                                                                                     |
| Tested system              | A video-based gait analysis workflow using OpenPose BODY_25 keypoints and MATLAB post-processing. The workflow supports sagittal-view and frontal-view videos.                                                                                                              |
| Reference / ground truth   | Marker-based 3D motion capture. The clinical dataset used ten Vicon Vero cameras at 100 Hz. The public unimpaired dataset also included synchronized 3D motion capture.                                                                                                     |
| Video / acquisition setup  | Two Samsung Galaxy Tab A7 tablets on tripods, recording at 30 Hz and 1920 x 1080 resolution. One tablet captured the frontal view and one captured the sagittal view. The public unimpaired dataset used two frontal-view Basler cameras at 25 Hz and 960 x 540 resolution. |
| Comparison approach        | Video-derived gait parameters were compared with motion-capture-derived parameters at the step, trial, and session levels. The main paper emphasizes session-level averages for the stroke and PD groups, which is close to a clinical reporting scenario.                  |

  

## 3. Tested Parameters

  

| Parameter                | Covered?       | Notes / results                                                                                                                                                                                    |
| ------------------------ | -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Gait speed               | Yes            | Strong agreement with motion capture. Errors were generally small enough to be clinically meaningful for many populations.                                                                         |
| Step length              | Yes            | Sagittal-view estimates were more accurate than frontal-view estimates. Frontal-view step length was affected by walking direction.                                                                |
| Step width               | No             |                                                                                                                                                                                                    |
| Cadence                  | No             |                                                                                                                                                                                                    |
| Step time / support time | Step time only | Step time showed very small error, especially in sagittal-view videos. Support time was not a main output.                                                                                         |
| Joint angles             | Yes            | Sagittal-plane hip, knee, and ankle kinematics were compared with motion capture. Hip and knee were more reliable than ankle.                                                                      |
| Other parameters         | Yes            | Stroke-specific asymmetry metrics: step time asymmetry and step length asymmetry. PD-specific metric: trunk inclination. Speed-related changes from preferred to fast walking were also evaluated. |

  

## 4. Statistical Metrics

  

| Metric                 | Used?        | Use / result                                                                                                                                                               |
| ---------------------- | ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AE / MAE               | Yes          | The paper reports errors as absolute differences. MAE is used for lower-limb joint kinematics.                                                                             |
| MAPE / MAE%            | No           |                                                                                                                                                                            |
| RMSE                   | No           |                                                                                                                                                                            |
| Bias / mean difference | Yes          | Mean differences between motion capture and video were reported.                                                                                                           |
| ICC                    | No           |                                                                                                                                                                            |
| Bland-Altman / LoA     | Yes          | 95% limits of agreement were reported as mean difference +/- 1.96 SD. This is useful for PosePro validation reporting.                                                     |
| Pearson r              | Yes          | Pearson correlations were used to quantify association between video and motion capture measurements.                                                                      |
| SEM / MDC              | Not directly | The discussion compares video errors with published minimal detectable change or clinically meaningful change values, but SEM/MDC were not computed as primary statistics. |

  

## 5. Key Results

  

- The workflow could estimate clinically relevant gait parameters from simple videos recorded with low-cost tablets, across unimpaired adults, post-stroke participants, and participants with Parkinson's disease.

- Sagittal-view videos generally produced lower errors and stronger agreement with motion capture than frontal-view videos.

- Step time, step length, and gait speed were strongly correlated with motion capture. For the post-stroke group, sagittal-view errors were about 0.01 s for step time, 0.03 m for step length, and 0.04 m/s for gait speed. Frontal-view errors were larger, about 0.05 s, 0.07 m, and 0.10 m/s respectively.

- For the Parkinson's disease group, sagittal-view errors were about 0.01 s for step time, 0.02 m for step length, and 0.03 m/s for gait speed. Frontal-view errors were larger, about 0.03 s, 0.07 m, and 0.15 m/s respectively.

- Hip and knee sagittal-plane kinematics were more accurate than ankle kinematics. The discussion notes that average errors for hip and knee were below about 4 degrees, while ankle errors could be higher.

- The workflow could detect within-participant changes from preferred to fast walking speed, which is important for rehabilitation monitoring.

- Frontal-view spatial parameters were influenced by walking direction. The paper reports better precision when participants walked toward the camera than when they walked away from it.

  

## 6. Limitations and Risk Warnings

  

- The method is not intended to match the accuracy of marker-based motion capture. It is positioned as a reasonably accurate, accessible clinical tool.

- Sagittal-view videos are preferable when possible, especially for parameters requiring higher precision.

- Frontal-view videos can support spatiotemporal parameters, but they are weaker for spatial estimates such as step length and are affected by walking direction.

- Ankle kinematics are less reliable than hip and knee kinematics.

- The current workflow requires technical processing: OpenPose, GPU-based computation, MATLAB post-processing, and manual checking/correction in some cases.

- The authors used a pre-trained OpenPose model. Performance may differ in populations whose body structure, assistive devices, clothing, or movement patterns differ from the training data.

- This paper does not validate step width, cadence, support time, or 3D joint kinematics as main outputs.

  


## 7. Implications 

  

| Aspect                     | Implication                                                                                                                                                                                      |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Reference standard         | PosePro should ideally be compared with a strong reference system such as 3D motion capture, a pressure walkway, validated wearable sensors, or carefully designed manual annotation.            |
| Parameter selection        | First-stage validation should prioritize gait speed, step time, and step length. Step width and joint angles should be treated as higher-risk outputs requiring separate validation.             |
| Error metrics              | We should report absolute error / MAE, mean difference or bias, Pearson correlation, and 95% limits of agreement. If sample size allows, ICC can be added even though this paper did not use it. |
| Video usability assessment | The evaluation form should record camera view, walking direction, full-body visibility, frame rate, resolution, distance to camera, and whether assistive devices are present.                   |
| Robustness grouping        | We should analyze performance by camera view, walking direction, patient group, walking speed, assistive device use, and video quality.                                                          |

  

## 8. Final Judgment

  

| Question                       | Yes/No | Judgment                                                                                                                                                                                                       |
| ------------------------------ | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Core paper?                    | Yes    | This is one of the core papers for PosePro's video-based clinical gait validation framework.                                                                                                                   |
| Should it be cited?            | Yes    | It directly supports low-cost video gait analysis, multi-view validation, clinical populations, and comparison with 3D motion capture.                                                                         |
| Should it be reread carefully? | Yes    | Reread the Methods, Table 1, Table 2, and Discussion when writing the PosePro validation plan.                                                                                                                 |
| One-sentence summary           | NA     | Low-cost tablet videos plus OpenPose can estimate several clinically relevant gait parameters in neurological populations, but accuracy depends strongly on camera view, parameter type, and clinical context. |

  


  

