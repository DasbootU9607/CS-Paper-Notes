---
title: "VisionMD-Gait: scalable clinical gait assessment from smartphone videos"
authors: Shuyu Liu, Alvin Wong, Si Chen, Patrick J. Antonelli & Diego L. Guarín
journal: Scientific Reports
year: "2026"
doi: https://doi.org/10.1038/s41598-025-34912-5
priority: High
status: Read
---
# VisionMD-Gait: scalable clinical gait assessment from smartphone videos

  

## 1. Overview

  

| Item               | Notes                                                                                                                                                                                 |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Relevance          | High                                                                                                                                                                                  |
| Main use           | Reference standard / Parameter selection / Error metrics / Video acquisition / Robustness analysis / Limitations discussion                                                           |
| One-sentence value | VisionMD-Gait represents a step towards the democratization of quantitative gait analysis for clinicians and researchers seeking accessible, cost-effective, mobile health solutions. |

  

## 2. Study Design

  

| Item                       | Notes                                                                                                                                                                                                                                                 |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Participants / sample size | 24 healthy adults and 10 adults with vestibular dizziness.<br>After outlier removal, the analysis included 269 total laps on an 8-meter walkway: 187 laps from healthy controls and 77 laps from participants with dizziness.                         |
| Population type            | Healthy adults and ambulatory vestibular-clinic patients with dizziness. Dizziness participants had BPPV or symptoms consistent with vestibular dizziness; participants with major neurological or neuromuscular causes of imbalance were excluded.   |
| Walking task               | Participants walked along an 8-meter clinical hallway at a comfortable self-selected speed, turned at the end, and completed at least four laps. (The analysis excluded turning events and retained only straight walking segments)                   |
| Tested system              | VisionMD-Gait: an open-source smartphone-video gait analysis platform.<br>It uses subject selection, segment selection, monocular 3D pose estimation, a gait transformer model, and feature extraction to compute spatiotemporal gait parameters.     |
| Reference / ground truth   | Noraxon Ultium Motion IMU-based wearable 3D motion capture system, with sensors placed bilaterally on the feet, shanks, thighs, and one sensor on the lower back.                                                                                     |
| Video / acquisition setup  | Single frontal-view smartphone video recorded with an iPhone 12 at 60 fps and 1080 x 1920 resolution. The phone was mounted on a tripod behind the participant at a distance sufficient to capture the full body in a real vestibular clinic hallway. |
| Comparison approach        | Video-derived parameters were compared with wearable-sensor-derived parameters. The same gait events and walking segments were aligned between modalities. Accuracy was evaluated separately in the healthy and dizziness groups.                     |

  

## 3. Tested Parameters

  

| Parameter                | Covered? | Notes / results                                                                                                                                                                                                |
| ------------------------ | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Gait speed               | Yes      | Strong correlation with sensor measures in both groups. MAE% was 7.24% in healthy controls and 9.21% in the dizziness group.                                                                                   |
| Step length              | Yes      | Covered as average left/right step length along the depth axis. It had larger relative error than most temporal parameters: 7.51% in healthy controls and 9.68% in the dizziness group.                        |
| Step width               | No       |                                                                                                                                                                                                                |
| Cadence                  | Yes      | Very high agreement with sensors. MAE% was below 1% in both groups, and Pearson r was 1.00.                                                                                                                    |
| Step time / support time | Yes      | Step duration, stride duration, stance time, swing time, and double support time were validated. Step and stride duration had MAE% below 1%; double support time had larger MAE% but remained below 10%.       |
| Joint angles             | Partly   | The pipeline estimates lower-limb joint kinematics internally through a gait transformer model, but this paper primarily validates spatio-temporal gait parameters rather than reporting joint-angle accuracy. |
| Other parameters         | Yes      | The paper also compares clinical group differences, showing reduced gait speed and cadence and longer step, stride, stance, swing, and double support times in the dizziness group.                            |

  

## 4. Statistical Metrics

  

| Metric                 | Used? | Use / result                                                                                                                                                                                                  |
| ---------------------- | ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AE / MAE               | Yes   | Accuracy was quantified using MAE expressed as a percentage of the sensor-based estimate. All reported average MAE% values were below 10%.                                                                    |
| MAPE / MAE%            | Yes   | MAE% was the main error metric. Temporal parameters such as cadence, step duration, and stride duration showed very low MAE%; double support time, step length, and gait speed showed larger relative errors. |
| RMSE                   | No    |                                                                                                                                                                                                               |
| Bias / mean difference | Yes   | Bias was assessed through Bland-Altman analysis. Mean differences were reported as close to zero, suggesting no major systematic over- or under-estimation.                                                   |
| ICC                    | No    |                                                                                                                                                                                                               |
| Bland-Altman / LoA     | Yes   | Bland-Altman plots in the supplementary material showed narrow and symmetric 95% limits of agreement. Spatial parameters, especially step length, had slightly wider limits.                                  |
| Pearson r              | Yes   | Pearson correlation was used to assess agreement. Correlations ranged from 0.76 to 1.00 in healthy controls and from 0.70 to 1.00 in the dizziness group.                                                     |
| SEM / MDC              | No    |                                                                                                                                                                                                               |

  

## 5. Key Results

  

- VisionMD-Gait showed strong agreement with the Noraxon wearable system for gait speed, cadence, step duration, stride duration, stance time, swing time, double support time, and step length.

- Temporal parameters performed especially well. Cadence, step duration, and stride duration had MAE% below 1% in both healthy controls and participants with dizziness.

- Spatial and more complex phase-related parameters had larger errors. Gait speed, step length, and double support time had the highest relative errors, although all remained below 10%.

- Bland-Altman analysis showed bias close to zero and no clear proportional bias, supporting agreement between video-based and sensor-based estimates.

- The system detected clinically meaningful group differences: participants with dizziness had slower gait speed, lower cadence, longer step and stride duration, longer stance and swing time, and longer double support time.

- Step length was lower in the dizziness group than in healthy controls, but this difference was not statistically significant after correction and residual checks were weaker for this parameter.

  

## 6. Limitations and Risk Warnings

  

- The validation sample was small, especially for the dizziness group, and the clinical population was limited to vestibular dizziness rather than broader neurological, orthopedic, or rehabilitation populations.

- The analysis excluded turning events and focused only on straight walking segments.

- Slight inaccuracies may occur under poor lighting or occlusion.

- Step length and double support time had larger relative errors than cadence and step duration, so spatial and phase-related parameters should be interpreted more cautiously.

- Step width and joint-angle accuracy were not directly validated as primary outputs.



## 7. Implications

  

| Aspect                     | Implication                                                                                                                                                                                                                                    |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Reference standard         | Wearable IMU systems can serve as a practical reference system when optical motion capture or pressure walkways are unavailable. (Validity still needs to be justified)                                                                        |
| Parameter selection        | We should prioritize gait speed, cadence, step duration, stride duration, stance time, swing time, double support time, and step length if comparable reference labels are available. Step width and joint angles require separate evidence.   |
| Error metrics              | MAE%, Pearson correlation, mean bias, and Bland-Altman limits of agreement are useful for reporting accuracy.                                                                                                                                  |
| Video usability assessment | The video checklist should include full-body visibility, straight walking availability, lighting quality, occlusion, frame rate, resolution, camera position, and whether turns can be excluded or segmented.                                  |
| Robustness grouping        | We should analyze errors by lighting, occlusion, video quality, walking direction/segment type, patient group, and parameter type. Straight walking and turning should be separated.                                                           |
| Report discussion          | The report should state that smartphone frontal-view video can provide clinically useful spatiotemporal gait parameters, but accuracy is parameter-dependent and does not automatically extend to step width, turning, or joint-angle outputs. |

  

## 8. Final Judgment

  

| Question                       | Yes/No | Judgment                                                                                                                                                                                                                                                                                 |
| ------------------------------ | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Core paper?                    | Yes    | NA                                                                                                                                                                                                                                                                                       |
| Should it be cited?            | Yes    | NA                                                                                                                                                                                                                                                                                       |
| Should it be reread carefully? | Yes    | Especially the Methods, Tables 1-3, and Discussion.                                                                                                                                                                                                                                      |
| One-sentence summary           | NA     | VisionMD-Gait shows that a single frontal-view smartphone video can estimate several clinically relevant spatiotemporal gait parameters with strong agreement against wearable sensors, but the evidence is strongest for straight walking and basic temporal/spatiotemporal parameters. |
