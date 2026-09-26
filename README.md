# Awesome-Diffusion-Guidance [![Awesome](https://awesome.re/badge.svg)](https://github.com/sindresorhus/awesome)

**Welcome to the collection of research on diffusion guidance methods!**  
This repo curates cutting-edge papers on diffusion model guidance 🌟

Your stars fuel the updates! ⭐ This library is actively maintained, with new papers and features added regularly.

## Table of Contents

- [Papers by Topic](#papers-by-topic)
  - [Foundations & Theory of Diffusion Guidance](#1-foundations--theory-of-diffusion-guidance)
  - [CFG Correction & High-Guidance-Scale Methods](#2-cfg-correction--high-guidance-scale-methods)
  - [Adaptive, Scheduled & Efficient Guidance](#3-adaptive-scheduled--efficient-guidance)
  - [Self-, Attention- & Internal-Model Guidance](#4-self-attention--internal-model-guidance)
  - [External-Objective & General Conditional Guidance](#5-external-objective--general-conditional-guidance)
  - [Flow, Alternative Conditioning & Guidance-Free Methods](#6-flow-alternative-conditioning--guidance-free-methods)
- [How to Contribute](#how-to-contribute)
- [To Do](#to-do)

## Papers by Topic

Tags provide additional descriptors for cross-cutting research properties.

### 1. Foundations & Theory of Diffusion Guidance

Papers that study the foundations, distributions, and dynamics of diffusion guidance, including classifier guidance and classifier-free guidance.

- **[Diffusion Models Beat GANs on Image Synthesis](https://proceedings.neurips.cc/paper/2021/hash/49ad23d1ec9fa4bd8d77d02681df5cfa-Abstract.html)**  
  `2021.12` · `NeurIPS 2021` · [Code](https://github.com/openai/guided-diffusion)  
  **Tags:** `Classifier Guidance` · `Guidance Foundations`  
  Introduces classifier guidance using gradients to enhance sample quality in diffusion models, surpassing GANs on image synthesis.

- **[Classifier-Free Diffusion Guidance](https://openreview.net/forum?id=qw8AKxfYbI)**  
  `2021.12` · `NeurIPS 2021 Workshop`  
  **Tags:** `Classifier-Free Guidance` · `CFG Foundations`  
  Enables guidance without classifiers by jointly training on conditional and unconditional objectives.

- **[Characteristic Guidance: Non-linear Correction for Diffusion Model at Large Guidance Scale](https://proceedings.mlr.press/v235/zheng24f.html)**  
  `2023.12` · `ICML 2024` · [Code](https://github.com/scraed/CharacteristicGuidanceWebUI)  
  **Tags:** `CFG Theory` · `Fokker–Planck` · `High Guidance Scale`  
  Applies non-linear corrections based on Fokker-Plank equations to handle over-saturation artifact at large guidance scales in diffusion models.

- **[Theoretical Insights for Diffusion Guidance: A Case Study for Gaussian Mixture Models](https://arxiv.org/abs/2403.01639)**  
  `2024.03` · `ICML 2024`  
  **Tags:** `CFG Theory` · `Probabilistic Analysis` · `Gaussian Mixture Models`  
  Provide  theoretical study towards understanding the influence of guidance on diffusion models in the context of Gaussian mixture models.

- **[Inner Classifier-Free Guidance and Its Taylor Expansion for Diffusion Models](https://openreview.net/forum?id=0QAzIMq32X)**  
  `2024.04` · `TMLR`  
  **Tags:** `CFG Theory` · `CFG Alternative` · `Taylor Expansion`  
  This approach involves utilizing a single model to jointly optimize the conditional score predictor and unconditional score predictor, eliminating the need for additional classifiers. The inner classifier-free guidance (ICFG) provides an alternative perspective on the CFG method when the condition has a specific structure, demonstrating that CFG represents a first-order case of ICFG.

- **[REG: Rectified Gradient Guidance for Conditional Diffusion Models](https://arxiv.org/abs/2501.18865)**  
  `2025.01` · `ICML 2025`  
  **Tags:** `CFG Theory` · `CFG Correction` · `Generalized Guidance`  
  Proposes a rectified gradient guidance method that enhances conditional diffusion models by aligning practical implementations with a theoretically valid scaled joint distribution objective, improving performance over existing guidance techniques.

- **[Classifier-Free Guidance: From High-Dimensional Analysis to Generalized Guidance Forms](https://arxiv.org/abs/2502.07849)**  
  `2025.02` · `arXiv`  
  **Tags:** `CFG Theory` · `Probabilistic Analysis` · `Generalized Guidance`  
  Uniquely demonstrates that Classifier-Free Guidance accurately reproduces the target distribution in high and infinite dimensions, extending to a family of non-linear generalizations with improved robustness, sample fidelity, and diversity.

- **[Conditional Diffusion Models with Classifier-Free Gibbs-like Guidance](https://arxiv.org/abs/2505.21101)**  
  `2025.05` · `arXiv` · [Code](https://github.com/yazidjanati/cfgig)  
  **Tags:** `CFG Theory` · `Probabilistic Analysis` · `Diversity`  
  Samples tilted distributions with Rényi divergence for low-noise corrections, fixing CFG's diversity issues.

### 2. CFG Correction & High-Guidance-Scale Methods

Papers that correct, stabilize, or reinterpret classifier-free guidance, especially at high guidance scales.

- **[Characteristic Guidance: Non-linear Correction for Diffusion Model at Large Guidance Scale](https://proceedings.mlr.press/v235/zheng24f.html)**  
  `2023.12` · `ICML 2024` · [Code](https://github.com/scraed/CharacteristicGuidanceWebUI)  
  **Tags:** `CFG Theory` · `Fokker–Planck` · `High Guidance Scale`  
  Applies non-linear corrections based on Fokker-Plank equations to handle over-saturation artifact at large guidance scales in diffusion models.

- **[CFG++: Manifold-constrained Classifier Free Guidance for Diffusion Models](http://arxiv.org/abs/2406.08070)**  
  `2024.06` · `ICLR 2025` · [Code](https://cfgpp-diffusion.github.io/)  
  **Tags:** `CFG Correction` · `Manifold` · `High Guidance Scale`  
  Constrains guidance to data manifold using orthogonal projections for better sample quality and invertibility.

- **[Eliminating Oversaturation and Artifacts of High Guidance Scales in Diffusion Models](https://arxiv.org/pdf/2410.02416)**  
  `2024.10` · `ICLR 2025` · [Code](https://github.com/huggingface/diffusers/issues/9585#issuecomment-2774216484)  
  **Tags:** `CFG Correction` · `Geometry` · `High Guidance Scale`  
  Decompose the update term in CFG into parallel and orthogonal components with respect to the conditional model prediction and observe that the parallel component primarily causes oversaturation, while the orthogonal component enhances image quality.

- **[TCFG: Tangential Damping Classifier-free Guidance](https://arxiv.org/abs/2503.18137)**  
  `2025.03` · `CVPR 2025` · [Code](https://github.com/5410tiffany/tcfg.github.io)  
  **Tags:** `CFG Correction` · `Geometry` · `High Guidance Scale`  
  Geometrically filters tangential misalignments using SVD for better manifold alignment and quality with minimal overhead.

- **[Angle Domain Guidance: Latent Diffusion Requires Rotation Rather Than Extrapolation](https://arxiv.org/abs/2506.11039)**  
  `2025.06` · `ICML 2025` · [Code](https://github.com/jinc7461/ADG)  
  **Tags:** `CFG Correction` · `Geometry` · `High Guidance Scale`  
  Angle Domain Guidance (ADG) mitigates color distortions in text-to-image latent diffusion models by constraining magnitude variations and optimizing angular alignment, preserving enhanced text-image alignment at higher guidance weights.

- **[Guidance in the Frequency Domain Enables High-Fidelity Sampling at Low CFG Scales](https://openreview.net/forum?id=0cdXElXkk6)**  
  `2025.06` · `ICLR 2026` · [Code](https://github.com/sdtana/ComfyUI-FDG)  
  **Tags:** `CFG Correction` · `Frequency Domain` · `High Guidance Scale`  
  Analyzes CFG in the frequency domain and proposes frequency-decoupled guidance (FDG): separate scales on low- vs. high-frequency parts of the CFG update (structure and conditioning vs. detail), improving fidelity at low guidance while reducing high-CFG oversaturation and diversity loss.

- **[CFG-Ctrl: Control-Based Classifier-Free Diffusion Guidance](https://arxiv.org/abs/2603.03281)**  
  `2026.03` · `CVPR 2026` · [Code](https://github.com/THU-SI/CFG-Ctrl)  
  **Tags:** `CFG Correction` · `Control Theory` · `High Guidance Scale`  
  Reframes CFG as control on the generative flow and proposes SMC-CFG (sliding mode control) with nonlinear feedback to reduce instability and overshooting at large guidance scales; Code release includes FLUX, Qwen-Image, SD3/SD3.5, and Wan video pipelines.

### 3. Adaptive, Scheduled & Efficient Guidance

Papers that adapt guidance strength, schedule guidance over time, or reduce the computational cost of guided sampling.

- **[Adaptive Guidance: Training-free Acceleration of Conditional Diffusion Models](https://arxiv.org/abs/2312.12487)**  
  `2023.12` · `AAAI 2025`  
  **Tags:** `Adaptive Guidance` · `Guidance Schedule` · `Efficiency`  
  Skips evaluations upon convergence via NAS policies for training-free acceleration reducing NFEs.

- **[Analysis of Classifier-Free Guidance Weight Schedulers](https://openreview.net/pdf?id=SUMtDJqicd)**  
  `2024.04` · `TMLR`  
  **Tags:** `Adaptive CFG` · `Guidance Schedule` · `CFG Analysis`  
  Investigates varying classifier-free guidance weights during diffusion, finding that simple, monotonically increasing schedulers improve performance with minimal code, while complex parametrized schedulers offer gains but lack generalizability across models and tasks.

- **[Applying Guidance in a Limited Interval Improves Sample and Distribution Quality in Diffusion Models](https://arxiv.org/abs/2404.07724)**  
  `2024.04` · `NeurIPS 2024` · [Code](https://github.com/kynkaat/guidance-interval)  
  **Tags:** `Guidance Schedule` · `Efficiency` · `CFG`  
  Restricts classifier-free guidance to a limited noise level interval during sampling, improving inference speed and result quality.

- **[Classifier-free Guidance with Adaptive Scaling](https://arxiv.org/abs/2502.10574)**  
  `2025.02` · `arXiv`  
  **Tags:** `Adaptive CFG` · `Dynamic Guidance` · `Guidance Schedule`  
  β-CFG introduces a novel adaptive scaling method using gradient-based normalization and time-dependent β-distribution curves to dynamically balance prompt matching and image quality during the diffusion denoising process.

- **[Adaptive Diffusion Guidance via Stochastic Optimal Control](https://arxiv.org/abs/2505.19367)**  
  `2025.05` · `arXiv`  
  **Tags:** `Adaptive Guidance` · `Optimal Control` · `Guidance Schedule`  
  Introduces a stochastic optimal control framework that dynamically adjusts guidance strength in diffusion models based on time, current sample, and conditioning class, offering a principled approach to guidance scheduling.

- **[Feedback Guidance of Diffusion Models](https://arxiv.org/abs/2506.06085)**  
  `2025.06` · `arXiv` · [Code](https://github.com/FelixKoulischer/FBG_using_edm2)  
  **Tags:** `Feedback` · `Adaptive Guidance` · `Dynamic Guidance`  
  Self-regulates coefficients based on predicted informativeness, adapting for complex prompts and balancing diversity-quality.

- **[How Much To Guide: Revisiting Adaptive Guidance in Classifier-Free Guidance Text-to-Vision Diffusion Models](https://arxiv.org/abs/2506.08351)**  
  `2025.06` · `arXiv`  
  **Tags:** `Adaptive CFG` · `Guidance Schedule` · `Efficiency`  
  Step AG, a simple and universally applicable adaptive guidance strategy, restricts classifier-free guidance to the first several denoising steps, achieving high-quality, well-conditioned images with a 20% to 30% speedup.

- **[Dynamic Classifier-Free Diffusion Guidance via Online Feedback](https://arxiv.org/abs/2509.16131)**  
  `2025.09` · `arXiv`  
  **Tags:** `Feedback` · `Adaptive CFG` · `Guidance Schedule`  
  Introduces a dynamic CFG framework using online feedback from latent-space evaluators (e.g., CLIP, discriminators) to adaptively adjust guidance scales per timestep, achieving up to 55.5% human preference win-rate for prompt-specific image generation.

- **[Towards a Golden Classifier-Free Guidance Path via Foresight Fixed Point Iterations](https://arxiv.org/abs/2510.21512)**  
  `2025.10` · `NeurIPS 2025` · [Code](https://github.com/Ka1b0/Foresight-Guidance)  
  **Tags:** `Fixed-Point` · `CFG Theory` · `Efficiency`  
  Introduces Foresight Guidance (FSG), a unified framework that reframes CFG and its variants as fixed point iterations seeking a golden path. FSG prioritizes longer-interval subproblems in early diffusion stages with increased iterations, achieving state-of-the-art performance in both image quality and computational efficiency.

### 4. Self-, Attention- & Internal-Model Guidance

Papers that derive guidance signals from self-attention, internal representations, or related signals within the diffusion model.

- **[Attend-and-Excite: Attention-Based Semantic Guidance for Text-to-Image Diffusion Models](https://dl.acm.org/doi/abs/10.1145/3592116)**  
  `2023.01` · `ACM Transactions on Graphics`  
  **Tags:** `Cross-Attention` · `Semantic Guidance` · `Training-Free`  
  Introduces Attend-and-Excite, an attention-based semantic guidance method that iteratively refines cross-attention maps to ensure text-to-image diffusion models faithfully generate all subjects in the prompt (requires new attention processor per model).

- **[Diffusion Self-Guidance for Controllable Image Generation](https://arxiv.org/abs/2306.00986)**  
  `2023.06` · `NeurIPS 2023`  
  **Tags:** `Self-Guidance` · `Internal Signal` · `Controllable Generation`  
  Introduces self-guidance, a method that provides greater control over generated images by guiding the internal representations of diffusion models.

- **[Improving Sample Quality of Diffusion Models Using Self-Attention Guidance](https://ieeexplore.ieee.org/document/10378223/)**  
  `2023.10` · `ICCV 2023` · [Code](https://github.com/SusungHong/Self-Attention-Guidance)  
  **Tags:** `Self-Attention` · `Training-Free` · `Artifact Reduction`  
  Uses self-attention maps to guide diffusion models away from degraded regions, improving generated image quality without extra training.

- **[Self-Rectifying Diffusion Sampling with Perturbed-Attention Guidance](https://arxiv.org/abs/2403.17377)**  
  `2024.03` · `ECCV 2024` · [Code](https://github.com/cvlab-kaist/Perturbed-Attention-Guidance)  
  **Tags:** `PAG` · `Attention Guidance` · `Training-Free`  
  Proposes Perturbed-Attention Guidance (PAG) to improve sample quality in diffusion models by adding random perturbations to attention maps, enabling self-rectification in both unconditional and conditional generation.

- **[Guiding a Diffusion Model with a Bad Version of Itself](https://proceedings.neurips.cc/paper_files/paper/2024/hash/5ee7ed60a7e8169012224dec5fe0d27f-Abstract-Conference.html)**  
  `2024.06` · `NeurIPS 2024` · [Code](https://github.com/NVlabs/edm2)  
  **Tags:** `Weak-to-Strong` · `Internal Signal` · `Self-Guidance`  
  Uses a poorly trained model version for guidance to control trade-offs between sample quality and diversity.

- **[Smoothed Energy Guidance: Guiding Diffusion Models with Reduced Energy Curvature of Attention](https://arxiv.org/abs/2408.00760)**  
  `2024.08` · `NeurIPS 2024` · [Code](https://github.com/SusungHong/SEG-SDXL)  
  **Tags:** `Attention Guidance` · `Energy Guidance` · `Artifact Reduction`  
  Presents Smoothed Energy Guidance (SEG), a method that smooths energy curvature in attention maps to enhance unconditional image generation quality while minimizing artifacts (requires new attention processor per model).

- **[Spatiotemporal Skip Guidance for Enhanced Video Diffusion Sampling](https://arxiv.org/abs/2411.18664)**  
  `2024.11` · `CVPR 2025` · [Code](https://github.com/junhahyung/STGuidance)  
  **Tags:** `Skip Guidance` · `Internal Signal` · `Video Diffusion`  
  Develops Spatiotemporal Skip Guidance (STG), a training-free technique that skips specific layers in video diffusion transformers to boost sample quality without sacrificing diversity or motion dynamics.

- **[Entropy Rectifying Guidance for Diffusion and Flow Models](https://arxiv.org/abs/2504.13987)**  
  `2025.04` · `arXiv`  
  **Tags:** `Attention Guidance` · `Flow Guidance` · `Training-Free`  
  Entropy Rectifying Guidance (ERG) is a simple and effective guidance mechanism that improves image quality, diversity, and prompt consistency in diffusion and flow models by modifying the attention mechanism during inference, extending to unconditional sampling and combining seamlessly with other guidance methods.

- **[Normalized Attention Guidance: Universal Negative Guidance for Diffusion Model](https://arxiv.org/abs/2505.21179)**  
  `2025.05` · `NeurIPS 2025`  
  **Tags:** `Attention Guidance` · `Negative Guidance` · `Training-Free`  
  Introduces a training-free, universal negative guidance method for diffusion models that uses extrapolation in attention space with L1-based normalization, generalizing across architectures, sampling regimes, and modalities while maintaining fidelity.

- **[Token Perturbation Guidance for Diffusion Models](https://arxiv.org/abs/2506.10036)**  
  `2025.06` · `NeurIPS 2025` · [Code](https://github.com/TaatiTeam/Token-Perturbation-Guidance)  
  **Tags:** `Token Perturbation` · `Internal Signal` · `Training-Free`  
  Shuffles tokens for training-free, condition-agnostic guidance improving unconditional generation.

- **[S²-Guidance: Stochastic Self Guidance for Training-Free Enhancement of Diffusion Models](https://arxiv.org/abs/2508.12880)**  
  `2025.08` · `arXiv` · [Code](https://github.com/AMAP-ML/S2-Guidance)  
  **Tags:** `Self-Guidance` · `Skip Guidance` · `Training-Free`  
  Introduces a training-free self-guidance method using stochastic block-dropping to create sub-networks that refine suboptimal predictions, enhancing sample quality and prompt adherence beyond traditional CFG.

- **[Improving Diffusion Generalization with Weak-to-Strong Segmented Guidance](https://arxiv.org/pdf/2603.20584)**  
  `2026.03` · `CVPR 2026` · [Code](https://github.com/Westlake-AGI-Lab/SGG)  
  **Tags:** `Weak-to-Strong` · `Adaptive Guidance` · `Training-Free`  
  This paper introduces the Weak‑to‑Strong (W2S) guidance principle and Segmented Guidance (SGG), a framework that combines condition‑dependent and condition‑agnostic guidance to improve the generalization of diffusion models.

### 5. External-Objective & General Conditional Guidance

Papers that use external objectives, discriminators, energy functions, or other general conditioning signals to guide generation.

- **[Refining Generative Process with Discriminator Guidance in Score-based Diffusion Models](https://arxiv.org/abs/2211.17091)**  
  `2022.11` · `ICML 2023` · [Code](https://github.com/alsdudrla10/DG)  
  **Tags:** `Discriminator Guidance` · `External Objective`  
  Introduces Discriminator Guidance, which improves sample quality in pre-trained diffusion models by separately training a discriminator to assess denoising path realism and adding an auxiliary term during generation to deceive it, correcting the score to approximate the data distribution without GAN-like joint training.

- **[Training-Free Structured Diffusion Guidance for Compositional Text-to-Image Synthesis](https://arxiv.org/abs/2212.05032)**  
  `2022.12` · `ICLR 2023` · [Code](https://github.com/weixi-feng/Structured-Diffusion-Guidance)  
  **Tags:** `Training-Free` · `Structured Guidance` · `Semantic Guidance`  
  Improve the compositional skills of T2I models, specifically more accurate attribute binding and better image compositions, by incorporating linguistic structures with the diffusion guidance process.

- **[Universal Guidance for Diffusion Models](https://ieeexplore.ieee.org/document/10208653/)**  
  `2023.06` · `CVPR Workshops 2023` · [Code](https://github.com/arpitbansal297/Universal-Guided-Diffusion)  
  **Tags:** `Training-Free` · `Energy Guidance` · `Arbitrary Conditions`  
  Provides a training-free method to incorporate arbitrary conditions into pre-trained unguided diffusion models using energy functions.

- **[TFG: Unified Training-Free Guidance for Diffusion Models](https://papers.nips.cc/paper_files/paper/2024/hash/2818054fc6de6dacdda0f142a3475933-Abstract-Conference.html)**  
  `2024.09` · `NeurIPS 2024` · [Code](https://github.com/YWolfeee/Training-Free-Guidance)  
  **Tags:** `Training-Free` · `External Objective` · `General Conditional Guidance`  
  Unifies training-free guidance methods with efficient hyper-parameter optimization for various conditional generation tasks.

- **[Variational Control for Guidance in Diffusion Models](https://arxiv.org/abs/2502.03686)**  
  `2025.02` · `arXiv` · [Code](https://github.com/czi-ai/oc-guidance)  
  **Tags:** `Training-Free` · `External Objective` · `Inverse Problems`  
  Employs variational inference for terminal cost guidance in pre-trained models, unifying methods for training-free inverse problems.

- **[Improving Discriminator Guidance in Diffusion Models](https://arxiv.org/abs/2503.16117)**  
  `2025.03` · `arXiv`  
  **Tags:** `Discriminator Guidance` · `External Objective` · `Probabilistic Analysis`  
  Proposes a training objective for discriminator guidance in diffusion models that minimizes Kullback-Leibler divergence, improving sample quality over the conventional method using Cross-Entropy loss.

- **[Domain Guidance: A Simple Transfer Approach for a Pre-trained Diffusion Model](https://arxiv.org/abs/2504.01521)**  
  `2025.04` · `ICLR 2025`  
  **Tags:** `Domain Transfer` · `General Conditional Guidance` · `Training-Free`  
  Introduces a simple transfer approach that leverages pre-trained knowledge to guide the sampling process toward the target domain, sharing a formulation similar to classifier-free guidance for improved domain alignment and generation quality.

- **[Instructing Text-to-Image Diffusion Models via Classifier-Guided Semantic Optimization](https://arxiv.org/abs/2505.14254)**  
  `2025.05` · `arXiv`  
  **Tags:** `External Objective` · `Semantic Guidance` · `Training-Free`  
  Proposes optimizing semantic embeddings guided by attribute classifiers to steer text-to-image diffusion models for desired edits, eliminating the need for text prompts and model training or fine-tuning.

- **[LumaGuide: Distribution Shaping for Training-Free HDR Generation in Diffusion Models](https://arxiv.org/abs/2607.26237)**  
  `2026.08` · `arXiv 2026` · [Code](https://github.com/shreshthsaini/LumaGuide)  
  **Tags:** `Training-Free` · `Energy Guidance` · `Distribution Shaping`  
  Training-free, energy-based guidance that steers sampling toward a target feature distribution instead of a class or prompt. Instantiated for HDR generation by matching a luminance histogram in PQ space through the VAE with a Wasserstein-1 loss on Flux.1-dev; targets come from a small text-to-histogram regressor, a reference image, or a preset, and the same machinery extends to video with temporal consistency terms.

### 6. Flow, Alternative Conditioning & Guidance-Free Methods

Papers that explore flow matching, alternative conditioning mechanisms, or generation without conventional guidance.

- **[ProtoDiffusion: Classifier-Free Diffusion Guidance with Prototype Learning](https://proceedings.mlr.press/v222/baykal24a.html)**  
  `2024.02` · `ACML 2024` · [Code](https://github.com/ituvisionlab/ProtoDiffusion)  
  **Tags:** `Prototype Guidance` · `CFG Alternative` · `Efficiency`  
  Integrates prototype learning into classifier-free guidance to speed up sampling and enhance quality using class-specific prototypes.

- **[No Training, No Problem: Rethinking Classifier-Free Guidance for Diffusion Models](https://arxiv.org/abs/2407.02687)**  
  `2024.07` · `ICLR 2025`  
  **Tags:** `CFG Alternative` · `CFG Theory` · `Training-Free`  
  Introduces independent condition guidance (ICG) and time-step guidance (TSG) using time-step encodings for training-free, invertible sampling applicable unconditionally.

- **[TFG-Flow: Training-free Guidance in Multimodal Generative Flow](https://arxiv.org/abs/2501.14216)**  
  `2025.01` · `ICLR 2025`  
  **Tags:** `Flow Matching` · `Training-Free` · `Flow Guidance`  
  Introduces a novel training-free guidance method for multimodal generative flow, uniquely addressing the curse-of-dimensionality while maintaining unbiased sampling for guiding discrete variables in applications like molecular design.

- **[Visual Generation Without Guidance](https://arxiv.org/abs/2501.15420)**  
  `2025.01` · `ICML 2025` · [Code](https://github.com/thu-ml/GFT)  
  **Tags:** `Guidance-Free` · `CFG Alternative` · `Conditional Generation`  
  Uses only a single model by reformulating the training loss as a linear interpolation between conditional and unconditional components with a randomly sampled pseudo-temperature and a stopping gradient for stability, halving inference costs while matching quality and diversity.

- **[Diffusion Models without Classifier-free Guidance](https://arxiv.org/abs/2502.12154)**  
  `2025.02` · `arXiv` · [Code](https://github.com/tzco/Diffusion-wo-CFG)  
  **Tags:** `CFG-Free` · `Explicit Conditioning` · `Inference Efficiency`  
  Integrates condition posteriors into objectives for accelerated processes matching CFG quality without unconditional models.

- **[CFG-Zero\*: Improved Classifier-Free Guidance for Flow Matching Models](https://arxiv.org/abs/2503.18886)**  
  `2025.03` · `arXiv` · [Code](https://github.com/WeichenFan/CFG-Zero-star)  
  **Tags:** `Flow Matching` · `CFG Correction` · `Guidance Schedule`  
  Optimizes guidance scales for flow matching to correct early velocities and zero initial steps, outperforming CFG in multimedia generation.

- **[Guidance Free Image Editing via Explicit Conditioning](https://arxiv.org/abs/2503.17593)**  
  `2025.03` · `arXiv`  
  **Tags:** `Guidance-Free` · `Explicit Conditioning` · `Image Editing`  
  Explicit  Proposes a  technique that models noise distribution on input modalities to guide conditional diffusion models, significantly reducing computational costs and improving inference time compared to CFG in image editing tasks.

- **[Diffusion Models with Double Guidance: Generate with aggregated datasets](https://arxiv.org/abs/2505.13213)**  
  `2025.05` · `arXiv`  
  **Tags:** `Multi-Condition` · `CFG Alternative` · `Conditional Generation`  
  Enables precise conditional generation by maintaining control over multiple conditions without requiring joint annotations, even when training samples lack all conditions simultaneously.

- **[Rectified-CFG++ for Flow Based Models](https://arxiv.org/abs/2510.07631)**  
  `2025.10` · `NeurIPS 2025` · [Code](https://github.com/shreshthsaini/Rectified-CFGpp/tree/master)  
  **Tags:** `Rectified Flow` · `Flow Guidance` · `CFG Correction`  
  An adaptive predictor-corrector guidance method for rectified flow models that prevents off-manifold drift, ensuring stable, high-quality, and artifact-free image generation across a wide range of guidance scales .
## How to Contribute

If you have a relevant paper to add, please follow these steps:

1. Fork the repository.
2. Create a new branch for your changes.
3. Add the paper to the appropriate topic section.
4. Include the paper link, date, venue, tags, code link when available, and a concise neutral summary.
5. Commit and push your changes.
6. Open a pull request for review.

## To Do

- Continue adding relevant papers.
- Periodically verify paper, venue, and code links.
