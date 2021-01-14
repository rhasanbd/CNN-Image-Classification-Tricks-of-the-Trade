# CNN-Image Classification-Tricks of the Trade

In this set of notebooks, we perform a set of experiments to train a simple 4-hidden layer Convolutional Neural Network (CNN) architecture for performing image classification **optimally** on the MNIST Fashion dataset.

More specifically, we investigate the impact of various regularization techniques. 

### CNN Architecture
We build a 4-hidden layer CNN model:
- 3 Convolutional layers and 1 Fully-Connected (dense) layer


## Regularization
To reduce **overfitting**, following regularization techniques are used:
- Weight decay (le regularization)
- Data augmentation
- Dropout


## Data Augmentation
Refer to the following notebook to learn how to use Keras' ImageDataGenerator class for performing data augmentation. https://github.com/rhasanbd/Data-Augmentation/blob/main/Keras-Data%20Augmentation.ipynb

## Overcome Vanishing Gradient Problem
We use Batch Normalization (BN) to overcome the vanishing gradient problem. In one experiment (experiment no. 2) we don't apply BN to observe whether it degrades the learning.

## Experiments
We performed the following 9 experiments.

1. No Regularization
2. No Regularization & No BN
3. Weight Decay 0.01
4. Weight Decay 0.001
5. Horizontal Flip
6. Horizontal Flip + Zoom
7. Horizontal Flip + Random Crop
8. Horizontal Flip + Zoom + Rotation + Random Crop
9. Dropout


## Key Observation

Based on the results obtained from the experiments, we make following observations.
- The shallow CNN can be trained optimally without Batch Normalization. The ReLU activation and He initiazer are good enough to ensure the flow of healthy loss gradients.

- The best technique to combat overfitting is dropout.

- The effect of data augmentation varies depending on how it is applied. For example, experiment 8 has the worst performance (test accuracy) because of aggressive data augmentation policy. However, it has nearly 0 overfitting.

- Data augmentation is a very useful regularization technique, but it needs to applied judiciously. 

<img src="https://cse.unl.edu/~hasan/Pics/CNN-ImageClassification-Results-Comparison.png" width=800, height=400>

See the learning curves of the experiments <a href="https://cse.unl.edu/~hasan/Pics/CNN-ImageClassification-Results.pdf">here</a>.


