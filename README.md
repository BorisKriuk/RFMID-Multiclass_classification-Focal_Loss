# RFMID-Multiclass_classification-Focal_Loss
Solving Class Imbalance problem at the Retinal Fundus Multi-disease Image Dataset by implementing Focal Loss.

I.Object Detectors

The two-stage approach predominates in modern object recognition. As initially introduced in the Selective Search [1], the first stage creates a sparse set of candidate proposals, and the second stage classifies the proposals into foreground classes. Combining region proposals with Convolutional Neural Networks later improved the second-stage classifier, starting a series of enhancements of the second-stage classifier.
 
Most of the one-stage object detectors are tuned for speed; however, their accuracy doesn’t compare with those using the two-stage approach. In 2017, it was clearly shown that two-stage detectors could achieve higher rates by using samples with smaller image resolutions and fewer proposals. At the same time, the one-stage approach still doesn’t perform much better with high-resolution images and larger sample groups [2]. There is still much potential in one-stage object detectors and areas for research focus.

II. Class Imbalance Problem

Many object recognition methods face the problem of sample class imbalance during development which causes the following problems:
 
1. 	Easy negatives oftentimes saturate the sample and lead to model efficiency degeneration.
2. 	Easy negatives don’t contribute to the model learning process.
 
Common complex solutions usually focus on resampling and reweighing techniques. In 2018, Lin et al. from Facebook introduced the idea of Focal Loss, which is designed to handle the class imbalance problem in a more natural way [3].

IV. Essential EDA of Retinal Fundus Multi-disease Image Dataset (RFMID)

The dataset consists of 3200 fundus images captured using three different fundus cameras with 46 conditions annotated through adjudicated consensus of two senior retinal experts. The RFMID was designed to enable the development of generalizable models for retinal screening. The dataset is skewed and clearly faces the class imbalance problem that should be addressed properly.

V. Model Creation and Evaluation

The proposed Computer Vision model was tested to have higher efficiency than other candidates. To estimate the Focal Loss efficiency, the model was compiled using both Cross Entropy Loss and Focal Loss. For the Focal Loss, the following parameters were chosen: ɑ = 0.25, ɣ = 2.0. A weight balancing factor for all classes, the default is 0.25, as mentioned in the reference [3], and the focusing parameter, the default, is 2.0, as mentioned in the reference [3]. It helps to gradually reduce the importance given to simple (easy) examples in a smooth manner.

Reference:

[1] J. R. Uijlings, K. E. van de Sande, T. Gevers, and A. W. Smeulders. Selective search for object recognition. IJCV, 2013. 2, 4
[2] J. Huang, V. Rathod, C. Sun, M. Zhu, A. Korattikara, A. Fathi, I. Fischer, Z. Wojna, Y. Song, S. Guadarrama, and K. Murphy. Speed/accuracy trade-offs for modern convolutional object detectors. In CVPR, 2017. 2, 8
[3] Lin, T., Goyal, P., Girshick, R., He, K., & Dollár, P. (2017). Focal Loss for Dense Object Detection. ArXiv. /abs/1708.02002

