---
layout: project_page
permalink: /

title: "DTBS: Dual-Teacher Bi-directional Self-training for Domain Adaptation in Nighttime Semantic Segmentation"
authors:
    "[Fanding Huang](https://scholar.google.com/citations?user=EKcfr18AAAAJ&hl=en)<sup>1</sup>, 
    Zihao Yao<sup>2</sup>, 
    [Wenhui Zhou](https://scholar.google.com/citations?user=WsRH-pYAAAAJ&hl=zh-CN)<sup>1,*</sup>"
affiliations:
    <sup>1</sup>Hangzhou Dianzi University, <sup>2</sup>University of Wollongong  
paper: https://ebooks.iospress.nl/doi/10.3233/FAIA230382
code: https://github.com/hf618/DTBS
arXiv: https://arxiv.org/abs/2401.01066
---

<!-- Using HTML to center the abstract -->
<div class="columns is-centered has-text-centered">
    <div class="column is-four-fifths">
        <h2>Abstract</h2>
        <div class="content has-text-justified">
Due to the poor illumination and the difficulty in annotating, nighttime conditions pose a significant challenge for autonomous vehicle perception systems. Unsupervised domain adaptation (UDA) has been widely applied to semantic segmentation on such images to adapt models from normal conditions to target nighttime-condition domains. Self-training (ST) is a paradigm in UDA, where a momentum teacher is utilized for pseudo-label prediction, but a confirmation bias issue exists. Because the one-directional knowledge transfer from a single teacher is insufficient to adapt to a large domain shift. To mitigate this issue, we propose to alleviate domain gap by incrementally considering style influence and illumination change. Therefore, we introduce a one-stage Dual-Teacher Bi-directional Self-training (DTBS) framework for smooth knowledge transfer and feedback. Based on two teacher models, we present a novel pipeline to respectively decouple style and illumination shift. In addition, we propose a new Re-weight exponential moving average (EMA) to merge the knowledge of style and illumination factors, and provide feedback to the student model. In this way, our method can be embedded in other UDA methods to enhance their performance. For example, the Cityscapes to ACDC night task yielded 53.8 mIoU (%), which corresponds to an improvement of +5% over the previous state-of-the-art.
        </div>
    </div>
</div>

---


## Pipline

![pipline](/static/image/overview2_00.png)

*Figure 1: Overview of the proposed Dual-teacher Bidirectional Self-training (DTBS) architecture. Source flow ① → Target-day flow ② → Target-night flow ③ → T-S Feedback ④ are the four sub-flows that make up each iteration, with `sg` standing for no gradient backward propagation. The first three workflows achieve smooth domain adaptation. T-S feedback integrates knowledge to iteratively refine the student.*

## Performance

![performance](/static/image/com_sota3_min16_00.png)

*Figure 2: Some visual segmentation results of ACDC night val for the `Cityscapes → ACDC night` task. With the teacher model parameters feedback, our method is superior at predicting the street-side structures (building, fence) and easily-confused classes (traffic sign, terrain).*


## BibTeX
```
@incollection{huang2023dtbs,
  title={Dtbs: Dual-teacher bi-directional self-training for domain adaptation in nighttime semantic segmentation},
  author={Huang, Fanding and Yao, Zihao and Zhou, Wenhui},
  booktitle={ECAI 2023},
  pages={1084--1091},
  year={2023},
  publisher={IOS Press}
}
```
