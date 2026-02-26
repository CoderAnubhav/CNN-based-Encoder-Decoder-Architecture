📰 CNN-Based Multimodal Image Captioning

This project implements a CNN-only multimodal encoder–decoder architecture for news image caption generation as an efficient alternative to traditional CNN+LSTM and Transformer-based models.

Conventional LSTM-based approaches generate captions sequentially, which slows down training, weakens long-range dependencies, and can suffer from vanishing gradient issues. Transformer models address sequential limitations using self-attention, defined as:

<br>
Attention(Q, K, V) = softmax(QKᵀ / √dk) V

<br>

While powerful, self-attention introduces quadratic time complexity O(n²) with respect to sequence length, making Transformers computationally expensive and less suitable for real-time or edge deployment.

To overcome these challenges, this project:

Uses a CNN encoder to extract global image features such as scene understanding and object representations.

Fuses image embeddings with contextual embeddings for multimodal caption generation.

Implements a CNN-based decoder that performs fully parallel sequence modeling instead of sequential recurrence.

Employs residual connections between convolutional blocks to improve gradient flow and mitigate vanishing gradient problems.

Trains the model end-to-end using cross-entropy loss.

The resulting architecture reduces computational overhead, enables parallel computation, and remains suitable for low-latency and resource-constrained environments.