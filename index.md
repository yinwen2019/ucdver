---
layout: project_page
permalink: /

title: Knowledge-Aligned Counterfactual-Enhancement Diffusion Perception for Unsupervised Cross-Domain Visual Emotion Recognition

authors:
  - name: Wen Yin
    link: https://yinwen2019.github.io/
    superscript: 1
  - name: Yong Wang
    link: https://www.en.scse.uestc.edu.cn/info/1085/1927.htm
    superscript: 1
  - name: Guiduo Duan
    link: https://www.scse.uestc.edu.cn/info/1081/11210.htm
    superscript: 1,2
  - name: Dongyang Zhang
    link: https://zhangdy827.github.io/dyzhang.github.io/
    superscript: 1
  - name: Xin Hu
    link: https://openreview.net/profile?id=~XIN_Hu8
    superscript: 1
  - name: Yuan-Fang Li
    link: https://liyuanfang.github.io/
    superscript: 3
  - name: Tao He
    link: https://ht014.github.io/
    superscript: 1,2,*

affiliations:
    <sup>1</sup> The Laboratory of Intelligent Collaborative Computing of UESTC  <br>
    <sup>2</sup> Ubiquitous Intelligence and Trusted Services Key Laboratory of Sichuan Province  <br>
    <sup>3</sup> Faculty of Information Technology, Monash University  <br>
    <sup>*</sup> Corresponding author

accepted:
    The IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR) 2025
paper: https://www.cs.virginia.edu/~robins/Turing_Paper_1936.pdf
# video: https://www.youtube.com/results?search_query=turing+machine
code: https://github.com/yinwen2019/UCDVER
# data: https://huggingface.co/docs/datasets
slide: https://yinwen2019.github.io/ucdver/assets/slide.pptx
---

<!-- Using HTML to center the abstract -->
<div class="columns is-centered has-text-centered">
    <div class="column is-four-fifths">
        <h1>Abstract</h1>
        <div class="content has-text-justified">
        Visual Emotion Recognition (VER) is a critical yet challenging task aimed at inferring the emotional states of individuals based on visual cues. However, recent approaches predominantly focus on single domains, e.g., realistic images or stickers, limiting VER models' cross-domain generalizability. To address this limitation, we introduce an Unsupervised Cross-Domain Visual Emotion Recognition (UCDVER) task, which aims to generalize visual emotion recognition from the source domain (e.g., realistic images) to the low-resource target domain (e.g., stickers) in an unsupervised manner. Compared to the conventional unsupervised domain adaptation problems, UCDVER presents two key challenges: a significant emotional expression variability and an affective distribution shift. To mitigate these issues, we propose the Knowledge-aligned Counterfactual-enhancement Diffusion Perception (KCDP) framework for UCDVER. Specifically, KCDP first leverages a vision-language model to align emotional representations in a shared knowledge space and guides diffusion models for improved visual affective perception. Furthermore, a Counterfactual-Enhanced Language-image Emotional Alignment (CLIEA) method generates high-quality pseudo-labels for the target domain. Extensive experiments demonstrate that our approach surpasses state-of-the-art models in both perceptibility and generalization, e.g., gaining 12% improvements over SOTA VER model TGCA-PVT.
        </div>
    </div>
</div>

---


# Background
**Visual Emotion Recognition** (**VER**), a fundamental task in artificial intelligence and human-computer interaction, aims to identify human emotions through visual cues, such as facial expressions, body language  and contextual scene features. Existing VER methods typically focus on realistic images and have gained considerable advancements on a suite of datasets such as **EmoSet** and **Emotion6**. Unfortunately, current VER models cannot handle emotion recognition in these new domains due to the significant emotional expression variability between domains and an affective distribution shift. In this paper, we introduce a new challenging task **Unsupervised Cross-Domain Visual Emotion Recognition** (**UCDVER**), where a model is trained with labeled source-domain data (e.g., realistic images) and unlabeled target domain data (e.g., stickers), but is employed to recognize emotion in the target domain.

# Motivation
Taking the stickers and realistic images as an example shown in Figure 1, two key challenges arise:
- **Emotional expression variability**: Emotional expressions vary greatly. Realistic images reflect emotions expressed by real humans, while stickers exaggerate or simplify emotions, often focusing on single or multiple virtual elements.
- **Affective distribution shift**: According to the _Emotional Causality theory_, an emotion is embedded in a sequence involving (i) _external event_; (ii) _emotional state_; and (iii) _physiological response_. Stickers or emojis emphasize the last two, i.e. (ii) and (iii) , while the emotion in realistic images is often linked to the external context surrounding the subject(s).


![databias](/assets/databias.svg){: style="width: 500px; height: 300px; display: block; margin: 0 auto; margin-top: 50px; margin-bottom: 50px;"}


# Methods
We propose a **Knowledge-aligned Counterfactual-enhancement Diffusion Perception** (**KCDP**) framework, which projects affective cues into a domain-agnostic knowledge space and performs domain-adaptive visual affective perception by a diffusion model.  

Briefly, KCDP is composed of two primary modules: **Knowledge-Alignment Diffusion
Affective Perception** (**KADAP**) and **Counterfactual-Enhanced Language-Image Emotional Alignment** (**CLIEA**). The \textbf{KADAP} module focuses on learning domain-agnostic knowledge and making robust predictions based on an MoE predictor , while the **CLIEA** module generates high-quality pseudo-labels for effective training .


![framework](/assets/framework.svg){: style="width: 1000px; height: auto; display: block; margin: 0 auto; margin-top: 100px; margin-bottom: 100px;"}


The CLIEA strategy is designed to generate high-quality emotional pseudo-labels for  the target domain. CLIEA is inspired by the causal relationships underlying language-image emotional alignment.


![framework](/assets/casusalgraph.svg){: style="width: 500px; height: auto; display: block; margin: 0 auto; margin-top: 50px; margin-bottom: 50px;"}


## Citation
```
@article{ucdver,
  title={Knowledge-Aligned Counterfactual-Enhancement Diffusion Perception for Unsupervised Cross-Domain Visual Emotion Recognition},
  author={Wen Yin, Yong Wang, Guiduo Duan, Dongyang Zhang, Xin Hu, Yuan-Fang Li, Tao He},
  journal={CVPR},
  year={2025}
}
```
