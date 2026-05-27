---
type: Literature Note
status: Read
title: ImageNet Classification with Deep Convolutional Neural Networks
authors: Alex Krizhevsky, Ilya Sutskever, Geoffrey E. Hinton
year: "2012"
venue: NIPS
doi:
url: https://proceedings.neurips.cc/paper/2012/hash/c399862d3b9d6b76c8436e924a68c45b-Abstract.html
zotero:
pdf: https://papers.nips.cc/paper_files/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf
code: https://github.com/computerhistory/AlexNet-Source-Code
tags:
  - Paper
  - Computer-Vision
  - Deep-Learning
  - NIPS
aliases:
  - AlexNet
---

# ImageNet Classification with Deep Convolutional Neural Networks

## Citation

> Krizhevsky, A., Sutskever, I., & Hinton, G. E. (2012). ImageNet classification with deep convolutional neural networks. _Advances in neural information processing systems_, _25_.

## TL;DR

The paper introduces **AlexNet**, which won the **2012 ImageNet LSVRC competition** by a significant margin. It is widely considered a **landmark in the history of deep learning**, demonstrating that a deep Convolutional Neural Network (CNN) trained on **GPUs** could achieve state-of-the-art results on large-scale image classification tasks. The paper popularized key techniques such as the use of **ReLU activation functions**, **Dropout** for regularization, and **heavy data augmentation**.

> This paper proposes a **large-scale deep CNN**, namely AlexNet, trained on **2 GPUs** to address the challenge of **large-scale image classification** on the ImageNet ILSVRC-2010 and ILSVRC-2012 datasets. The paper shows that deep CNNs can substantially outperform traditional computer vision pipelines when trained on sufficient data and computational resources.

Core takeaway:

- **Problem:** large-scale **1000-class ImageNet classification**.
- **Method:** train a deep CNN **end-to-end from raw RGB pixels** using GPUs.
- **Result:** much lower **top-5 error** than hand-crafted feature pipelines.
- **Historical significance:** helped establish **deep CNNs** as the dominant approach for large-scale computer vision.

## Reading Context

Why am I reading this paper?

- [x] Foundational paper
- [ ] Related work
- [x] Method I may use
- [ ] Course / seminar
- [x] Survey / background
- [ ] Reproducing results
- [ ] Other:

Reading goal:

> I want to understand the significance of AlexNet in the area of deep learning, the architectural design, and training process of AlexNet. I also want to cultivate my abilities in reading research papers as this is the first paper I read.

## Research Question

**What problem is the paper trying to solve?**

- The paper aims to solve the problem of **large-scale image classification**: classifying about **1.2 million ImageNet training images** into **1000 categories**, using only simple preprocessing such as resizing, cropping, and mean subtraction.

**Why is this problem important?**

- **Large-scale image classification** is a fundamental benchmark for visual recognition.
- Solving this problem requires learning **robust and general visual representations** from complex natural images.

**What gap in prior work does it identify?**

- Previous computer vision systems relied heavily on **hand-crafted features**, such as SIFT, HOG, or engineered pipelines.
- Earlier neural networks were usually smaller and trained on smaller datasets, so they had not clearly demonstrated superiority on large-scale visual recognition.

## Main Contribution

**What are the main contributions claimed by the authors?**

1. They trained **one of the largest convolutional neural networks to date** on the subsets of ImageNet used in the ILSVRC-2010 and ILSVRC-2012 competitions [2] and achieved by far the best results ever reported on these datasets.
2. They wrote a **highly-optimized GPU implementation** of 2D convolution and all the other operations inherent in training convolutional neural networks.
3. They introduced and combined several important techniques, including **ReLU activation**, **data augmentation**, **Dropout**, **overlapping pooling**, and **local response normalization**.

**My interpretation of the real contribution:**

> The paper demonstrated that **deep learning can scale to large real-world vision problems** and outperform traditional **hand-crafted feature methods**.

## Key Idea

**What is the core idea?**

> To train a **large convolutional neural network directly on large-scale image data**, so that the network can learn **hierarchical visual representations from pixels** instead of relying on manually designed features.

**What is the main insight?**

- Visual recognition can be treated as a **representation learning problem**: if the model is deep enough and trained on enough labeled data, useful visual features can be learned automatically.
- CNNs are well suited for images because they exploit local spatial structure through **convolution**, **weight sharing**, and **pooling**.
- Scaling up **model size**, **data size**, and **computation** can significantly improve performance.

**Why should this idea work?**

- Convolutional layers can capture the local patterns of images (such as edges, corners, textures, and object parts) efficiently.
- Deep layers can compose simple low-level patterns into more abstract high-level object representations.
- **Weight sharing** reduces the number of parameters compared with fully connected networks, making learning from images more feasible.
- Large-scale supervised data provides enough examples for the model to learn general visual features.
- **Regularization and augmentation** help prevent the large model from overfitting.

## Method

**High-level method:**

1. Use ImageNet images as input **without hand-crafted feature extraction**.
2. Apply simple image preprocessing and **data augmentation**, such as resizing, cropping, flipping, mean subtraction, and color perturbation. These help enlarge the effective training set.
3. Train a deep CNN **end-to-end from pixel values to 1000-class predictions**.

**Important details:**

| Aspect | Details |
| --- | --- |
| Model / algorithm | **Supervised deep CNN** trained with backpropagation and stochastic gradient descent. |
| Architecture | **8 learned layers:** 5 convolutional layers and 3 fully connected layers. |
| Output | **1000-way softmax classifier.** |
| Dataset | ImageNet ILSVRC-2010 and ILSVRC-2012, with around 1.2 million training images and 1000 object categories. |
| Computation | Training distributed across **two NVIDIA GTX 580 GPUs** with **3GB memory each**. |
| Assumption | Large labeled datasets plus enough computation allow deep CNNs to learn useful visual representations. |

**Training setup:**

| Hyperparameter | Value |
| --- | --- |
| Mini-batch size | **128** |
| Momentum | **0.9** |
| Weight decay | **0.0005** |
| Initial learning rate | **0.01** |
| Learning-rate schedule | Divide by 10 when validation error stops improving; reduced three times. |
| Training duration | Roughly **90 epochs**, taking **5 to 6 days** on two GTX 580 GPUs. |

**Pseudo-code or mathematical formulation, if important:**

```text
Input: ImageNet training images and labels

for each training iteration:
	sample a mini-batch of 128 images:
	apply data augmentation to avoid overfitting:
		- random 224*224 crops from 256*256 images
		- horizontal flips
		- color/intensity perturbations using PCA on RGB pixel values
	forward images through CNN:
		convolution -> ReLU -> local response normalization / max pooling where used
		fully connected layers -> softmax
	compute classification loss
	backpropagate gradients
	update weights using SGD with momentum and weight decay

Output: trained CNN classifier for 1000 ImageNet classes

```

## Architecture

![[Pasted image 20260527151014.png]]

**Layer overview:**

| Stage | Configuration | Notes |
| --- | --- | --- |
| Input | **224 × 224 × 3 RGB patch** | Cropped from 256 × 256 images. |
| Conv1 | **96 filters, 11 × 11 × 3, stride 4** | Followed by ReLU, local response normalization, and max pooling. |
| Conv2 | **256 filters, 5 × 5 × 48** | Followed by ReLU, local response normalization, and max pooling. |
| Conv3 | 384 filters, 3 × 3 × 256 | No pooling or normalization before Conv4. |
| Conv4 | 384 filters, 3 × 3 × 192 | Connected only within the same GPU partition. |
| Conv5 | 256 filters, 3 × 3 × 192 | Followed by max pooling. |
| FC6 | **4096 neurons** | Dropout applied. |
| FC7 | **4096 neurons** | Dropout applied. |
| FC8 | **1000-way softmax** | Produces class probabilities. |

**Key architectural choices:**

- **Depth:** **five convolutional layers plus three fully connected layers**.
- **Nonlinearity:** ReLU is applied after every convolutional and fully connected layer.
- **Regularization:** data augmentation and Dropout are used to reduce overfitting.
- **Two-GPU split:** some layers communicate across GPUs, while others are restricted to the same GPU partition.
- **Pooling:** overlapping max pooling is used with neighborhood size 3 × 3 and stride 2.

## Experiments / Evaluation

**What is being evaluated?**

- Whether a large supervised CNN can achieve state-of-the-art performance on large-scale ImageNet classification.
- Whether architectural and regularization choices such as ReLU, local response normalization, overlapping pooling, data augmentation, Dropout, and two-GPU training improve performance.

**Datasets:**

| Dataset | Scale | Role in the paper |
| --- | --- | --- |
| ILSVRC-2010 | About **1.2M training images**, **50K validation images**, **150K test images**, **1000 classes** | Main dataset for most experiments because test labels were available. |
| ILSVRC-2012 | 1000-class ImageNet challenge setting | Used for the competition submission; test labels were not publicly available. |
| ImageNet Fall 2009 | **8.9M images**, **10,184 categories** | Additional large-scale evaluation. |

**Baselines:**

| Baseline | Dataset | Result |
| --- | --- | --- |
| Sparse coding | ILSVRC-2010 | **47.1% top-1 error**, **28.2% top-5 error** |
| SIFT + Fisher Vectors | ILSVRC-2010 | **45.7% top-1 error**, **25.7% top-5 error** |
| Fisher Vector based second-best entry | ILSVRC-2012 | **26.2% top-5 test error** |

**Metrics:**

- **Top-1 error:** the correct label is not the model's most probable prediction.
- **Top-5 error:** the correct label is not among the model's five most probable predictions.

**Main results:**

| Model / setting | Top-1 error | Top-5 error | Notes |
| --- | --- | --- | --- |
| AlexNet on ILSVRC-2010 test set | **37.5%** | **17.0%** | Main single-model result. |
| 1 CNN on ILSVRC-2012 validation set | **40.7%** | **18.2%** | Single CNN reported in Table 2. |
| 7 CNNs with ImageNet Fall 2011 pretraining | **36.7% validation** | **15.4% validation / 15.3% test** | **Winning ILSVRC-2012 submission.** |
| Variant on ImageNet Fall 2009 | 67.4% | 40.9% | Uses an extra sixth convolutional layer. |

**Ablation studies:**

| Component | Reported effect |
| --- | --- |
| ReLU | Trained **much faster** than comparable saturating nonlinearities such as tanh. |
| Two-GPU training | Reduced top-1 and top-5 error by **1.7** and **1.2** percentage points compared with a smaller one-GPU network. |
| Local response normalization | Reduced top-1 and top-5 error by **1.4** and **1.2** percentage points. |
| Overlapping pooling | Reduced top-1 and top-5 error by **0.4** and **0.3** percentage points. |
| PCA-based color augmentation | Reduced top-1 error by **over 1 percentage point**. |
| Network depth | Removing any convolutional layer degraded performance; removing middle layers caused about a 2 percentage point top-1 loss. |

**Does the evidence support the claim?**

- Yes. The reported results clearly outperform the strongest hand-crafted feature baselines on ILSVRC-2010 and **won ILSVRC-2012 by a large margin in top-5 test error**.

## Strengths

- The paper demonstrates that **deep CNNs can scale to million-image supervised learning** and outperform hand-crafted visual recognition pipelines.
- The experimental comparison is strong for its time because it uses the major ImageNet benchmark.
- The paper combines several practical techniques into one working system: GPU training, ReLU, data augmentation, Dropout, local response normalization, and overlapping pooling.
- The architecture and training details are concrete enough to become a reusable reference point for later CNN work.

## Weaknesses / Limitations

**Limitations stated by the authors:**

- The network size was limited mainly by **available GPU memory** and acceptable training time.
- The model still overfit substantially without **data augmentation** and **Dropout**, despite the large dataset.
- The authors expected that larger networks, more computation, more data, unsupervised pretraining, and video data could further improve results.

**Limitations I noticed:**

- The architecture is tied to a specific **2-GPU partitioning scheme**, so reproducing it on a single GPU or a different multi-GPU setup requires modification.
- The model is computationally expensive for its time: roughly 5 to 6 days of training on two GTX 580 GPUs.
- The final competition result uses model averaging / ensembling, which improves accuracy but increases inference and training cost.

**Threats to validity:**

- The strongest ILSVRC-2012 test results come from submitted models and ensembles, while test labels were not publicly available for all variants.
- The results are centered on ImageNet classification, so they do not directly prove performance on other vision tasks such as detection, segmentation, or fine-grained recognition.

## Connections

**Related papers:**

- [[ImageNet: A Large-Scale Hierarchical Image Database]]
- [[Gradient-Based Learning Applied to Document Recognition]]
- [[Rectified Linear Units Improve Restricted Boltzmann Machines]]
- [[Improving Neural Networks by Preventing Co-adaptation of Feature Detectors]]

**Related concepts:**

- [[Convolutional Neural Network]]
- [[ReLU]]
- [[Dropout]]
- [[Data Augmentation]]
- [[ImageNet]]
- [[Top-5 Error]]
- [[Stochastic Gradient Descent]]

**This paper builds on:**

- Earlier CNN work such as LeNet, GPU-based neural network training, ImageNet as a large labeled dataset, and recent work on ReLU and Dropout.

**This paper is similar to:**

- Later CNN classification papers such as [[VGGNet]], [[GoogLeNet]], and [[ResNet]] in the sense that they also scale CNNs on ImageNet.

**This paper differs from:**

- Hand-crafted feature pipelines such as SIFT + Fisher Vectors because it learns features directly from pixels end-to-end.

## Useful Quotes / Notes

**Important excerpts from the paper:**

- The authors emphasize that the model uses **60 million parameters** and **650,000 neurons**.
- The paper reports **37.5% top-1** and **17.0% top-5** error on ILSVRC-2010.
- The ILSVRC-2012 winning system achieved **15.3% top-5 test error**, compared with **26.2%** for the second-best entry.
- Local response normalization is described as closer to brightness normalization than contrast normalization because it does not subtract mean activity.

**My comments:**

- This paper is important not because every architectural choice remained standard, but because it proved that deep supervised CNNs plus enough data and GPU computation could dominate large-scale vision benchmarks.
- Some details, such as local response normalization and the exact 2-GPU split, are historically important but less common in modern CNN architectures.
- The paper is a good example of how engineering details, data scale, and model architecture can matter together.

## How I Might Use This

**Could this paper be useful for my future work?**

- [x]  Background / related work
- [x]  Method reference
- [x]  Experimental baseline
- [x]  Dataset / benchmark
- [ ]  Theoretical idea
- [ ]  Not useful for now

**Possible use:**

- Use it as a historical and technical reference when explaining the rise of deep learning in computer vision.
- Use its architecture, training setup, and ImageNet results as a baseline when studying later CNNs such as VGG, GoogLeNet, and ResNet.
- Use the paper to understand practical regularization methods for large neural networks: data augmentation, Dropout, and weight decay.

## Further Investigation

- Saturating nonlinearities and non-saturating nonlinearity (V. Nair and G. E. Hinton. Rectified linear units improve restricted boltzmann machines. In Proc. 27th International Conference on Machine Learning, 2010.)
- Dropout (G.E. Hinton, N. Srivastava, A. Krizhevsky, I. Sutskever, and R.R. Salakhutdinov. Improving neural networks by preventing co-adaptation of feature detectors. arXiv preprint arXiv:1207.0580, 2012.)
- Momentum
- PCA
