diffusion models are the current state of the art image genration models 

it consists of two processes 
- backward process 
- forward process 

in layman terms, the **forward process** adds noice in the original data and a neural network leanrs to denoise the image, that is the **backward process**

![cat](img/cat_diffusion.png)

if want to see visualize it in our minds imagine there is a _image_ space of 1 million pixel, and the space is mostly empty, but in that space there are clusters of good images that mean something (like cats, dogs whatever) 

diffusion models learns to find its way from a random sample in the image space, to one of these clusters 

**diffusion maths cheatsheet (that is used while programming)** 

1. closed form noise sampling 

$$q(x_t|x_0) = N(x_t; \sqrt{\bar{\alpha}}x_0,(1-\sqrt{\bar{\alpha}})I)$$

where $\alpha_t$ = 1 - $\beta_t$ , $\bar{\alpha_t} = \prod_{s=1}^t\alpha_s$, $\beta$ is the noise

2. noise prediction loss 

$$L = E_{x_0, \epsilon, t} \left[ \| \epsilon - \epsilon_\theta(x_t, t) \|^2 \right]$$

3. sampling step ( ddpm )

![Sampling Step](https://latex.codecogs.com/svg.latex?%5Ccolor%7Bwhite%7D%20x_{t-1}%20%3D%20%5Cfrac%7B1%7D%7B%5Csqrt%7B%5Calpha_t%7D%7D%20%5Cleft(%20x_t%20-%20%5Cfrac%7B%5Cbeta_t%7D%7B%5Csqrt%7B1%20-%20%5Cbar%7B%5Calpha%7D_t%7D%7D%20%5Cepsilon_%5Ctheta(x_t,%20t)%20%5Cright)%20%2B%20%5Csigma_t%20z)

