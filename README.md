# Development-of-an-Adaptable-Deep-Learning-Model-for-Artistic-Style-Transfer


# Development of an Adaptable Deep Learning Model for Artistic Style Transfer

In this article, a lightweight PyTorch implementation of neural style transfer was built, and learn how to transfer popular art styles onto any image was described.


## Overview

Neural style transfer is a cool technique where we can mix two pictures – one with the stuff you want to show (content) and another with a cool artistic vibe (style).

The result is a new picture that has your content but looks like it was painted in the style you picked. It's like giving your photos a special artistic touch. This is part of a bigger field called non-photorealistic rendering, which is all about making images look more artistic and less like regular photos.
## Working methodology

1. **Network Utilization**: We use a pre-trained VGG19 convolutional neural network to capture image details, where early layers focus on 'style' elements like colors, and later layers depict more intricate 'content' details such as eyes and ears of a cat.

2. **Activation Extraction**: Inputting the content image into VGG19 yields network activations at conv4, while the style image activations are obtained at earlier to middle convolution layers (conv1, conv2, conv3, conv4, conv5).

3. **Gram Matrix Encoding**: Activations are transformed into Gram matrix representation, serving as a descriptor for the image's 'style.'

4. **Synthesis Objective**: Our aim is to generate an output image merging the content of one image with the style of another.

5. **Loss Calculations**:
   - *Content Loss*: Quantified by the L2 distance between the content and generated images.
   - *Style Loss*: Computed as the sum of L2 distances between Gram matrices from different VGG19 layers for content and style images.
   - *Total Variation Loss*: Enhances spatial coherence and reduces noise in the generated image.
   - *Total Loss*: The cumulative sum of the above losses, each multiplied by its respective weight.

6. **Optimization Technique**: We employ the L-BFGS iterative optimization method to progressively minimize these losses, achieving the desired synthesized results.



## Dependencies

* Python 3.9+

* Framework: PyTorch

* Libraries: os, numpy, cv2, matplotlib, torchvision
## Output


<img width="1114" alt="NST_img" src="https://github.com/tirtharajpal/-Development-of-an-Adaptable-Deep-Learning-Model-for-Artistic-Style-Transfer/assets/150589994/1b72e209-4835-44b1-8f53-2b2e54d15ec2">
