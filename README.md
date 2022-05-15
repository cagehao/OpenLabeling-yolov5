# OpenLabeling-yolov5

This is a project that modified Openlabeling with auto-labeling features by using yolov5 to label the data automatically.

# How to use the yolov5 detect feature 
+ 1, modify project_root\yolov5\detect.py line 49 weights=[path to your customized weight]
+ 2, run project_root\main\main.py
+ 3, select the image and set Detect = 1, wait for few second and the yolov5 will automatically label the data, and you can manually correct the labels.
![1.png](https://raw.github.com/cagehao/OpenLabeling-yolov5/master/1.png)
![2.png](https://raw.github.com/cagehao/OpenLabeling-yolov5/master/2.png)
+ 4, find your label in the project_root\main\output\YOLO_darknet

# Use data data confidence balance feature
a problem in agnostic non maxium suppression is that if the confidence of the classes are not balance in the neural network, for two similiar classes, one class always get higher confidence than the other. So, the weak class is always suppress by the other class, then all the objects belongs to these two classes are classified as the strong class.
![3.png](https://raw.github.com/cagehao/OpenLabeling-yolov5/master/3.png)
reference:
+ yolov5:https://github.com/ultralytics/yolov5
+ OpenLabeling: https://github.com/Cartucho/OpenLabeling
