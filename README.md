# MoGuP

This repository is the official implementation of [MoGuP]().

**[MoGuP: Motion-Guided Prediction for Video Anomaly Detection]()**
<br/>
[Viet-Tuan Le](https://vt-le.github.io/), 
[Yong-Guk Kim](http://home.sejong.ac.kr/~ykim/)
<br/>

[![Project Website](https://img.shields.io/badge/Project-Website-orange)](https://moguprediction.github.io/)


## News

- [XX/XX/2024] Pre-trained MoGuP models are available on [Hugging Face Library](https://huggingface.co/)!
- [XX/XX/2024] Code released!

## Setup

### Requirements

```shell
pip install -r requirements.txt
```

### Weights

**[PVTv2]** [PVT](https://github.com/whai362/PVT).. 


## Usage

### Training

```python
...
```

### Inference

Once the training is done, run inference:

```python
...
```

## Visualization

<table class="center">
<tr>
  <td style="text-align:center;"><b>UCSD Ped22</b></td>
  <td style="text-align:center;"><b>CUHK Avenue</b></td>
</tr>
<tr>
  <td><img src="static/images/fig_introduction_error_comparation_ped2.png"></td>
  <td><img src="static/images/fig_introduction_error_comparation_avenue.png"></td>
  <td><img src="static/images/fig_introduction_error_comparation_shanghaitech.png"></td>
</tr>
</table>


## Citation
If you make use of our work, please cite our paper.
```bibtex
@article{le2024mogup,
    title={MoGuP: Motion-guided Prediction for Video Anomaly Detection},
    author={Le, Viet-Tuan and Kim, Yong-Gul},
    journal={IEEE Transactions on Circuits and Systems for Video Technology},
    year={2024}
}
```