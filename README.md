## 图像检索

开始整理这两三年自己在image retrieval的一些资料，方便来年的毕业设计。

#### 单词数目为100k统计的各项指标

| 单词数目 | SIFT or rootSIFT | 空间校正与否 | 重排数目 | 检索精度mAP | 查询时间(55张)(s) |
| ---------|:----------------:| :-----------:|:--------:|:-----------:|:-----------------:|
|   100k   |    rootSIFT      |      否      |     -    |    62.46%   |       5.429707    |
|   100k   |    rootSIFT      |      是      |    20    |    66.42%   |      20.853832    |
|   100k   |    rootSIFT      |      是      |    30    |    68.25%   |      21.673585    |
|   100k   |    rootSIFT      |      是      |    40    |    69.27%   |      23.300404    |
|   100k   |    rootSIFT      |      是      |    50    |    69.83%   |      23.719468    |
|   100k   |    rootSIFT      |      是      |    100   |    72.48%   |      24.180888    |
|   100k   |    rootSIFT      |      是      |    200   |    75.56%   |      31.165427    |
|   100k   |    rootSIFT      |      是      |    500   |    78.85%   |      46.064313    |
|   100k   |    rootSIFT      |      是      |    1000  |    79.93%   |      70.192928    |
|   100k   |    rootSIFT      |      是      |    2000  |    80.75%   |     110.999173    |
|   100k   |    rootSIFT      |      是      |    3000  |    80.92%   |     145.799017    |
|   100k   |    rootSIFT      |      是      |    4000  |    80.97%   |     176.786657    |
|   100k   |    rootSIFT      |      是      |    5063  |    80.96%   |     207.201570    |

#### 单词数目为500k统计的各项指标

| 单词数目 | SIFT or rootSIFT | 空间校正与否 | 重排数目 | 检索精度mAP | 查询时间(55张)(s) |
| ---------|:----------------:| :-----------:|:--------:|:-----------:|:-----------------:|
|   500k   |    rootSIFT      |      否      |     -    |    74.82%   |       5.345534    |
|   500k   |    rootSIFT      |      是      |    20    |    77.77%   |      21.646773    |
|   500k   |    rootSIFT      |      是      |    30    |    79.06%   |      21.615220    |
|   500k   |    rootSIFT      |      是      |    40    |    79.86%   |      23.453462    |
|   500k   |    rootSIFT      |      是      |    50    |    80.54%   |      23.588034    |
|   500k   |    rootSIFT      |      是      |    100   |    82.18%   |      24.942057    |
|   500k   |    rootSIFT      |      是      |    200   |    83.35%   |      30.585792    |
|   500k   |    rootSIFT      |      是      |    500   |    84.89%   |      41.023239    |
|   500k   |    rootSIFT      |      是      |    1000  |    85.52%   |      54.836481    |
|   500k   |    rootSIFT      |      是      |    2000  |    85.73%   |      67.173112    |
|   500k   |    rootSIFT      |      是      |    3000  |    85.77%   |      80.634803    |
|   500k   |    rootSIFT      |      是      |    5063  |    85.76%   |     103.606303    |

#### 单词数目为1m统计的各项指标

| 单词数目 | SIFT or rootSIFT | 空间校正与否 | 重排数目 | 检索精度mAP | 查询时间(55张)(s) |
| ---------|:----------------:| :-----------:|:--------:|:-----------:|:-----------------:|
|    1m    |    rootSIFT      |      否      |     -    |    77.64%   |       5.513093    |
|    1m    |    rootSIFT      |      是      |    20    |    80.00%   |      18.864077    |
|    1m    |    rootSIFT      |      是      |    30    |    80.81%   |      18.948402    |
|    1m    |    rootSIFT      |      是      |    40    |    81.44%   |      21.543470    |
|    1m    |    rootSIFT      |      是      |    50    |    82.02%   |      23.290658    |
|    1m    |    rootSIFT      |      是      |    100   |    83.32%   |      25.396074    |
|    1m    |    rootSIFT      |      是      |    200   |    84.47%   |      31.414361    |
|    1m    |    rootSIFT      |      是      |    500   |    85.25%   |      39.314887    |
|    1m    |    rootSIFT      |      是      |    1000  |    85.51%   |      46.913126    |
|    1m    |    rootSIFT      |      是      |    2000  |    85.55%   |      58.102913    |
|    1m    |    rootSIFT      |      是      |    3000  |    85.55%   |      68.756579    |
|    1m    |    rootSIFT      |      是      |    4000  |    85.55%   |      77.051332    |
|    1m    |    rootSIFT      |      是      |    5063  |    85.55%   |      85.428169    |

**查询时间**：查询时间是单词查询的结果，并没有进行多次查询进行平均，此外查询时间是查询和计算mAP时间的总和。

### MSER

MSER得到椭圆区域后，再结合SIFT，可以剔除掉很多没用的点，VLFeat中的MESR例子见[这里](http://www.vlfeat.org/overview/mser.html)。此外MSER还可以用于文本区域筛选中，具体可以看这个[Robust Text Detection in Natural Scenes and Web Images](http://prir.ustb.edu.cn/TexStar/scene-text-detection/)。概念与作用相关词：漫水填充法、显著性。

### 基于SIFT特征点匹配

[SIFT on GPU (SiftGPU)](http://ccwu.me/), works for nVidia, ATI and Intel cards.

### 待做实现

- Fisher Vector 256个单词，128降维到64，oxford buiding上mAP为42.70%。
- Fisher Vector 512个单词，128降维到64，oxford buiding上mAP为52.27%；L2归一化中如果不采用max的方式，mAP为43.43%。
- Fisher Vector 1024个单词，128降维到64，oxford buiding上mAP为x%；L2归一化中如果不采用max的方式，mAP为47.06%。
