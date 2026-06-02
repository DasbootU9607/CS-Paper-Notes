---
title: Improving Gait Analysis Techniques with Markerless Pose Estimation Based on Smartphone Location
authors: Yang J, Park K
journal: Bioengineering
year: 2024
doi: 10.3390/bioengineering11020141
last_updated: 2026-06-02
github_user: DasbootU9607
priority: High
status: Read
---

  

# Improving Gait Analysis Techniques with Markerless Pose Estimation Based on Smartphone Location

  

## 1. Overview

  

| Item               | Notes                                                                                                                                                       |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Relevance          | High                                                                                                                                                        |
| Main use           | Video acquisition; robustness analysis; limitations discussion; parameter selection                                                                         |
| One-sentence value | This paper shows that smartphone camera location affects markerless pose-estimation accuracy in gait analysis, especially for lower-extremity joint angles. |

  

## 2. Study Design

  

| Item                       | Notes                                                                                                                                                                        |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Participants / sample size | 20 healthy volunteers: 10 males and 10 females; age 24.15 +/- 1.8 years; height 169.4 +/- 8.3 cm; mass 64.93 +/- 15.3 kg.                                                    |
| Population type            | Healthy young adults; no serious musculoskeletal injury, neurological disorder, fracture, or surgery history.                                                                |
| Walking task               | Treadmill walking at each participant's preferred speed. Participants first adapted to treadmill walking for 3 min, rested for 5 min, then walked for 1 min.                 |
| Tested system              | Smartphone video processed with customized HPE based on MediaPipe / BlazePose. The analysis used 2D x-y coordinates for shoulder, hip, knee, ankle, toe, and heel landmarks. |
| Reference / ground truth   | Marker-based motion capture system: OptiTrack Prime 41 with nine cameras, 120 fps, and 39 reflective markers.                                                                |
| Video / acquisition setup  | Five Samsung Galaxy S22 smartphones, 2340 x 1080 pixels, 30 fps. Cameras were placed 3 m from the subject and 0.8 m high at five side/diagonal positions.                    |
| Comparison approach        | Hip, knee, and ankle joint angles from HPE were compared with marker-based motion capture. The study examined how smartphone position affected MAE and correlation.          |

  

## 3. Tested Parameters

  

| Parameter                | Covered? | Notes / results                                                                                                                        |
| ------------------------ | -------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Gait speed               | No       |                                                                                                                                        |
| Step length              | No       |                                                                                                                                        |
| Step width               | No       |                                                                                                                                        |
| Cadence                  | No       |                                                                                                                                        |
| Step time / support time | No       |                                                                                                                                        |
| Joint angles             | Yes      | Main outcome. Hip, knee, and ankle flexion-extension angles were calculated from 2D HPE and compared with marker-based motion capture. |
| Other parameters         | No       | The paper focused on lower-extremity joint angles and smartphone camera position.                                                      |

  

## 4. Statistical Metrics

  

| Metric                 | Used? | Use / result                                                                                                                                                                         |
| ---------------------- | ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| AE / MAE               | Yes   | Main error metric. Most lower-extremity joint-angle MAEs were below 5 degrees. Overall MAE was about 2.35 degrees for hip, 2.82 degrees for knee, and 3.06 degrees for ankle.        |
| MAPE / MAE%            | No    |                                                                                                                                                                                      |
| RMSE                   | No    |                                                                                                                                                                                      |
| Bias / mean difference | No    |                                                                                                                                                                                      |
| ICC                    | No    |                                                                                                                                                                                      |
| Bland-Altman / LoA     | No    |                                                                                                                                                                                      |
| Pearson r              | Yes   | Used to assess association between HPE and marker-based motion capture joint angles. Hip and knee correlations were high; ankle correlations were lower and more position-dependent. |
| SEM / MDC              | No    |                                                                                                                                                                                      |

  

## 5. Key Results

  

- Most participants showed MAE below 5 degrees between HPE and motion capture for hip, knee, and ankle joint angles.

- Hip angle: lowest MAE was 1.92 +/- 0.41 degrees and high correlation was 0.97 +/- 0.015 at P2.

- Knee angle: lowest MAE was 2.4 +/- 0.66 degrees and highest correlation was 0.98 +/- 0.014 at P2.

- Ankle angle: lowest MAE was 2.29 +/- 0.5 degrees and highest correlation was 0.84 +/- 0.081 at P3.

- The paper concludes that hip and knee joint angles were accurately measured at the front diagonal position, while ankle angle was more accurately measured at the lateral side.

- Left-side joint-angle results were more reliable than right-side results because the smartphones were positioned on the subject's left side and the right leg was more often occluded.

- The right ankle was the weakest case. At P5, right ankle correlation was 0.45 +/- 0.149, likely because toe detection was obscured or inaccurate.

  

## 6. Limitations and Risk Warnings

  

- The study used healthy young adults, not older adults or clinical gait-impaired populations.

- The walking task was treadmill walking, not overground walking or hospital corridor walking.

- The analysis focused on 2D flexion-extension joint angles. Other joint motions and other planes were not explored.

- The study did not validate temporal-spatial variables such as gait speed, step length, step width, cadence, or step time.

- A 5-degree error may be acceptable for general gait analysis, but may be non-negligible when high kinematic precision is required.

- HPE accuracy can be affected by lighting, ambient light intensity, clothing texture/color, frame rate, and smartphone camera performance.

- Ankle angle estimation needs caution because it depends on accurate toe detection, which is vulnerable to occlusion, footwear, and leg crossover.

  

## 7. Implications

  

| Aspect                     | Implication                                                                                                                                                            |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Reference standard         | Marker-based OptiTrack can serve as a strong reference system for joint-angle validation.                                                                              |
| Parameter selection        | This paper supports validating joint angles separately from basic gait parameters. Hip/knee may be lower risk than ankle, but all joint angles need direct validation. |
| Error metrics              | We should report MAE in degrees and Pearson correlation for joint angles; a single correlation value is insufficient.                                                  |
| Video usability assessment | We should record smartphone/camera position, angle, distance, height, full-body visibility, side of camera, occlusion, clothing, lighting, frame rate, and resolution. |
| Robustness grouping        | Strong support for grouping results by camera location and by left/right side, especially when one side is closer to the camera.                                       |
| Report discussion          | Cite this paper to argue that camera placement is a methodological variable, not a minor technical detail.                                                             |

  

## 8. Final Judgment

  

| Question                       | Yes/No | Judgment                                                                                                                                                                                                    |
| ------------------------------ | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Core paper?                    | Yes    | Core paper for video-acquisition rules and camera-position robustness.                                                                                                                                      |
| Should it be cited?            | Yes    | Especially useful when discussing smartphone camera placement and joint-angle accuracy.                                                                                                                     |
| Should it be reread carefully? | Yes    | Reread Data Collection, Error Calculation and Statistics, Results, Limitations, and Conclusions before writing the video acquisition protocol.                                                              |
| One-sentence summary           | NA     | Smartphone-based HPE can estimate treadmill hip/knee/ankle angles with relatively low MAE, but accuracy depends on camera location and is weakest for ankle angles affected by toe detection and occlusion. |
