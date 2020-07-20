# GAN Tricks 2020
My own list of modern GAN tricks I come across.


## Training Tricks

#### Loss functions
- Use Mescheder's R1/R2 losses for better convergence. Mescheder et al. 2018. [Code](https://github.com/LMescheder/GAN_stability).

#### Activation functions
- Don't use ReLU; it's possibly bad at low-->high dimension transformations [[1](https://people.eecs.berkeley.edu/~bmild/fourfeat/)][[2](https://vsitzmann.github.io/siren/)]. Try a fourier activation or smooth activation like Swish (a.k.a. SiLU) instead.

#### Optimization
- Train generators and discriminators with different learning rates

#### Data augmentation
- Use Differentiable Augmentation to reduce the required training data from ~70k to ~1k-2k, perhaps even the hundreds. Zhao et al. 2020. [Code](https://github.com/mit-han-lab/data-efficient-gans).

#### Output Quality

- For HD resolution, use ProgressiveGrowing as your base architecture. Either that or explore some of the recent AutoEncoder approaches (though these aren't GANs), e.g. ALAE
- If you can afford it, add some self-attention like stated [here](https://github.com/lucidrains/stylegan2-pytorch#attention). Self-Attention GAN is originally [here](https://github.com/heykeetae/Self-Attention-GAN).

## Architecture Tricks
- Throw some linear layers between the latent space and convolution layers. According to the StyleGAN paper, it helps disentangle the latent space.

#### Style encoding
- AdaIN to modulate style globally across an image [Unofficial PyTorch implementation](https://github.com/naoto0804/pytorch-AdaIN)
- SPADE to modulate style at spatial locations within an image [Official PyTorch](https://github.com/NVlabs/SPADE)


## Latent Space Tricks
- SeFa to find meaningful latent spaces in <1 second. [Implemented in Rosinality's StyleGAN2 repo](https://github.com/rosinality/stylegan2-pytorch#closed-form-factorization-httpsarxivorgabs200706600).


# Other Resources
- 2016 - [Soumith Chintala: ganhacks](https://github.com/soumith/ganhacks)
- 2019 - [Marco Pasini: 10 Lessons I Learned Training GANs for one Year
](https://towardsdatascience.com/10-lessons-i-learned-training-generative-adversarial-networks-gans-for-a-year-c9071159628)
