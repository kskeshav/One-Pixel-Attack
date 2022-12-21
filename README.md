# One-Pixel-Attack
## One_Pixel_Attack_for_Fooling_Deep_Neural_Networks
I Implemented the One-Pixel attack teechnique by using an Evolutionary Algorithm called Differential Evolution (DE). We can iteratively generate adversarial images to try to minimize the confidence (probability) of the neural network's classification. First, generate several adversarial samples that modify a random pixel and run the images through the neural network. Next, combine the previous pixels' positions and colors together, generate several more adversarial samples from them, and run the new images through the neural network. If there were pixels that lowered the confidence of the network from the last step, replace them as the current best known solutions. Repeat these steps for a few iterations; then on the last step return the adversarial image that reduced the network's confidence the most. If successful, the confidence would be reduced so much that a new (incorrect) category now has the highest classification confidence.

## Enhanced Resnet
By understanding the One-Pixel attack and how it affects the neural network, it is clear that the
location of the pixel plays a significant role for the image to be perturbed. Performing changes on
the pixel colour and the position can help the neural network to classify the image accurately.
Based on these, we have come up with approaches to make our network less sensitive to these
kinds of attacks. Data augmentation is an optimization mechanism which is used to improve generalization
properties. In this approach, we present simple yet powerful augmentation techniques to alter the
pixel positions. This can be done either by a Flip or a Rotation of the adversarial image.
With a normal Flip or Rotation to the adversarial image, the neural network does not attain
robustness because the One-Pixel attack will still be able to find that particular pixel to attack. By
adding randomness to a prediction function, it transforms the image randomly, ie; random flipping
of the image or rotation by a random degree before feeding it to the Deep Neural Network. This
causes One-Pixel attack to either generate adversarial images in a more significant time or not
generate any adversarial image at all.
In the Random data augmentation approach the noise in the adversarial image still persists even
though the DNN classifies the image accurately. This noise can be eliminated by adding denoising
autoencoding layers before the first layer of the network, to make sure it receives denoised image
instead of a perturbed image. Although one-pixel attack is a black-box attack, adding encoding
and decoding layers to the model eliminates the noise in the pixels, thereby giving a clean image
to the network.
Denoising autoencoders take partially corrupted images whilst training to recover the original
undistorted images. To train an autoencoder to denoise data, it is necessary to perform preliminary
stochastic noise insertion, in order to corrupt the image and use the corrupted image as an input to
the autoencoder, with the only exception that the loss should still be computed for the original image
against the corrupted image.
