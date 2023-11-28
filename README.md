# MoGuP

This repository is the official implementation of [MoGuP](https://moguprediction.github.io/) [![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Fvt-le%2FMoGuP&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false)](https://hits.seeyoufarm.com).

**[MoGuP: Motion-Guided Prediction for Video Anomaly Detection](https://moguprediction.github.io/)**
<br/>
[Viet-Tuan Le](https://vt-le.github.io/), 
[Yong-Guk Kim](http://home.sejong.ac.kr/~ykim/)
<br/>

[![Project Website](https://img.shields.io/badge/Project-Website-orange)](https://moguprediction.github.io/)


## News

- [11/24/2023] Pre-trained MoGuP models are released!
<!--
- [XX/XX/2024] Code released!)
-->

## Setup

### Requirements

```shell
pip install -r requirements.txt
```

We evaluate `MoGuP` on:
| Dataset | Link                                                                                  |
|--|---------------------------------------------------------------------------------------|
| UCSD Ped2 | [![Google drive](https://badgen.net/static/Homepage/Ped2/blue)](http://www.svcl.ucsd.edu/projects/anomaly/dataset.html) |
| CUHK Avenue | [![Google drive](https://badgen.net/badge/Homepage/Avenue/cyan)](http://www.cse.cuhk.edu.hk/leojia/projects/detectabnormal/dataset.html) |
| ShanghaiTech | [![Google drive](https://badgen.net/badge/Homepage/ShanghaiTech/green?)](https://svip-lab.github.io/dataset/campus_dataset.html) |

A dataset is a directory with the following structure:
  ```bash
  $ tree data
  ped2/avenue
  ├── training
  │   └── frames
  │       ├── ${video_1}$
  │       │   ├── 000.jpg
  │       │   ├── 001.jpg
  │       │   └── ...
  │       ├── ${video_2}$
  │       │   ├── 00.jpg
  │       │   └── ...
  │       └── ...
  ├── testing
  │   └── frames
  │       ├── ${video_1}$
  │       │   ├── 000.jpg
  │       │   ├── 001.jpg
  │       │   └── ...
  │       ├── ${video_2}$
  │       │   ├── 000.jpg
  │       │   └── ...
  │       └── ...
  └── ped2/avenue.mat
  
  shanghaitech
  ├── training
  │   └── frames
  │       ├── ${video_1}$
  │       │   ├── 000.jpg
  │       │   ├── 001.jpg
  │       │   └── ...
  │       ├── ${video_2}$
  │       │   ├── 00.jpg
  │       │   └── ...
  │       └── ...
  ├── testing
  │   └── frames
  │       ├── ${video_1}$
  │       │   ├── 000.jpg
  │       │   ├── 001.jpg
  │       │   └── ...
  │       ├── ${video_2}$
  │       │   ├── 000.jpg
  │       │   └── ...
  │       └── ...
  └── test_frame_mask
      ├── 01_0014.npy
      ├── 01_0015.npy
      └── ...  
  ```

## Data preprocessing
- Object detecion: [Cascade R-CNN](https://github.com/open-mmlab/mmaction2)
- Extracting optical flow frames: [FlowNet2.0](https://github.com/NVIDIA/flownet2-pytorch)


## Evaluation
Please first download the pre-trained model

| Dataset | Pretrained Model                                                                                  |
|--|---------------------------------------------------------------------------------------|
| UCSD Ped2 | [![Google drive](https://badgen.net/static/Link/Ped2/blue?icon=chrome)](https://drive.google.com/drive/folders/1Jq8vEGS9eEV2a6rK3TmjhUKcbbbuLcYd?usp=sharing) |
| CUHK Avenue | [![Google drive](https://badgen.net/badge/Link/Avenue/blue?icon=chrome)](https://drive.google.com/drive/folders/1UxPg9u6Bmhh5YBMfU31Gj4BZmL-ghIeq?usp=sharing) |
| ShanghaiTech | [![Google drive](https://badgen.net/badge/Link/ShanghaiTech/blue?icon=chrome)](https://drive.google.com/drive/folders/1Jq8vEGS9eEV2a6rK3TmjhUKcbbbuLcYd?usp=sharing) |

## Usage

### Training

```bash
 python hybrid_train.py \
    --cfg <path/to/config/file>
```   

### Evaluation

Once the training is done, run inference:

```bash
 python hybrid_eval.py \
    --cfg <path/to/config/file>
``` 

## Visualization

<table class="center">
<tr>
  <td style="text-align:center;"><b>UCSD Ped22</b></td>
  <td style="text-align:center;"><b>CUHK Avenue</b></td>
</tr>
<tr>
  <td><img src="https://github.com/MoGuPrediction/MoGuPrediction.github.io/blob/main/static/images/fig_introduction_error_comparation_ped2.png"></td>
  <td><img src="https://github.com/MoGuPrediction/MoGuPrediction.github.io/blob/main/static/images/fig_introduction_error_comparation_avenue.png"></td>
  <td><img src="https://github.com/MoGuPrediction/MoGuPrediction.github.io/blob/main/static/images/fig_introduction_error_comparation_shanghaitech.png"></td>
</tr>
</table>


## Citation
If you make use of our work, please cite our paper.
```bibtex
@article{le2024mogup,
    title={MoGuP: Motion-guided Prediction for Video Anomaly Detection},
    author={Le, Viet-Tuan and Kim, Yong-Guk},
}
```