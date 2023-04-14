# ECE-GY-7123-mini-project    

-------------------------------------------------------------------------------------------------------------

## **Introduction**

In this project, we modify the architecture of the residual network (ResNet) model for image classification on the CIFAR-10 dataset, with the goal of achieving a test accuracy of over 90% while keeping the model size under 5 million parameters. 

This project provides insights into the impact of different architectural modifications and hyper-parameter choices on the performance of ResNet, in the context of image classification tasks.

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

**Methodology  3**

Add a **Learning Rate Decay** parameter for tuning the Learning Rate with two other parameters: **high_speed_lr_decay** and **low_speed_lr_decay**

Here is the Basic Coding Logic for Tuning Learning Rate:

```python
if lr > 0.003:
    lr_decay = high_speed_lr_decay
else
    lr_decay = low_speed_lr_decay
lr *= lr_decay
```

high_speed_lr_decay should set lower.

low_speed_lr_decay should set higher.


---------------------------------------------------------------------

**Methodology 4:**

Compare Optimizer: **SGD** vs **Adams**

SGD Parameters setting

- WEIGHT_DECAY
- MOMENTUM
- DAMPENING
- LEARNING RATE

Adams Parameters setting:

- WEIGHT_DECAY
- LEARNING RATE
- PARAMS

-------------------------------------------------------------

**Step Five:**

Compare ResNet 18 with ResNet 34











