# Int20h hackathon test task

## Objective
Create a model to solve [iMaterialist (Fashion) 2019 at FGVC6](https://www.kaggle.com/c/imaterialist-fashion-2019-FGVC6) competition.
Task can be splitted to two subtasks:
* outfit parts segmentation
* outfit parts class prediction
## Modeling steps
**EDA**<br><br>
**Test dataset preprocessing based on EDA:**<br>
* removed objects with classes that containen attributes
* removed objects with area less then 10 000px<br>

Class propostion within datasest were preserved<br><br>
**Model training**<br>
Model was trained used MaskRCNN neural network with RESNET50 backbone for 1 epoch on 20% of original dataset. This restrictions is dictated by lack of personal hardware and Kaggle GPU usage limitations. <br>
For training images augmentation Random Horizontal Flip were used. <br>
Images were resized to 512x512 due to restrictions described. <br>
Model optimization were performed with next parameters:
* learning rate = 0.001
* momentum = 0.9
* weight_decay = 0.0005
* scheduler step size = 5
* gamma = 0.1 <br>

Model were evaluated on average Intersection over Union score for segmantation and Accuracy for class prediction.<br>
We got next results:<br>
**IoU:<br>**
**Accuracy:<br>**
## Further steps
Implement adaptive learning rate (speedup) <br>
Try "lighter" backbone model like MobileNet (speedup) <br> 
Try triangle learning rate (better/faster convergence) <br>
If possible (hardware restrictions) train on full sized images <br>
If possble (hardware restrictions) use full dataset <br>
Optimize evaluation loop (speedup) <br>
