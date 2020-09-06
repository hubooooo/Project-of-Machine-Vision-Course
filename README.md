# -
基于SSD算法的商品识别与自动计价系统

算法流程：
1.Prior box matching
2.Loss function
3.Data amplification
4.Forecasting process
5.Performance evaluation

具体实施:
①Data preparation 
to generate our own datasets and make labels
②Perform training 
to modify the default training script content of SSD to match our own dataset
③Testing 
to test different combinations of several types of items.


YOLO存在三个缺陷：

1.两个bounding box功能的重复降低了模型的精度；
2.全连接层的使用不仅使特征向量失去了位置信息，还产生了大量的参数，影响了算法的速度；
3.只使用顶层的特征向量使算法对于小尺寸物体的检测效果很差。

为了解决这些问题，SSD应运而生。SSD的全称是Single Shot MultiBox Detector，Single Shot表示SSD是像YOLO一样的单次检测算法，MultiBox指SSD每次可以检测多个物体，Detector表示SSD是用来进行物体检测的。

相比Yolo，SSD采用CNN来直接进行检测，而不是像Yolo那样在全连接层之后做检测。其实采用卷积直接做检测只是SSD相比Yolo的其中一个不同点，另外还有两个重要的改变，一是SSD提取了不同尺度的特征图来做检测，大尺度特征图（较靠前的特征图）可以用来检测小物体，而小尺度特征图（较靠后的特征图）用来检测大物体；二是SSD采用了不同尺度和长宽比的先验框（Prior boxes, Default boxes，在Faster R-CNN中叫做锚，Anchors）。

