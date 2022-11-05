# A set of experiments regarding diffusion models 

- Trained by finding the reverse markov transitions that maximizes the likelyhood of the training data. 
- We cast Lvlb in terms of KL divergence such that we can calculate it in closed form. 
- The transition distributions in the markov chains are gaussians, where the forward process requires a variance schedule and the reverse process parameters are learned 
- The training objective is to maximize the likelihood of the training data. This is manifested as tuning of the model parameters to minimize the variational upper bound of the negative log likelihood of the data. 
