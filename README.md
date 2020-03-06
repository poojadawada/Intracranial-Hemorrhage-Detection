# Intracranial Hemorrhage Detection

MSBA - Semester 2 (Advanced Predictive Modeling)

Intracranial hemorrhage and its type is time consuming to detect and sometimes needs intrusive procedure to be sure. It is very time sensitive and mortality rate is quite high. Solving this problem through deep learning models would have a great impact on the lives of people. So we decided to give it a shot.
The problem consists of finding if the hemorrhage exists and then classifying it into what type of hemorrhage it is.

![Layers of Brain](https://github.com/poojadawada/Intracranial-Hemorrhage-Detection/blob/master/hem2.png)

Depending on where the bleeding is, the type of hemorrhage and the corresponding treatment is decided.

### Dataset
The dataset ([Kaggle](https://www.kaggle.com/c/rsna-intracranial-hemorrhage-detection)) had DCM images that capture the density instead of color at each pixel.
Each DCM image had 6 labels. One for existence of hemorrhage and 5 for the subtypes. So it was a multilabel classification problem.

### Preprocessing
Windowing: Zooming into a pixel range (brain density range, bone density range, blood density range, etc) to maximize information we pass through the RGB channels of the input layer in a Convolutional Neural Network.

### Modeling:
We tried VGG16, Resnet50, InceptionV3 and dilated Resnet with 6 sigmoid units for the output layer. We recieved best results from InceptionV3 and dilated Resnet

### Evaluation:
Kaggle competition suggested a weighted cross entropy, with more weightage on detection of a hemorrhage.
As it is a highly imbalanced problem, we also considered F1 score and decided InceptionV3 to give the best result on basis of that.
The threshold was decided giving more weightage to recall as is the case in a medical case.


For more information, please refer to the presentation in the repository or our [blogpost](https://medium.com/detecting-intracranial-hemorrhage-with-deep/detecting-intracranial-hemorrhage-with-deep-learning-e3c5a6eb3d11).
