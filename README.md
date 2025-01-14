# Comdefend_tensorflow

## Environment
- tensorflow >= 1.1
- python3

## Code
The code has two parts. The first part we implement the work of CVPR2019 (ComDefend: An Efficient Image Compression Model to Defend Adversarial Examples [3]) by using tensorflow. The second part we implement the network by adding residual blocks.

## Our idea
We mainly focus how data compression works in adversarial defense. Dziugaite et al [1] use JPEG compression method to prevent FGSM attacks. Hendrycks et al [2] use PCA to detect natural images from adversarial examples. Jia et al [3] use autoencoder network to purify adversarial examples. These methods aim at extracting main useful information of the adversarial attacks and in a result they can eliminate noisy information.

The image compression method has its intrinsic problem that if the compression rate is big the classification accuracy rate may decrease, while a small compression rate may not remove enough noisy disturbance. So we intuitively think that we can add residual block in the encoding stage so we may reserve both raw input’s high-level information and reasonable low compression rate. What’s more, Resnet can help smooth the gradients in the training progress. which may be useful to eliminate adversarial noise added by hand.

<image width='500px' src='https://ws3.sinaimg.cn/large/006tNc79ly1g2yn3sesj4j31e80iktdn.jpg'>

## Result

<image width='500px' src='https://ws4.sinaimg.cn/large/006tNc79ly1g2yn57d9a5j30ly0fidhh.jpg'>
<image width='500px' src='https://ws2.sinaimg.cn/large/006tNc79ly1g2yn67xn4vj30mu0g3tcs.jpg'>
<image width='500px' src='https://ws1.sinaimg.cn/large/006tNc79ly1g2yn6l086lj30mu0g377v.jpg'>

## Acknowledge

With @yeoyi519 's help.

 ## Reference
[1] Das, N.; Shanbhogue, M.; Chen, S.T.; Hohman, F.; Chen, L.; Kounavis, M.E.; Chau, D.H. Keeping the bad guys out: Protecting and vaccinating deep learning with jpeg compression. arXiv 2017, arXiv:1705.02900

[2] Dan Hendrycks and Kevin Gimpel. 2017. Early Methods for Detecting Adversarial Images. In International Conference on Learning Representations (Workshop Track).

[3] X. Jia, X. Wei, X. Cao, and H. Foroosh, “ComDefend: An Efficient Image Compression Model to Defend Adversarial Examples,” arXiv:1811.12673 [cs], Nov. 2018.
