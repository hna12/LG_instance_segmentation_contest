# Mask scoring R-CNN
link: https://paperswithcode.com/method/mask-scoring-r-cnn

Mask scoring R-CNN = Mask RCNN with MaskIoU Head, which takes the instance feature and the predicted mask together as input, and predicts the IoU btw input mask and GT mask

backbone: ResNext101, ResNet strikes back

optimizer: SGD, Adadelta

AutoAugment(online augmentation) : resizing default mmdet image size (1333, 800) -> origin image size (1280,1024)
