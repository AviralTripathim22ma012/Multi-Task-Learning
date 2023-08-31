## Facial Feature Detection
**Dataset:** CelebA <br>
<br>
In machine learning, the task of attribute prediction is predicting one or more 
attributes or characteristics of an object or entity based on the item's features or 
other pertinent data. <br>
A single model is trained using the machine learning technique known as "multitask learning" to carry out several related tasks at once. Multi-task learning could 
be used in the context of attribute prediction to train a single model to predict 
many properties of an object or entity simultaneously. <br>
The benefit of employing multi-task learning for attribute prediction is that it 
enables the model to share data and learn common representations across 
several tasks, potentially improving performance and reducing training times as 
compared to training separate models for each task. <br>
Using a neural network with shared feature extraction layers and task-specific 
output layers for each attribute being predicted is a popular method for multitask learning in attribute prediction. Using a loss function that takes into account 
the faults for each job, the model simultaneously optimises the parameters of all 
the output layers during training. <br>
## Choice of hyperparameters and backbone:
### Why VGG16 over Resnet18?
 Simpler architecture: VGG16 has a simpler architecture compared to 
ResNet18. It consists of 16 layers of convolutional and pooling layers 
followed by three fully connected layers.
 Lower computational cost: VGG16 has a lower computational cost 
compared to ResNet18, as it has fewer parameters. This can be an 
advantage when training on limited computational resources. (as GPU 
runtime is limited in CoLab)
### Why lr= 0.001?
 Effective for most tasks: it balances the need for fast convergence and 
avoiding overshooting.
 Used in pre-trained VGG16 model: VGG16 was trained with a learning rate 
of 0.001, making it a natural choice for fine-tuning.
### Transforms used.
 CenterCrop(178): This transform centers the image and crops it to a square 
of size 178x178 pixels. Center-cropping the image also ensures that the 
face is approximately in the center of the image
 Resize(128): This transform resizes the cropped image to a square of size 
128x128 pixels. Resizing the image to a smaller size reduces the 
computational cost.
### Why Adam Optimizer?
 Sparse binary attributes: The CelebA dataset contains 40 binary attributes. 
These binary attributes are sparse, meaning that only a few of them are 
active for each image. The Adam optimizer can handle sparse gradients 
well and is known to perform well on datasets with sparse features.

## Research paper implemented
Dropped Scheduled Task: Mitigating Negative Transfer in
Multi-task Learning using Dynamic Task Dropping

https://openreview.net/pdf?id=myjAVQrRxS
