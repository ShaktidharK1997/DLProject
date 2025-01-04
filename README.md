# Modified ResNet for CIFAR-10 Classification

## Project Overview
This project implements a modified ResNet architecture optimized for the CIFAR-10 dataset, with a focus on achieving high accuracy while maintaining a parameter count below 5 million. Our implementation achieves 93.67% accuracy on the test set with only 4,697,742 parameters.

## Key Features
- Custom ResNet architecture with optimized depth and width
- Advanced training strategies including Lookahead Optimizer and CutMix augmentation
- Squeeze-and-Excitation blocks for enhanced feature representation
- Comprehensive data augmentation pipeline
- Cosine Annealing learning rate scheduling

## Architecture Details
- Initial convolutional layer with 3x3 kernel
- Three groups of residual layers (depths: 4-4-3)
- Squeeze-and-Excitation blocks for feature recalibration
- Adaptive Average Pooling before classification
- Channel expansion in powers of two starting from 64 channels

## Training Configuration
- Learning Rate: 0.1 with Cosine Annealing scheduling
- Optimizer: SGD with Lookahead mechanism
- Momentum: 0.9
- Weight Decay: 0.0005
- Data Augmentation: Random Horizontal Flip, Random Crop, CutMix
- Epochs: 200 with Early Stopping

## Results
- Final Test Accuracy: 93.67%
- Average Test Loss: 0.2790
- Total Parameters: 4,697,742

## Data Preprocessing
- Normalization Parameters:
  - Mean: [0.4914, 0.4822, 0.4465]
  - Std: [0.2023, 0.1994, 0.2010]
- Augmentation: Random horizontal flipping and 32x32 random crops with 4-pixel padding

## Requirements
- PyTorch
- torchvision
- numpy
- matplotlib (for visualization)

## References
1. M. R. Zhang, J. Lucas, G. Hinton, and J. Ba, "Lookahead Optimizer: k steps forward, 1 step back"
2. Jie Hu, Li Shen, Samuel Albanie, Gang Sun, Enhua Wu, "Squeeze-and-Excitation Networks"
3. K. Liu, "pytorch-cifar", GitHub repository, 2023
