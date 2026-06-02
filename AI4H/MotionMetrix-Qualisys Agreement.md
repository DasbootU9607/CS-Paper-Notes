---
title: Level of Agreement between the MotionMetrix System and an Optoelectronic Motion Capture System for Walking and Running Gait Measurements
authors: Jaen-Carrillo D, Garcia-Pinillos F, Chicano-Gutierrez JM, Perez-Castilla A, Soto-Hermoso V, Molina-Molina A, Ruiz-Alias SA
journal: Sensors
year: 2023
doi: https://doi.org/10.3390/s23104576
last_updated: 2026-06-02
github_user: DasbootU9607
priority: High
status: Read
---

  

# Level of Agreement between the MotionMetrix System and an Optoelectronic Motion Capture System for Walking and Running Gait Measurements

  

## 1. Overview

  

| Item               | Notes                                                                                                                                                  |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Relevance          | High                                                                                                                                                   |
| Main use           | Reference standard; parameter selection; error metrics; limitations discussion                                                                         |
| One-sentence value | This paper directly compares MotionMetrix markerless software with Qualisys 3D MCS and shows that agreement is strongly variable- and speed-dependent. |

  

## 2. Study Design

  

| Item                       | Notes                                                                                                                                                                                                                       |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Participants / sample size | 24 recreationally active young adults: 16 men and 8 women; age 22.7 +/- 2.6 years; height 1.72 +/- 0.10 m; body mass 69.1 +/- 11.7 kg.                                                                                      |
| Population type            | (1) Healthy, active young adults; <br>(2) Familiar with treadmill running; <br>(3) Free from injuries and health problems.                                                                                                  |
| Walking task               | Treadmill protocol in one session: walking at 5 km/h, running at 10 km/h, and running at 15 km/h. Each speed lasted 1 min; last 30 s were analyzed.                                                                         |
| Tested system              | MotionMetrix marker-less system with two Microsoft Kinect v1 sensors on both sides of the treadmill. Kinect tracked 20 body joints in 3D at 30 Hz; up to 60 Hz when both sensors tracked the same point.                    |
| Reference / ground truth   | Qualisys 3D optoelectronic motion capture system with eight Oqus cameras at 250 Hz. The paper treats Qualisys as the gold standard / measure of reference.                                                                  |
| Video / acquisition setup  | Laboratory treadmill setup. MotionMetrix followed manufacturer instructions: calibration, fitted clothing, no reflective/shiny fabric, secured shoelaces, hair tucked away, no direct sunlight, and unobstructed body view. |
| Comparison approach        | MotionMetrix outputs were compared with Qualisys outputs using pairwise mean comparison, bias, Pearson r, SEE, and ICC.                                                                                                     |

  

## 3. Tested Parameters

  

| Parameter                | Covered?            | Notes / results                                                                                                                                                                                         |
| ------------------------ | ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Gait speed               | Fixed speed         | Speed was controlled by treadmill: 5, 10, and 15 km/h. Gait speed itself was not validated as an estimated output.                                                                                      |
| Step length              | Yes                 | At 5 km/h, unilateral step length had significant bias, but stride length showed good agreement: r = 0.713, ICC = 0.817.                                                                                |
| Step width               | Yes                 | Consistently poor. At 5 km/h, MotionMetrix step width was 0.16 m vs Qualisys 0.01 m; r = -0.006, ICC = 0.000. At 10 and 15 km/h, agreement also remained poor.                                          |
| Cadence                  | Yes                 | Best walking result. At 5 km/h, cadence was 114.4 spm vs 114.5 spm; r = 0.994, ICC = 0.997.                                                                                                             |
| Step time / support time | Yes                 | Step time left at 5 km/h showed excellent agreement: r = 0.920, ICC = 0.960. Stance, swing, load response, pre-swing, and double support had low ICCs despite small time bias.                          |
| Joint angles             | Yes, mainly running | Knee flexion, thigh flexion/extension, and spine angle were tested in running. Agreement was mixed; swing knee flexion at 15 km/h was relatively strong, but thigh and spine variables were often poor. |
| Other parameters         | Yes                 | Stride time, stride rate, stride length, contact time, vertical displacement, landing/stance/swing knee flexion, thigh flexion/extension, and spine angle.                                              |

  

## 4. Statistical Metrics

  

| Metric                 | Used? | Use / result                                                                                                                                          |
| ---------------------- | ----- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| AE / MAE               | No    |                                                                                                                                                       |
| MAPE / MAE%            | No    |                                                                                                                                                       |
| RMSE                   | No    |                                                                                                                                                       |
| Bias / mean difference | Yes   | Pairwise mean comparison and systematic bias were reported. Walking phase variables had small time bias, but several were statistically different.    |
| ICC                    | Yes   | ICC [2,1], two-way random-effects model, single measurement, absolute agreement. Interpretation followed Koo and Li: poor, moderate, good, excellent. |
| Bland-Altman / LoA     | No    |                                                                                                                                                       |
| Pearson r              | Yes   | Used to assess level of agreement. Hopkins criteria were used: trivial to almost perfect.                                                             |
| SEM / MDC              | No    |                                                                                                                                                       |
| SEE                    | Yes   | Standard error of the estimate from linear regression analysis was reported for each variable.                                                        |

  

## 5. Key Results

  

- The main conclusion is parameter-specific: some variables showed high agreement, while others showed poor agreement.

- Walking at 5 km/h: cadence and left step time had excellent ICCs; stride length had good ICC; step width had essentially no agreement.

- MotionMetrix underestimated stance and swing phases, as well as load response and pre-swing phases, at 5 km/h.

- Running at 10 km/h: stride time, stride rate, and stride length showed good agreement; contact time and step width showed poor agreement.

- Running at 15 km/h: stride time, stride rate, and stride length showed almost perfect agreement; vertical displacement and swing knee flexion were acceptable; many other angle variables were weak.

- Step width is the clearest warning variable. The discussion explicitly notes poor reliability for MotionMetrix step-width measurements compared with Qualisys.

- The paper supports a cautious wording: MotionMetrix is promising for selected gait variables in the tested contexts, but not globally accurate for all outputs.

  

## 6. Limitations and Risk Warnings

  

- The sample was limited to healthy, active young adults. 

- The protocol was treadmill-based. It does not directly validate overground walking, turns, start/stop phases, home videos, or hospital corridor videos.

- The setup used two Kinect sensors and controlled laboratory conditions, not a single smartphone or ordinary clinical camera.

- Step width was unreliable, even under controlled conditions.

- Joint angle validity was mixed. Knee flexion was better than thigh/spine variables in some running conditions, but the results do not justify broad confidence in all kinematic outputs.

- Video quality restrictions matter: clothing, reflections, sunlight, hair, shoelaces, and blocked view were controlled according to manufacturer guidance.

  

## 7. Implications

  

| Aspect                     | Implication                                                                                                                                                              |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Reference standard         | Qualisys-style optoelectronic MCS is a strong comparator. PosePro should clearly define whether its comparator is a true gold standard or only a reference label.        |
| Parameter selection        | Prioritize cadence, step/stride time, stride length, and basic temporal-spatial parameters. Treat step width, contact time, double support, and joint angles separately. |
| Error metrics              | Use bias, Pearson r, ICC with confidence intervals, and SEE/MAE-style error metrics. Do not rely on correlation alone.                                                   |
| Video usability assessment | Record full-body visibility, camera view, clothing, reflection, sunlight/lighting, occlusion, frame rate, and whether shoes/hair or objects interfere with tracking.     |
| Robustness grouping        | Group results by parameter type, speed, camera setup, and video quality. Step width and angle variables need their own robustness checks.                                |
| Report discussion          | Cite this paper to argue that markerless gait validity is not a single yes/no claim; it varies by variable, locomotion speed, system setup, and context.                 |

  

## 8. Final Judgment

  

| Question                       | Yes/No | Judgment                                                                                                                                                                                                          |
| ------------------------------ | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Core paper?                    | Yes    | Core evidence for parameter-specific validation against a gold-standard motion capture system.                                                                                                                    |
| Should it be cited?            | Yes    | Especially useful for supporting ICC/bias/SEE reporting and warning against global accuracy claims.                                                                                                               |
| Should it be reread carefully? | Yes    | Reread Methods, Tables 1-3.                                                                                                                                                                                       |
| One-sentence summary           | NA     | MotionMetrix agreed well with Qualisys for cadence and stride-related measures, but agreement was poor for step width and mixed for phase/angle variables, so each output parameter must be validated separately. |
