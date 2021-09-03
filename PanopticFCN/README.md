# FaPN: Feature-aligned Pyramid Network for Dense Image Prediction [[arXiv]](https://arxiv.org/pdf/2108.07058.pdf) [[Project Page]](http://www.shihuahuang.cn/fapn/)

```BibTex
@inproceedings{
  huang2021fapn,
  title={{FaPN}: Feature-aligned Pyramid Network for Dense Image Prediction},
  author={Shihua Huang and Zhichao Lu and Ran Cheng and Cheng He},
  booktitle={International Conference on Computer Vision (ICCV)},
  year={2021}
}
```


## Installation
* Copy this project to `/path/to/PanopticFCN`

## Training
To train a model with 8 GPUs, run:
```bash
cd /path/to/detectron2/tools
python3 projects/PanopticFCN/train.py --config-file <config.yaml> --num-gpus 8
```

For example, PanopticFCN training (1x schedule) with ResNet-50-FAST backbone on 8 GPUs,
one should execute:
```bash
cd /path/to/detectron2/tools
python3 projects/PanopticFCN/train.py --config-file projects/PanopticFCN/configs/PanopticFCN-R50+FaPN-1x-FAST.yaml --num-gpus 8
```

## Evaluation
To evaluate a pre-trained model with 8 GPUs, run:
```bash
cd /path/to/detectron2/tools
python3 projects/PanopticFCN/train.py --config-file <config.yaml> --num-gpus 8 --eval-only MODEL.WEIGHTS /path/to/model_checkpoint
```

## Results
### COCO Panoptic Segmentation
#### PanopticFCN + FaPN:
<table><tbody>
<!-- START TABLE -->
<!-- TABLE HEADER -->
<th valign="bottom">Name</th>
<th valign="bottom">lr<br/>sched</th>
<th valign="bottom">PQ</th>
<th valign="bottom">mask<br/>mIoU</th>
<th valign="bottom">St<br/>PQ</th>
<th valign="bottom">box<br/>AP</th>
<th valign="bottom">Th<br/>PQ</th>
<th valign="bottom">download</th>
<!-- TABLE BODY -->
 <tr><td align="left"><a href="./PanopticFCN/configs/PanopticFCN-R50+FaPN-1x-FAST.yaml">R50</a></td>
<td align="center">1x</td>
<td align="center">41.8</td>
<td align="center">42.0</td>
<td align="center">33.1</td>
<td align="center">32.3</td>
<td align="center">47.6</td>
<td align="center"><a href="https://drive.google.com/file/d/1r3OlzCityLm9hhcXpoDAcfF6g4t4Qro1/view?usp=sharing">model</a>&nbsp;|&nbsp;
<a href="https://drive.google.com/file/d/1BYylyzmDOlBWObopjYjXSWdopG1Vijqx/view?usp=sharing">log</a></td>
</tr>
 <tr><td align="left"><a href="./PanopticFCN/configs/PanopticFCN-R50-600+FaPN-3x-FAST.yaml">R50-600</a></td>
<td align="center">3x</td>
<td align="center">43.5</td>
<td align="center">43.5</td>
<td align="center">35.1</td>
<td align="center">34.5</td>
<td align="center">49.0</td>
<td align="center"><a href="https://drive.google.com/file/d/1RIlPN1fvdQ95Yytjs-cir-FCWTSeUx2E/view?usp=sharing">model</a>&nbsp;|&nbsp;
<a href="https://drive.google.com/file/d/1jhqspevFvlLvpNKv0oh-5A1Mw0wGu97r/view?usp=sharing">log</a></td>
</tr>
</tbody></table>
