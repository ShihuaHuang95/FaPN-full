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
* Install MaskFormer following [the instructions](https://github.com/facebookresearch/MaskFormer/blob/main/INSTALL.md)
* Setup the dataset following [the structure](https://github.com/facebookresearch/MaskFormer/blob/main/datasets/README.md)
* Copy this project to `/path/to/MaskFormer`

## Training
To train a model with 8 GPUs, run:
```bash
cd /path/to/MaskFormer
python3 ./train_net.py \
  --config-file configs/ade20k-150/swin/maskformer_swin_large+FaPN_IN21k_384_bs16_160k_res640.yaml \
  --num-gpus 8
```

## Evaluation
To evaluate a pre-trained model with 8 GPUs, run:
```bash
cd /path/to/MaskFormer
python3 train_net.py --config-file <config.yaml> --num-gpus 8 --eval-only MODEL.WEIGHTS /path/to/model_checkpoint
```

## Results
### ADE20K-150 Semantic Segmentation
#### MaskFormer + FaPN:
<table><tbody>
<!-- START TABLE -->
<!-- TABLE HEADER -->
<th valign="bottom">Name</th>
<th valign="bottom">mIoU<br/>Single-Scale</th>
<th valign="bottom">mIoU<br/>Multi-Scale</th>
<th valign="bottom">download</th>
<!-- TABLE BODY -->
 <tr><td align="left"><a href="./MaskFormer/configs/ade20k-150/swin/maskformer_swin_large+FaPN_IN21k_384_bs16_160k_res640.yaml">Swin+Large+IN21K</a></td>
<td align="center">55.2</td>
<td align="center">56.7</td>
<td align="center"><a href="https://drive.google.com/file/d/1MGE6INbMhzXW6f9_eFejJtqlYEKYxTQM/view?usp=sharing">model</a>&nbsp;|&nbsp;
<a href="https://drive.google.com/file/d/1CYW-G_OLn8EtGlDbktI6ykwFJ8q0aL4O/view?usp=sharing">log</a></td>
</tbody></table>

### COCOStuff-10K Semantic Segmentation
#### MaskFormer + FaPN:
<table><tbody>
<!-- START TABLE -->
<!-- TABLE HEADER -->
<th valign="bottom">Name</th>
<th valign="bottom">mIoU<br/>Single-Scale</th>
<th valign="bottom">mIoU<br/>Multi-Scale</th>
<th valign="bottom">download</th>
<!-- TABLE BODY -->
 <tr><td align="left"><a href="./MaskFormer/configs/coco-stuff-10k-171/maskformer_R101+FaPN_bs32_60k.yaml">R101</a></td>
<td align="center">39.6</td>
<td align="center">40.6</td>
<td align="center"><a href="https://drive.google.com/file/d/1UvK8XOwqfIrGVQGdT84bkehU72cHSeXO/view?usp=sharing">model</a>&nbsp;|&nbsp;
<a href="https://drive.google.com/file/d/1BNxjTnGrHxlsqtB23wiE1aOHgSJRJYwM/view?usp=sharing">log</a></td>
</tbody></table>