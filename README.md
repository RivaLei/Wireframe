# Wireframe

> A curated list of papers & resources linked to Wireframe.

## Introduction

## Contents

- [2D Wireframe](#2d-wireframe)
  - [Papers](#papers-2d)
    - [2018](###2018)
    - [2019](###2019)
    - [2020](###2020)
    - [2021](###2021)
  - [Datasets (2D)](#data-2d)
- [3D Wireframe](#3d-wireframe)
  - [Papers](#papers-3d)
  - [Datasets (3D)](#data-3d)

# 2D Wireframe

The wireframe parsing task is firstly proposed by Huang et al. [1]. It proposes the task formulation, a large-scale 
dataset with wireframe annotations, a baseline method, and a set of evaluation metrics. After that, Zhou et al. [4] and 
propose an end-to-end solution and significantly improves the performance. Zhang et al. [3] is a counterpart work and refine 
the annotations of [1]. Meanwhile, Xue et al. [8] is a follow-up work of Xue et al. [2] which holds the new state-of-the-art result. 
Lin et al. [6] design a hough transform based convolutional operator to treat the line detection task. 
In order to handle the topology of junction and line, a graph neural network based method LGNN [5] was proposed to resolve the wireframe task. 
Besides, Huang et al. [7] propose to speed up the line detection. 
Strictly speaking, line detection is not wireframe parsing as it does not detect junctions of multiple segments.

<p align="center">
<img src="img/demo.gif"  width="400">
</p>

The source video above is from [kujiale](https://b.kujiale.com/) website. 

<a name="papers-2d"></a>

## Papers

### 2018

- [1] Kun Huang, Yifan Wang, Zihan Zhou, Tianjiao Ding, Shenghua Gao, and Yi Ma. Learning to parse wireframes in images of man-made environments. In CVPR, 2018. [[code](https://github.com/huangkuns/wireframe)] [[paper](https://arxiv.org/abs/2007.07527)]

### 2019

- [2] Nan Xue, Song Bai, Fudong Wang, Gui-Song Xia, Tianfu Wu, and Liangpei Zhang. Learning attraction field representation for robust line segment detection. In CVPR, 2019. [[code](https://github.com/cherubicXN/afm_cvpr2019)] [[paper](https://openaccess.thecvf.com/content_CVPR_2019/papers/Xue_Learning_Attraction_Field_Representation_for_Robust_Line_Segment_Detection_CVPR_2019_paper.pdf)]
- [3] Ziheng Zhang*, Zhengxin Li*, Ning Bi, Jia Zheng, Jinlei Wang, Kun Huang, Weixin Luo, Yanyu Xu, and Shenghua Gao. Ppgnet: Learning point-pair graph for line segment detection. In CVPR, 2019. [[code](https://github.com/svip-lab/PPGNet)] [[paper](https://www.aiyoggle.me/publication/ppgnet-cvpr19/ppgnet-cvpr19.pdf)]
- [4] Yichao Zhou, Haozhi Qi, and Yi Ma. End-to-End Wireframe Parsing. In ICCV, 2019. [[code](https://github.com/zhou13/lcnn)] [[paper](https://arxiv.org/abs/1905.03246)]

### 2020

- [5] Quan Meng, Jiakai Zhang, Qiang Hu, Xuming He, and Jingyi Yu. 2020. LGNN: A Context-aware Line Segment Detector. In ACM MM, 2020. [[paper](https://arxiv.org/abs/2008.05892)]
- [6] Yancong Lin, and Silvia L. Pintea, and Jan C. van Gemert. Deep Hough-Transform Line Priors. In ECCV, 2020. [[code](https://github.com/yanconglin/Deep-Hough-Transform-Line-Priors)] [[paper](https://arxiv.org/abs/2007.09493)]
- [7] Siyu Huang, Fangbo Qin, Pengfei Xiong, Ning Ding, Yijia He, and Xiao Liu. TP-LSD: Tri-Points Based Line Segment Detector. In ECCV, 2020. [[code](https://github.com/Siyuada7/TP-LSD)] [[paper](https://arxiv.org/abs/2009.05505)]
- [8] Nan Xue, Tianfu Wu, Song Bai, Fudong Wang, Gui-Song Xia, Liangpei Zhang, and Philip H.S. Torr. Holistically-attracted wireframe parsing. In CVPR, 2020. [[code](https://github.com/cherubicXN/hawp)] [[paper](https://arxiv.org/pdf/2003.01663.pdf)]

### 2021

- [9] Yifan Xu*, Weijian Xu*, David Cheung, and Zhuowen Tu. Line Segment Detection Using Transformers without Edges. In CVPR, 2021. [[paper](https://arxiv.org/abs/2101.01909)]
- [10] Xili Dai, Xiaojun Yuan, Haigang Gong, and Yi Ma. Fully Convolutional Line Parsing. arXiv preprint, 2021. [[code](https://github.com/Delay-Xili/F-Clip)] [[paper](https://arxiv.org/abs/2104.11207v2)]

<a name="data-2d"></a>

## Datasets (2D)

So far as we know, there exist two wireframe datasets namely [**ShanghaiTech**](https://github.com/huangkuns/wireframe) and [**YorkUrban**](https://www.elderlab.yorku.ca/resources/york-urban-line-segment-database-information/).

1. The **ShanghaiTech** dataset proposed by Huang et al. [1]. It contains 5,000 training images and 462 test images of man-made scenes which is a basic dataset used by all methods [1-8]. It has another relabeled version [**SIST**](https://github.com/svip-lab/PPGNet) which's junctions and lines are carefully labeled.
2. The **YorkUrban** is an early existent dataset which is a small dataset containing 102 images and only has Manhattan lines labeled. Most works test their model on it to evaluate the generalizability of models.

|            <img src="img/ShanghaiTech.png" width="280">            |                                   <img src="img/YorkUrban.png" width="280">                                    |
| :----------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------: |
| [**ShanghaiTech dataset**](https://github.com/huangkuns/wireframe) | [**YorkUrban dataset**](https://www.elderlab.yorku.ca/resources/york-urban-line-segment-database-information/) |

### Leaderboard

|              |                  | DWP[1] | AFM[2] | PPGNET[3] | LCNN[4] | LGNN[5] | DHT[6] | TP-LSD[7] | HAWP[8] | LETR[9] | F-Clip[10] |
| :----------: | :--------------: | :----: | :----: | :-------: | :-----: | :-----: | :----: | :-------: | :-----: | :-----: | :--------: |
| ShanghaiTech | sAP<sup>10</sup> |  5.1   |  24.4  |     -     |  62.9   |  62.3   |  66.6  |   60.6    |  66.5   |  65.2   |    68.3    |
|              |  AP<sup>H</sup>  |  67.8  |  69.2  |           |  80.3   |    -    |   -    |   84.3    |  84.5   |  84.7   |    85.7    |
|  YorkUrban   | sAP<sup>10</sup> |  2.1   |  9.4   |     -     |  26.4   |    -    |  27.4  |   27.4    |  28.5   |  29.4   |    30.8    |
|              |  AP<sup>H</sup>  |  51.0  |  48.2  |           |  58.5   |    -    |   -    |     -     |  60.6   |  61.2   |    65.0    |

# 3D Wireframe-test riva branch

<p align="center">
<img src="img/3d-wireframe.png"  width="400">
<img src="img/3d-wireframe.gif"  width="400">
</p>

<a name="papers-3d"></a>

## Papers (3D)

- Yichao Zhou, Haozhi Qi, Yuexiang Zhai, Qi Sun, Zhili Chen, Li-Yi Wei, and Yi Ma. Learning to reconstruct 3D Manhattan wireframes from a single image. In ICCV, 2019. [[dataset](https://drive.google.com/drive/folders/11OBjTfMSIqFgFeS6c3M1UGZXpozV4S4P)] [[code](https://github.com/zhou13/shapeunity)] [[paper](https://arxiv.org/abs/1905.07482)] [[video](https://www.youtube.com/watch?v=l3sUtddPJPY)]
- Rémi Pautrat*, Juan-Ting Lin*, Viktor Larsson, Martin R. Oswald, and Marc Pollefeys. SOLD2: Self-supervised Occlusion-aware Line Description and Detection. In CVPR, 2021. [[code](https://github.com/cvg/SOLD2)] [[paper](https://arxiv.org/abs/2104.03362)]

<a name="data-3d"></a>

## Datasets (3D)

So far as we know, there exist two wireframe datasets: one synthetic dataset and one real world dataset. Both of them were proposed by [Zhou et al.](https://arxiv.org/abs/1905.07482)

1. [**SceneCity**](https://drive.google.com/drive/folders/13zE_7tL5ms7YagaXJbzLFTM1ygBv2jRS) is synthetic city dataset which is generated through 3D mesh.
   The dataset includes 230 cities, each containing 8 × 8 city blocks. 100 viewpoints are generated for each city and then render to images through global illumination by Blender modeler. The number of total images is 23000, first 22700 images for training and the rest 300 for validation.

2. [**MegaWireframe**](https://drive.google.com/drive/folders/1nvKZMU2fSECMo1BfW2Ge1EO1mBuKRq2n) is a realistic Landmark dataset which is relabeled from [MegaDepth v1](http://www.cs.cornell.edu/projects/megadepth/) dataset. It selects about 200 images from [MegaDepth v1](http://www.cs.cornell.edu/projects/megadepth/) which is manually labeled with wireframes, and registered with the rough 3D depth.

|                         <img src="img/SceneCity.png" width="280">                         |                           <img src="img/megaDepth.png" width="280">                           |
| :---------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------: |
| [**SceneCity**](https://drive.google.com/drive/folders/13zE_7tL5ms7YagaXJbzLFTM1ygBv2jRS) | [**MegaWireframe**](https://drive.google.com/drive/folders/1nvKZMU2fSECMo1BfW2Ge1EO1mBuKRq2n) |
