# ECE-GY-7123-mini-project    

-------------------------------------------------------------------------------------------------------------

**Introduction**



## **Method Design for Tuning:**

**Step One:**

The **First** parameter we tune is the **Channel Size**:

**Four** Channel Size numbers will be tested in:

32 (Original) --->	64 --->	**42 (Best)**	--->	25

- Plot the 4 graphs (finished)
- Compare the results

---------------------------------------------------------------------

**Step Two:**

The Second parameter we tune is the **Filter Size**:

The two parameters we need to tune is: **Padding** and **Kernel_Size**

Three sets will be tested:

[padding = 1, padding = 1, kernel_size = 3]

**[padding = 2, padding = 2, kernel_size = 5] (Best)**

[padding = 3, padding = 3, kernel_size = 7]   

- Plot the graph (finished)

---------------------------------------------------------------------

**Step Three (important!!!):**

Add a **Learning Rate Decay** parameter for tuning the Learning Rate with two other parameters: **high_speed_lr_decay** and **low_speed_lr_decay**

Here is the Basic Coding Logic for Tuning Learning Rate:

```python
if lr > 0.003:
    lr_decay = high_speed_lr_decay
else:
    lr_decay = low_speed_lr_decay
lr *= lr_decay
```

high_speed_lr_decay should set lower.

low_speed_lr_decay should set higher.


---------------------------------------------------------------------

**Step Four:**

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











