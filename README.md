# FaPN: Feature-aligned Pyramid Network for Dense Image Prediction [[arXiv]](https://arxiv.org/pdf/2108.07058.pdf)

```BibTex
@inproceedings{
  huang2021fapn,
  title={{FaPN}: Feature-aligned Pyramid Network for Dense Image Prediction},
  author={Shihua Huang and Zhichao Lu and Ran Cheng and Cheng He},
  booktitle={International Conference on Computer Vision (ICCV)},
  year={2021}
}
```

## Overview
<!-- <img align="right" width="400" src="fpn_vs_fapn.png"> -->
<img width="400" src="./assert/fpn_vs_fapn.png">

This project provides the official implementation for our ICCV2021 paper 
"[FaPN: Feature-aligned Pyramid Network for Dense Image Prediction](https://arxiv.org/pdf/2108.07058.pdf)" 
based on [Detectron2](https://github.com/facebookresearch/detectron2). 
FaPN is a simple yet effective top-down pyramidal architecture to generate multi-scale features for dense image prediction.
Comprised of a feature alignment module (FAM) and a feature selection module (FSM), FaPN addresses the issue of feature alignment
in  the original [FPN](https://arxiv.org/abs/1612.03144), leading improvements on various dense prediction tasks, such as object detection, semantic, instance, panoptic segmentation, etc. 


## Installation
This project is based on [Detectron2](https://github.com/facebookresearch/detectron2), which can be constructed as follows.
* Install Detectron2 following [the instructions](https://detectron2.readthedocs.io/tutorials/install.html).
* Setup the dataset following [the structure](https://github.com/facebookresearch/detectron2/blob/master/datasets/README.md).
* Copy this project to `/path/to/detectron2`
* Install DCNv2 following [Install DCNv2.md](./DCNv2/README.md).

## Training
To train a model with 8 GPUs, run:
```bash
cd /path/to/detectron2/tools
python3 train_net.py --config-file <config.yaml> --num-gpus 8
```

For example, to launch PanopticFCN training (1x schedule) with ResNet-50 backbone on 8 GPUs,
one should execute:
```bash
cd /path/to/detectron2/tools
python3 train_net.py --config-file ../configs\COCO-Detection\faster_rcnn_R_50_FAN_1x.yaml --num-gpus 8
```

## Evaluation
To evaluate a pre-trained model with 8 GPUs, run:
```bash
cd /path/to/detectron2/tools
python3 train_net.py --config-file <config.yaml> --num-gpus 8 --eval-only MODEL.WEIGHTS /path/to/model_checkpoint
```

## Results
### COCO Object Detection
#### Faster R-CNN:
<table><tbody>
<!-- START TABLE -->
<!-- TABLE HEADER -->
<th valign="bottom">Name</th>
<th valign="bottom">lr<br/>sched</th>
<th valign="bottom">box<br/>AP</th>
<th valign="bottom">box<br/>APs</th>
<th valign="bottom">box<br/>APm</th>
<th valign="bottom">box<br/>APl</th>
<th valign="bottom">download</th>
<!-- TABLE BODY -->
<!-- ROW: faster_rcnn_R_50_FAN_1x -->
 <tr><td align="left"><a href="configs/COCO-Detection/faster_rcnn_R_50_FAN_1x.yaml">R50-FAN</a></td>
<td align="center">1x</td>
<td align="center">0.551</td>
<td align="center">0.102</td>
<td align="center">4.8</td>
<td align="center">35.7</td>
<td align="center"><a href="https://drive.google.com/file/d/16bws3mM-itTMBZvbBoBaJIm8bW7jLrTl/view?usp=sharing">model</a>&nbsp;|&nbsp;
<a href="https://drive.google.com/file/d/1cP0JJ98zNbqXDfx2g12qEF3i9wqyxzet/view?usp=sharing">log</a></td>
</tr>
 <tr><td align="left"><a href="configs/COCO-Detection/faster_rcnn_R_101_FAN_3x.yaml">R101-FAN</a></td>
<td align="center">3x</td>
<td align="center">0.551</td>
<td align="center">0.102</td>
<td align="center">4.8</td>
<td align="center">35.7</td>
<td align="center"><a href="https://drive.google.com/file/d/1KioARI3Be2LPG1MdIgiQeAL_KIlRXhNP/view?usp=sharing">model</a>&nbsp;|&nbsp;
<a href="https://drive.google.com/file/d/1a_8yvjIbV_uaNYKsN9sPhblcceHHG7SC/view?usp=sharing">log</a></td>
</tr>
</tbody></table>


