# A set of experiments regarding diffusion models 

- Trained by finding the reverse markov transitions that maximizes the likelyhood of the training data. 
- We cast Lvlb in terms of KL divergence such that we can calculate it in closed form. 
- The transition distributions in the markov chains are gaussians, where the forward process requires a variance schedule and the reverse process parameters are learned 
- The training objective is to maximize the likelihood of the training data. This is manifested as tuning of the model parameters to minimize the variational upper bound of the negative log likelihood of the data. 
- U-Net is a popular semantic segmentation architecture, whose main idea is that it progressively downsamples and then upsamples its input image, and adds skip connections between layers having the same resolution. These help with gradient flow and avoid introducing a representation bottleneck, unlike usual autoencoders. Based on this, one can view diffusion models as denoising autoencoders without a bottleneck.
- UNET, the network takes two inputs, the noisy images and the variances of their noise components. The latter is required since denoising a signal requires different operations at different levels of noise. We transform the noise variances using sinusoidal embeddings, similarly to positional encodings used both in transformers and NeRF. This helps the network to be highly sensitive to the noise level, which is crucial for good performance. We implement sinusoidal embeddings using a Lambda layer.

## training 
Eurosat dataset, 5 epochs

![org1](https://github.com/fmerizzi/diffusion_models/blob/main/images/2022-11-07%2012:13:17.693488.png)

![org1](https://github.com/fmerizzi/diffusion_models/blob/main/images/2022-11-07%2012:18:35.915267.png)

![org1](https://github.com/fmerizzi/diffusion_models/blob/main/images/2022-11-07%2012:24:11.470212.png)

![org1](https://github.com/fmerizzi/diffusion_models/blob/main/images/2022-11-07%2012:29:42.462231.png)

![org1](https://github.com/fmerizzi/diffusion_models/blob/main/images/2022-11-07%2012:35:02.010591.png)

## originals

![org1](https://github.com/fmerizzi/diffusion_models/blob/main/images/2022-11-07%2013:17:10.714447ORIGINALS.png)

![org1](https://github.com/fmerizzi/diffusion_models/blob/main/images/2022-11-07%2013:17:28.005930ORIGINALS.png)


## generated

![org1](https://github.com/fmerizzi/diffusion_models/blob/main/images/2022-11-07%2012:51:31.763552.png)

![org1](https://github.com/fmerizzi/diffusion_models/blob/main/images/2022-11-07%2012:51:38.357045.png)
