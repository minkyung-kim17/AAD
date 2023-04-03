# Active anomaly detection based on deep one-class classification
Kim, Minkyung, et al. "Active anomaly detection based on deep one-class classification." Pattern Recognition Letters 167 (2023): 18-24.


## Abstract
> Active learning has been utilized as an efficient tool in building anomaly detection models by leveraging expert feedback. In an active learning framework, a model queries samples to be labeled by experts and re-trains the model with the labeled data samples. It unburdens in obtaining annotated datasets while improving anomaly detection performance. However, most of the existing studies focus on helping ex- perts identify as many abnormal data samples as possible, which is a sub-optimal approach for one-class classification-based deep anomaly detection. In this paper, we tackle two essential problems of active learning for Deep SVDD: query strategy and semi-supervised learning method. First, rather than solely identifying anomalies, our query strategy selects uncertain samples according to an adaptive boundary. Second, we apply noise contrastive estimation in training a one-class classification model to incorporate both labeled normal and abnormal data effectively. We analyze that the proposed query strategy and semi-supervised loss individually improve an active learning process of anomaly detection and further improve when combined together on seven anomaly detection datasets.

## Run experiment
python main.py {dataset name} {pollution ratio} {loss type} {query type} {pseudo-abnormal}
```
[Options]
Dataset         : ionosphere, arrhythmia, cardio, mnist_tab, glass, optdigits, nslkdd
Pollution ratio : [0, 1] 
                  If the value is larger than the pollution ratio of each dataset, it's changed to the pollution ratio of each dataset.
                  Ex.) 1 is interpreted as the pollution ratio of each dataset.
Loss type       : soft_boundary, one_class, dsad, nce, soft_boundary_nce, one_class_uai, soft_boundary_uai
Query type      : random, mlp, db, abs, no
Pseudo-abnormal : {0:not use, 1:use}
```

* The code and repository are based on the following works: [Deep-SVDD-PyTorch](https://github.com/lukasruff/Deep-SVDD-PyTorch) and [Deep-SAD-PyTorch](https://github.com/lukasruff/Deep-SAD-PyTorch)
* FYI: [Random Seeds and Reproducibility](https://towardsdatascience.com/random-seeds-and-reproducibility-933da79446e3)

## Citation and Contact
If you use our work, please also cite the paper:
```
@article{kim2023active,
  title={Active anomaly detection based on deep one-class classification},
  author={Kim, Minkyung and Kim, Junsik and Yu, Jongmin and Choi, Jun Kyun},
  journal={Pattern Recognition Letters},
  volume={167},
  pages={18--24},
  year={2023},
  publisher={Elsevier}
}
```
If you would like to get in touch, please contact [mkkim1778@gmail.com](mailto:mkkim1778@gmail.com)
