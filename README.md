# CS Paper Notes

This repository collects my reading notes for computer science research papers. The notes are written in Markdown and organized for review in Obsidian or directly on GitHub.

## Repository Structure

| Folder | Description | Notes |
| --- | --- | --- |
| [AI4H](./AI4H/) | Papers and notes on artificial intelligence for healthcare, clinical analysis, and medical decision support. | Focused AI-for-health reading notes. |
| [Basics](./Basics/) | Foundational papers and core concepts in AI, ML, and computer vision. | Start here for classic papers. |
| [Templates](./Templates/) | Reusable templates for future literature notes, organized by module. | Use these to keep note format consistent. |

## Paper Notes

The note tables use short display names so the README stays readable on GitHub. Full original paper titles are preserved below each table.

### AI4H

| Note | Year | Status | Focus |
| --- | --- | --- | --- |
| [Clinical Gait Analysis](./AI4H/Clinical%20Gait%20Analysis.md) | 2024 | Read | Video-based pose estimation for clinical gait analysis. |
| [Monocular 3D Gait Assessment](./AI4H/Monocular%203D%20Gait%20Assessment%20via%20Deep%20Learning.md) | 2021 | Read | Monocular smartphone-video gait parameters validated against GAITRite. |
| [Spatiotemporal Gait Parameters](./AI4H/Spatiotemporal%20Gait%20Parameters.md) | 2020 | Read | Markerless gait parameters compared with OptoGait and high-speed video. |
| [VisionMD-Gait](./AI4H/VisonMD.md) | 2026 | Read | Smartphone-video clinical gait assessment. |

**Full paper titles**

- Clinical Gait Analysis: Clinical gait analysis using video-based pose estimation: Multiple perspectives, clinical populations, and measuring change.
- Monocular 3D Gait Assessment: Algorithm based on one monocular video delivers highly valid and reliable gait parameters.
- Spatiotemporal Gait Parameters: Agreement Between Spatiotemporal Gait Parameters Measured by a Markerless Motion Capture System and Two Reference Systems: a Treadmill-Based Photoelectric Cell and High-Speed Video Analyses: Comparative Study.
- VisionMD-Gait: VisionMD-Gait: scalable clinical gait assessment from smartphone videos.

### Basics

| Note | Year | Status | Focus |
| --- | --- | --- | --- |
| [AlexNet](./Basics/AlexNet.md) | 2012 | Read | Large-scale CNN image classification on ImageNet. |

**Full paper titles**

- AlexNet: ImageNet Classification with Deep Convolutional Neural Networks.

## Note Format

The current templates are organized by module:

- [AI4H Note Template](./Templates/AI4H%20Note%20Template.md)
- [Basics Paper Note Template](./Templates/Basics%20Paper%20Note%20Template.md)

## Reading Workflow

My paper-reading workflow follows Mu Li's three-pass paper reading method. I first skim the paper to understand the title, abstract, figures, and overall contribution. Then I read more carefully to understand the method, assumptions, experiments, and results. Finally, I revisit the paper in depth when I need to connect it to other work or write a more complete note.

I use Zotero for reading and annotation. Highlight colors have specific meanings:

- **Yellow:** ordinary important points, definitions, methods, or results.
- **Green:** parts I do not fully understand yet.
- **Red:** possible problems, weaknesses, limitations, or questionable claims.
- **Blue:** strengths, elegant ideas, or things the paper does especially well.

After reading, I use these highlights to fill in the note template, turning annotations into structured summaries, critiques, and follow-up questions.

## How To Use

- Browse notes by folder from the [Repository Structure](#repository-structure) section.
- Open individual paper notes from the [Paper Notes](#paper-notes) table.
- Create new notes from the module-specific templates in [Templates](./Templates/).
