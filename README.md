# GAN Tricks 2020
My own list of modern GAN tricks I come across.


## Training Tricks

#### Loss functions
- Use Mescheder's R1/R2 losses for better convergence. Mescheder et al. 2018. [Code](https://github.com/LMescheder/GAN_stability).

#### Activation functions
- Don't use ReLU; it's possibly bad at low-->high dimension transformations [1](https://people.eecs.berkeley.edu/~bmild/fourfeat/)[2](https://vsitzmann.github.io/siren/). Try a fourier activation or smooth activation like Swish (a.k.a. SiLU) instead.

#### Data augmentation
- Use Differentiable Augmentation to reduce the required training data from ~70k to ~1k-2k, perhaps even the hundreds. Zhao et al. 2020. [Code](https://github.com/mit-han-lab/data-efficient-gans).

#### High definition (HD) output
- Use ProgressiveGrowing as your base architecture
- Either that or explore some of the recent AutoEncoder approaches (though these aren't GANs), e.g. ALAE

## Architecture Tricks

#### Style encoding
- AdaIN to modulate style globally across an image [Unofficial PyTorch implementation](https://github.com/naoto0804/pytorch-AdaIN)
- SPADE to modulate style at spatial locations within an image [Official PyTorch](https://github.com/NVlabs/SPADE)


## Latent Space Tricks
- SeFa to find meaningful latent spaces in <1 second. [Implemented in Rosinality's StyleGAN2 repo](https://github.com/rosinality/stylegan2-pytorch#closed-form-factorization-httpsarxivorgabs200706600).

