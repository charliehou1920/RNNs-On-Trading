# ECE-GY-7123-mini-project    

-------------------------------------------------------------------------------------------------------------

## A guide for this repository

This Repository contains 5 files:

(1) Mini_Project_Final.ipynb: This file contains everything for this mini project. Recommend you to run it on Google Colab

(2) Best_Model.pt: This is a PyTorch file with the best model we got after training 50 epochs. You can load our best model with following commands on Google Colab:

```python
import torch
PATH = 'Best_Model.pt'
# Load
model = torch.load(PATH)
model.eval()
```

(3) Best_Model_acc_history.png : This is a screen shot which records the accuracy per epoch in our best model

(4) Best_Model_loss_history.png: This is a screen shot which records the loss per epoch in our best mode

(5) README.md: The README file provides a generalization for this mini project

---------------------------------------------------------------------------------------------------

## **Introduction**

In this project, we modify the architecture of the residual network (ResNet) model for image classification on the CIFAR-10 dataset, with the goal of achieving a test accuracy of over 90% while keeping the model size under 5 million parameters. 

This project provides insights into the impact of different architectural modifications and hyper-parameter choices on the performance of ResNet, in the context of image classification tasks.

-------------------------------------------------------------------------

## Final Model Architecture

| Final model parameters                           | Values for the parameter                                 |
| ------------------------------------------------ | -------------------------------------------------------- |
| Number of the channels in the residual layer     | 64, 128, 256                                             |
| Batch Size                                       | 128                                                      |
| Kernel Size                                      | 3                                                        |
| Padding                                          | 1                                                        |
| Input data normalization                         | (0.4914,0.4822,0.4465), (0.2023,0.1994,0.2010)           |
| Number of residual blocks in each residual layer | Layer 1: 4;   Layer 2: 5;   Layer 3: 3                   |
| Initial Learning Rate                            | 0.75                                                     |
| Data augmentation strategies implemented         | Random Crop, Random Horizontal Flip, Normalize, ToTensor |
| Optimizer                                        | SGD with WEIGHT_DECAY = 0.001 and MOMENTUM = 0.9         |



------------------------------------------------------------------------

## **Methodologies to improve the Network**

**Methodology 1: Adjust the channel size for the Network** 

We found channel size = 32 or channel size = 42 is a good option when number of channels in the residual layer is 4, kernel_ size = 3 and padding = 1.

---------------------------------------------------------------------

**Methodology 2: Implement learning rate decay algorithm**

We designed and implemented a Constant Learning Rate Decay Algorithm to control the learning rate. Here is the core logic implemented by Python:

```python
# We set epoch_num = 50, initial lr = 0.1, lr_decay_period = 2
for epoch in range(epoch_num):
    if epoch != 0 and epoch % lr_decay_period == 0:
        if(lr>0.0015):
            lr*=lr_decay
```



---------------------------------------------------------------------

**Methodology  3: Data Augmentation**

The augmentation methods we utilized in our model: Random Crop, Random Horizontal Flip, Normalize, ToTensor


---------------------------------------------------------------------

**Methodology 4: Modify Resnet layers and add bottleneck**

For our final model, we set the number of channels in the residual layer as 3. Number of residual blocks in each residual layer is: 

Layer 1: 4

Layer 2: 5

Layer 3: 3













