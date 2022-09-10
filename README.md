# LG_instance_segmentation_contest ✨
## 입자 검출 정보 기반으로 입자들의 형태 변화를 계량적 지표로 산출 가능한 모델 개발

---
### Introduction
- 주최 : LG 화학 <br/>
- 주관 : 인공지능팩토리 (AIFactory) <br/>
- 대회 기간: 7/7 (목) 8:00 ~ 8/8 (월) 18:00 <br/>
- link: https://aifactory.space/competition/detail/2067 <br/>
- 주제: 유체상에 떠다니는 입자를 촬영한 화상을 바탕으로 각 입자와 그 형상을 최대한 잘 검출해내는 Instance Segmentation 모델을 만드는 것이 이번 대회 목표. <br/>
- 참고) 입자들의 형상은 균일하지 않고 유체상에서 촬영된 결과물인 만큼 표면으로부터의 거리에 따라 선명도 또한 차이가 있으며, 서로 겹쳐져 있는 경우도 존재. <br/>

<img src='https://user-images.githubusercontent.com/61971952/188265389-b1461854-a775-423b-bd1a-a901de19bef9.png' width = '500' height = '300'/> <br/>

### Dataset
- train dataset: 520장 <br/>
- test dataset: 350장 <br/>
- coco dataset 형식의 annotation file(입자 labeling 형식에 따라 label_train.json, label(polygon)train.json) <br/>
- 객체 category: 1개 (Normal) <br/>
- image height, width = 1024, 1280 <br/>

### Workflow
#### 1주차(7/13 ~ 7/17)
* Studying instance segmentation </br>
(https://mountainous-patio-ee7.notion.site/instance-segmentation-69662f0a591746d2a2db4cb218de95b0) </br> 
* Learn about MMdetection library </br>
간편하게 여러 최신 model을 이용할 수 있도록 package 제공됨. 
(https://mountainous-patio-ee7.notion.site/MMdetection-daba1bc939194a999963f4cec999eb59) </br>
* Data analysis 
* Train base-line(Mask RCNN) model <br/>
</br>

 Model | Backbone | Score
 -------------|-------|-------|
 Mask RCNN(base-line) | resnet50 |  0.5761174985  |

</br>

#### 2주차(7/18 ~ 7/24)
* segmentation model list up </br>
→ Mask R-CNN, Cascade Mask R-CNN, Mask Scoring R-CNN, Hybrid Task Cascade, YOLACT, SOLO, PointRend, DetectoRS, SOLOv2, SCNet, QueryInst
* 조원들에게 model 분배 후 제출 </br>
→ ✔️ Model을 분배했던 이유: MMDetection엔 많은 Instance Segmentation model이 존재하는데 각 model을 공부한 다음 data와 맞다고 생각되는 model을 정하기엔 시간이 촉박하여 조원들에게 model 분배 후 performance를 보고 model을 선정하기로 함.
* 점수가 높은 model 선정 </br>
→ SCNet, Mask Scoring R-CNN, Cascade Mask R-CNN, Mask R-CNN  </br>
(0.57 이상의 점수가 나오는 model로 선정)
</br>

분배모델| 점수
-------|-------|
SCNet_r50_fpn_1x_coco  |  0.5861291233  |
Cascade Mask R-CNN_r101_fpn_1x_coco | 0.596460128 |
Mask Scoring R-CNN_r50_fpn_1x_coco | 0.5752475505  |
Mask R-CNN_r101_fpn_1x_coco  |  0.5800140828 |
   
</br>

* model 공부 </br>
  * Mask R-CNN: https://www.notion.so/Mask-R-CNN-36b84ef17a21435e98760b11b444a20c
  * Cascade R-CNN: https://www.notion.so/Cascade-R-CNN-67c341f5a30d4c508443c93d3b16c7d6
  * SCNet: https://www.notion.so/SCNet-9d8061d6127b45cebec17e183ab232b8
  * Mask Scoring R-CNN: https://www.notion.so/Mask-Scoring-R-CNN-8db7c7d76c2248f5bcdfb62ee2253674 </br>
* modeling <br/>
#### 3주차(7/25 ~ 7/31)
* data 전처리 list up 후 분배, performance 확인 및 선정 </br>
✔️model selection 후 data 전처리 순으로 workflow를 잡은 이유: 
  * Augmentation(이미지 증강 기법)
  * Transform(이미지 중 일부를 변형하여 학습에 사용)
* Backbone 분배 후 성능 확인 및 선정 <br/>
#### 4주차(8/1 ~ 8/8)
Optimizer, Lr-scheduler 분배 후 선정 <br/>
성능 향상을 위한 hyperparameter 조정 <br/>

### Result
- mmdetection설명
- segmentation model -> 선정한 model
- augmentation list up -> 선정한거
- backbone 
- optimizer, lr-scheduler
- hyperparameter


## Discussion
