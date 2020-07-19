# GAN-Tricks-2020
My own list of modern GAN tricks I come across


## Training Tricks

### Loss functions
- Use Mescheder's R1/R2 losses for better convergence. Mescheder et al. 2018. [Code](https://github.com/LMescheder/GAN_stability).

### Data augmentation
- Use Differentiable Augmentation to reduce the required training data from ~70k to ~1k-2k, perhaps even the hundreds. Zhao et al. 2020. [Code](https://github.com/mit-han-lab/data-efficient-gans).


## Latent Space Tricks
- SeFa to find meaningful latent spaces in <1 second. [Implemented in Rosinality's StyleGAN2 repo](https://github.com/rosinality/stylegan2-pytorch#closed-form-factorization-httpsarxivorgabs200706600).

