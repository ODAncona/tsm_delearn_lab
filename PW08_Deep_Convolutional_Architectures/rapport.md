# Practical Work 8

## Exercice 1

The objective was to explore the performance of a deep VGGNet-inspired CNN on the CIFAR10 dataset.

This dataset includes images of 10 different object categories, each of size 32x32 pixels. The model was structured using the following architecture:

```txt
[
    [Conv2D → relu → BN]*3 
    → MaxPool2D 
    → Dropout
]*4 
→ Flatten 
→ Dense 
→ Dropout
→ Out
```

The model was trained using the Adam optimizer with a learning rate of 0.001. Training was managed with PyTorch Lightning, which facilitated easier scalability and cleaner code.

Logging and Monitoring: Training progress was monitored using TensorBoard, which logged metrics such as training and validation loss. Additionally, a confusion matrix and classification report were generated at the end of testing to evaluate model performance across different classes

## Exercice 2

The network use residual inception blocks, which are convolutional layers with varying kernel sizes operating at the same level within the network. These modules allow the network to capture information at multiple scales. Furthermore, residual connections are used and 1x1 convolutions are employed to reduce the number of parameters.

**Comparison with ResNet and GoogleNet**:

- **ResNet (Residual Network)**: Introduced by He et al., ResNet features residual connections which are essentially shortcuts that skip one or more layers. These connections help in training very deep networks by addressing the vanishing gradient problem, making it easier for the network to learn identity functions. Inception-v4 incorporates some of these ideas by blending Inception architecture with residual connections, leading to faster training times and potentially better performance.
- **GoogleNet (Inception-v1)**: The original GoogleNet introduced the concept of Inception modules, which use filters of different sizes at the same stage of the network to capture details at various scales. Over iterations, this architecture was refined into Inception-v3 and Inception-v4, which simplified and optimized the configurations for better performance and lower computational costs.

3. **Key Developments in Inception-v4**:
   - Inception-v4 has a more uniform design across its modules, reducing complexity and focusing on optimizing depth and width within the network.
   - The integration of residual connections in variants like Inception-ResNet has shown that these can accelerate the training process and slightly improve performance over networks without these connections.

In essence, Inception-v4 builds on the strengths of its predecessors by integrating successful elements from other architectures like ResNet, simplifying its structure, and optimizing for computational efficiency and performance in large-scale image recognition tasks.
