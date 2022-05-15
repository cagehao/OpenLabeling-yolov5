# OpenLabeling-yolov5

This is a project that modified Openlabeling with auto-labeling features by using yolov5 to label the data automatically.

# How to use the yolov5 detect feature 
+ 1, modify project_root\yolov5\detect.py line 49 weights=[path to your customized weight]
+ 2, run project_root\main\main.py
+ 3, select the image and set Detect = 1, wait for few second and the yolov5 will automatically label the data, and you can manually correct the labels.
![1.png](https://raw.github.com/cagehao/OpenLabeling-yolov5/master/1.png)
![2.png](https://raw.github.com/cagehao/OpenLabeling-yolov5/master/2.png)
+ 4, find your label in the project_root\main\output\YOLO_darknet

# Use data class confidence balance feature
a problem in agnostic non maxium suppression is that if the confidence of the classes are not balance in the neural network, for two similiar classes, one class always get higher confidence than the other. So, the weak class is always suppress by the other class, then all the objects belongs to these two classes are classified as the strong class.
![3.png](https://raw.github.com/cagehao/OpenLabeling-yolov5/master/3.png)
So the basic idea is to add a augment value to the weak class, so the class confidence balance feature enables us to select a class and add up to 10 levels of for any class.
Usage: 
+ Drag the Class track bar to the class you think is a weak class
+ Drag the Balance track bar to the level you want to augment
(you can repeat the two steps for multiple classes balancing, your choice of each class will be remembered)
+ select the image and set Detect = 1, you can see the difference after the class balancing.
![4.png](https://raw.github.com/cagehao/OpenLabeling-yolov5/master/4.png)
# reference:
+ yolov5:https://github.com/ultralytics/yolov5
+ OpenLabeling: https://github.com/Cartucho/OpenLabeling
