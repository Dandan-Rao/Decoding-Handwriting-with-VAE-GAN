## Dataset: MNIST hand written digits
## Models: VAE or GANs
## Target:
1. Combine VAE and classification model, can the system identify 10 patent spaces corresponding to each hand-write digit without any human label? If this is the case, then the VAE model has the potential to decode objects without or with little previous human knowledge. For example, we can decode animal language, animal behavior pattern, ancient language, and so on.

2. Use VAE and GANs to generate new pictures of hand-write digits.

<span style="color:#FFA500;font-weight:bold;"> Question:</span>
<span style="color:#FFA500;">  Should I preprocess data by normalize all values to the range 0-1? Or this is not important?</span>
> Yes, this will get the training process more stable. 

<span style="color:#FFA500;">  How to detect clusters in density-based distribution where clusters have dense cores and fuzzy/overlapping edges, and we don't know the number of clusters beforehand?</span>
> HDBSCAN model

<span style="color:#FFA500;"> What is KL Divergence loss?</span>
> VAE tries to learn a compressed representation of data which follows normal distribution. We can achieve this by defining KL Divergence loss. The loss encourages the learned distribution to stay close to standard normal.
Without KL loss, the latent space will become irregular or fragmented. 

<span style="color:#FFA500;"> Should the encoder and decoder in VAE be designed as mirror images?</span>
> Not necessary, but usually do. 
Use mirror design maintain consistent transformation capacity in both directions;
It also helps prevent one side overpowers the other.
And it is easy for implementation.

<span style="color:#FFA500;"> How and when should we use <span style="color:#FFA500;font-weight:bold;">activation layer, batch normalization layer, dropout layer, and pooling layer</span>?</span>
> 1. Applying activation function after a BatchNormalization layer is a common practice:
        Conv2D → BatchNormalization → Activation (e.g., LeakyReLU)
> 2. LeakyReLU often improves generation quality as compared to ReLU.
> 3. Dropout layer can be added in the dense or conv blocks, after the activation layer.
> 4. GANs rarely apply pooling layers. Instead use strides = 2 to increase/decrease layer size. 
