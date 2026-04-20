# PRODIGY_GA_04
Image-to-Image Translation using cGAN (Pix2Pix)


Overview

This project implements an Image-to-Image Translation model using a Conditional Generative Adversarial Network (cGAN), specifically the Pix2Pix architecture.

The model learns a mapping from an input image to an output image using paired training data. It is capable of transforming images from one domain to another, such as converting sketches into realistic images or grayscale images into colored ones.

#Key Features
Conditional GAN (cGAN) implementation
Pix2Pix-based architecture
Generator and Discriminator models built using PyTorch
Uses adversarial loss and L1 loss
Supports image-to-image transformation tasks
Google Colab compatible
Concept Explanation
What is Image-to-Image Translation?

Image-to-image translation refers to converting one type of image into another while preserving the underlying structure.

#Examples:

Sketch to real image
Day to night conversion
Map to satellite image
What is cGAN?

A Conditional GAN (cGAN) is a type of GAN where both the generator and discriminator are conditioned on additional information (in this case, an input image).

Instead of generating random outputs, the model generates outputs based on a given input image.

#Pix2Pix Architecture
Generator
Takes an input image
Produces a transformed output image
Uses an encoder-decoder structure (similar to U-Net)
Discriminator (PatchGAN)
Evaluates whether the generated image is real or fake
Looks at small patches instead of the whole image
Working Pipeline
Input image is passed to the Generator
Generator produces a fake (translated) image
Discriminator compares:
Real image pair (input + actual output)
Fake image pair (input + generated output)
Loss is calculated and models are updated
Loss Functions
Adversarial Loss

Ensures generated images look realistic.

L1 Loss

Ensures generated images are close to ground truth.

Final Generator Loss

Generator Loss = Adversarial Loss + L1 Loss

# Google Colab Link 
https://colab.research.google.com/drive/1U25k9_DXSDbxLEf9OEgn-qCI5-vxr3c0?usp=sharing

Usage
# Initialize model
G = Generator()
D = Discriminator()

# Train model
train(G, D)

# Generate output
output = G(input_image)
Example Output

Input Image → Generated Image

The generator produces a transformed version of the input image after training.

Note: In this implementation, dummy data is used, so outputs may appear noisy. Real datasets produce better results.

| Parameter     | Description                     |
| ------------- | ------------------------------- |
| Epochs        | Number of training iterations   |
| Learning Rate | Controls training speed         |
| Batch Size    | Number of samples per iteration |
| Image Size    | Resolution of images            |

#Future Improvements
Train on real datasets (e.g., edges to photos)
Implement full U-Net architecture
Improve image quality with longer training
Add GUI using Streamlit
Save and load trained models
Applications
Image enhancement
Medical imaging
Style transfer
Autonomous driving (scene translation)

#Conclusion

This project demonstrates how conditional GANs can be used for image-to-image translation tasks. Pix2Pix provides a powerful framework for learning mappings between image domains using paired data.
