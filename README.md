# Superpixel-enhanced Deep Neural Forest for Remote Sensing Image Semantic Segmentation
Code for Paper  
[Superpixel-enhanced Deep Neural Forest for Remote Sensing Image Semantic Segmentation](https://www.sciencedirect.com/science/article/pii/S0924271619302606)  
!['Can't load IMAGE'](https://github.com/whulixiya/ML/blob/master/Frameworks.png) 
## Environments
* Python 3.6.2
* Tensorflow 1.6.0
* Numpy 1.13.1
* Opencv-python
* Matplotlib
* Scipy

## Data
*	Download the test image (RGB for Potsdam/IRRG for Vaihingen) and RGB label image (Fully Reference/No Boundary) from ISPRS 2D semantic labelling website.
*	Transfer the RGB label image to the corresponding label image (provided).
                  
|         | Index | R    | G    | B    |
| ------- | ----- | ---- | ---- | ---- |
| Imp     | 0     | 255  | 255  | 255  |
| Build   | 1     | 0    | 0    | 255  |
| Low     | 2     | 0    | 255  | 255  |
| Tree    | 3     | 0    | 255  | 0    |
| Car     | 4     | 255  | 255  | 0    |
| Cluster | 5     | 255  | 0    | 0    |
| Un      | 6     | 0    | 0    | 0    |

*	Rename the testing image and label image.
## Evaluation
``` python
import predict_potsdam
predict_potsdam.process()

import predict_vaihingen
predict_vaihingen.process()
``` 
* The results include the predict RGB image, the predict Label image and the results.txt for accuracy.
* The whole evaluation process is about 20min.

## Results
|                      | Imp.S.   | Imp.S. | Build.   | **Build.** | Low.V.   | Low.V. | Tree     | Tree | Car      | Car  | Mean     | Mean     | OA       |
| -------------------- | -------- | ------ | -------- | ---------- | -------- | ------ | -------- | ---- | -------- | ---- | -------- | -------- | -------- |
|                      | F1       | IoU    | F1       | IoU        | F1       | IoU    | F1       | IoU  | F1       | IoU  | F1       | IoU      |          |
| Pre-trained Model(P) | 93.6     | 87.7   | 96.3     | 93         | **89.8** | 81.5   | **92.7** | 86.4 | **96.7** | 93.6 | **93.8** | **88.4** | 92.1     |
| Paper(P)             | **94.1** | 88.9   | **97.8** | 95.7       | 89.5     | 80.9   | 90.4     | 82.5 | 95.1     | 90.7 | 93.4     | 87.7     | **92.6** |
| Pre-trained Model(V) | **93.6** | 87.9   | 96.2     | 92.6       | 87.3     | 77.4   | **92.1** | 85.3 | **85.3** | 74.4 | 90.9     | **83.5** | **92.3** |
| Paper(V)             | 93.4     | 87.7   | **97.6** | 95.3       | **87.4** | 77.7   | 91.2     | 83.8 | 85.2     | 74.3 | **91**   | 83.3     | 92.2     |

## TODO
- [ ] Report the results trained on RTX8000

## Acknowledgements
Our code is developed based on：

[ssn_superpixels](https://github.com/NVlabs/ssn_superpixels)  
[pytorch_ssn](https://github.com/CYang0515/pytorch_ssn)  
[fully-differentiable-deep-ndf-tf](https://github.com/chrischoy/fully-differentiable-deep-ndf-tf)  
[Neural-Decision-Forests](https://github.com/jingxil/Neural-Decision-Forests)  
[tensorflow-deeplab-v3](https://github.com/rishizek/tensorflow-deeplab-v3)  
[deeplabv3-Tensorflow](https://github.com/ximimiao/deeplabv3-Tensorflow)  

## Cite
@article{Li2020Superpixel,  
  title={Superpixel-enhanced deep neural forest for remote sensing image semantic segmentation},  
  author={Li Mi and Zhenzhong Chen},  
  journal={ISPRS Journal of Photogrammetry and Remote Sensing},  
  volume={159},  
  pages={140-152},  
  year={2020},  
}

