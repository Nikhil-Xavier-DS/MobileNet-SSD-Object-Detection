# MobileNet SSD Object Detection

# MobileNet
MobileNets, as the name suggests, are neural networks constructed for the purpose of running very efficiently (high FPS, low memory footprint) on mobile devices. MobileNets has 3 steps:
1. Perform a separable depthwise convolution.
2. Use Width Multiplier to reduces the size of the input/output channels, set to a value between 0 and 1.
3. Use Resolution multiplier to reduces the size of the original input, set to a value between 0 and 1.

These 3 techiniques reduce the size of cummulative parameters and therefore the computation required. 

## MobileNet SSD
The SSD architecture is a single convolutional network which learns to predict bounding box locations and classify the locations in one pass. Put differently, SSD can be trained end to end while Faster-RCNN cannot. The SSD architecture consists of a base network followed by several convolutional layers: 
SSD operates on feature maps to predict bounding box locations.Each bounding box carries with it the following information:
1. 4 corner bounding box offset locations
2. CC class probabilities

SSD does not predict the shape of the box, rather just where the box is. The steps for object detection are as following:
1. Starts from a base model pretrained on ImageNet.
2. The base model is extended by several convolutional layers.
3. Each feature map is used to predict bounding boxes. Diversity in feature map size allows object detection at different resolutions.
4. Boxes are filtered by IoU metrics and hard negative mining.
5. Loss is a combination of classification (softmax) and dectection (smooth L1)
6. Model can be trained end to end.

Object detection pipeline is tested on the video attached.
