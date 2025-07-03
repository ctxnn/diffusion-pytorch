diffusion models are the current state of the art image genration models 

it consists of two processes 
- backward process 
- forward process 

in layman terms, the **forward process** adds noice in the original data and a neural network leanrs to denoise the image, that is the **backward process**

![cat](img/cat_diffusion.png)

if want to see visualize it in our minds imagine there is a _image_ space of 1 million pixel, and the space is mostly empty, but in that space there are clusters of good images that mean something (like cats, dogs whatever) 

diffusion models learns to find its way from a random sample in the image space, to one of these clusters 

