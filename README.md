# CASS: Class-wise Adaptive Strategy for Semi Supervised Semantic Segmentation

## Update Note
* (24.01.31) The paper has been accepted into IEEE Access.

### [Paper](https://doi.org/10.1109/ACCESS.2024.3363628)

## Getting Started

PASCAL VOC 2012 download link : [JPEGImages](http://host.robots.ox.ac.uk/pascal/VOC/voc2012/VOCtrainval_11-May-2012.tar), [SegmentationClass](https://drive.google.com/file/d/1Of_zgYIG_zdX1gJhnmFJRZ3uBTza2mpw/view?usp=sharing)

```angular2html
[Your Pascal Path]
  ├── JPEGImages
  └── SegmentationClass
```

Pretrained Backbone : [ResNet101](https://drive.google.com/file/d/126ZzFt8PQ0KX7dvKCn-ZSeKb468mZOyj/view?usp=share_link), [MiT-B4](https://drive.google.com/file/d/1Gn0QT7-SgT3k20JtSX7nyIOQJaEPcbQT/view?usp=share_link)

Eval Weight : [link](https://drive.google.com/drive/folders/11_MzauUu0de4NWCb0D4IpGtVcXLO1hSc?usp=share_link)

```angular2html
CASS
├── pretrained
│   ├── resnet101.pth
│   └── mit_b4.pth
└── cass_pretrained
    ├── 1_CASS_1_4_resnet101_78.04.pth
    ├── 2_CASS_1_4_resnet101_78.32.pth
    ├── 3_CASS_1_4_resnet101_78.05.pth
    ├── 1_CASS_1_4_segf_b4_79.90.pth
    ├── 2_CASS_1_4_segf_b4_79.81.pth
    └── 3_CASS_1_4_segf_b4_79.99.pth
```
## Config
You can control our methods in the [config file]().

## Train
```bash
sh tool/train.sh <num_gpu> <port>

# ex : sh tool/train.sh 4 23500
```

## Eval
```bash
sh tool/eval.sh <num_gpu> <port>

# ex : sh tool/eval.sh 4 23500
```

## Paper Result

| Method           |  1/2 (5292) |  1/4 (2646) |  1/8 (1323) |  1/16 (662) |
| -----------------| ----------- | ----------- | ----------- | ----------- |
| ST++             | -           | 76.6        | 76.3        | 74.5        |
| UniMatch         | 77.5        | 77.2        | 77.0        | 76.5        |
| CASS-V3(ours)    | 78.1        | 78.0        | 77.5        | 77.1        |
| CASS-B4(ours)    | 80.2        | 79.9        | 78.8        | 77.5        |


## Re Implementation Result

| Model               |  1/2 (5291) |  1/4 (2646) |  1/8 (1323) |  1/16 (662) |
| --------------------| ----------- | ----------- | ----------- | ----------- |
| CASS-V3 (Try 1)     | [78.86](https://drive.google.com/file/d/11U1StTB6y7TONpxO8DkLnBLpI-Cuhls2/view?usp=sharing) | [78.04](https://drive.google.com/file/d/1M-mp2XyQy4PE6OZoaDXQB0nViY0k8R__/view?usp=sharing) | [77.18](https://drive.google.com/file/d/1xJ8DPYHsqFm2OZOvJnUdqGVgWPvWiMk9/view?usp=sharing)        | TODO        |
| CASS-V3 (Try 2)     | [78.60](https://drive.google.com/file/d/19QoxDPdLl7M1SxF9FfV0amaEY_RkqPbl/view?usp=sharing) | [78.32](https://drive.google.com/file/d/1QlWG0A8fzmvbauofskJiHFgqAiEOZzjM/view?usp=sharing) | [77.29](https://drive.google.com/file/d/1UPQGOXo2aLhWaEI1K4UcITRhyygsSpeu/view?usp=sharing)        | TODO        |
| CASS-V3 (Try 3)     | [79.21](https://drive.google.com/file/d/1CinXys39ts-Ml0fdGUsA8PekL8JcoV6Y/view?usp=sharing) | [78.05](https://drive.google.com/file/d/1rJsMpMBoZLr5Uz3z4hpwEwRFKho59Z3G/view?usp=sharing) | [77.76](https://drive.google.com/file/d/1_M3sZE3XMsr6_Iq9LCkFH9yfjcEub8sp/view?usp=sharing)        | TODO        |
| Mean (std)          | 78.89 (0.25)       | 78.13 (0.13)        | 77.41 (0.25)        | TODO        |
|     |    |    |         |         |
| CASS-B4 (Try 1)     | [80.49](https://drive.google.com/file/d/1S7LrvcFT2ozLD_PKr8OkXd9tujEUJIas/view?usp=sharing)        | [79.90](https://drive.google.com/file/d/1mLzZnt1vELRAUWnJS1FJFjtNZyYJcENj/view?usp=share_link) | [78.78](https://drive.google.com/file/d/1S4Zy4hl7QwNwqWacNM2O0pG_v_TadTz7/view?usp=sharing)        | TODO        |
| CASS-B4 (Try 2)     | [80.53](https://drive.google.com/file/d/10FA8zYYZe5VbOTvLJ8VW7wlH-btvbRaA/view?usp=sharing)        | [79.81](https://drive.google.com/file/d/1l49MDtrBDDS0FN4NPoFX0UGoQaOsdTvt/view?usp=sharing) | [78.72](https://drive.google.com/file/d/1voq2y234u8VAwzDWjySlFWQQAONOvz-Y/view?usp=sharing)        | TODO        |
| CASS-B4 (Try 3)     | [80.42](https://drive.google.com/file/d/1UaklR18Bqjo889QHMYZqjZdkEMIt47Lw/view?usp=sharing)        | [79.99](https://drive.google.com/file/d/1BeH8r0MiioAzw_QPy2enC8aCmXdvdOpv/view?usp=sharing) | [78.76](https://drive.google.com/file/d/1dA_FJYXkQGicxDfQkdXuWHyXxDCfTFnO/view?usp=sharing)        | TODO        |
| Mean (std)          | 80.48 (0.05)        | 79.89 (0.07)        | 78.75 (0.02)        | TODO        |

