# gans-deformations-2
Second part of the GANs project (see [here](https://github.com/Robbberto/gans-deformations) for the first part).

The work of this repository was done by Roberto Ceraolo (me) and Roberto Minini for our semester project in collaboration with the Laboratory of the Physics of Biological Systems at EPFL.

We were followed by prof. Sahand Rahi and Corinne Jones.

This project is the second part of project that began during the Machine Learning course in the 2022-2023 Autumn semester.
In this second part, the aim of the work was still to obtain realistic deformations of images of C. Elegans. Nevertheless, this time, the images were not of neural activity but instead of the full shape of the body. The main reference for this work is the paper Dimensionality and Dynamics in the Behavior of C. elegans (G. J. Stephens et al., 2008). The authors studied and created a quantitative model to describe the shape of C. Elegans. Indeed, considering the worm’s curvature, they showed that the space of postures is low-dimensional and can be described by projecting on 4 principal components. The authors of the paper kindly provided us with a sample of the dataset they used for their publication. Our goal was to generate, through GANs [1], realistic deformations of their images. This way, in case we reached good results, we could use this architecture in applications in which data is not easy to retrieve.
We also re-built from scratch their quantitative methods to visualize the principal components of the postures, very closely to how as they are described in the paper. This allowed us to make comparisons between the distributions of generated and real images. Our code is available on request.
The logic we followed is the same as in the previous part of the project: starting by generating synthetic data resembling the real images, check the behavior of the GAN on them. Then, move to applying the GAN directly on real images. More or less halfway thorugh this project, we decided to change architecture of the GAN, from the one described in the previous report, to one based on StyleGAN2-ADA [4], which is one of the most recent and sophisticated architectures for image and video generations. The use of this different GAN brought to extremely better results with respect to the previous ones. While the previous one was struggling even with synthetic data, the new one is able to generate visually realistic deformations of the real C. Elegans images. They are hardly distinguishable from the real data by humans. When applying the quantitative procedure to compare the principal components of the matrix identifying the shapes, it seems that it still has some issues in replicating the distribution of shapes. Indeed, looking at the 2D graphs in 10 it seems that a part of the distribution is missing. Future work may address this issue and investigate what the missing parts have in common. When using the StyleGAN2-ADA, we checked how the quality and the distributions of images changed when training the GAN with sets of different sizes. It wasn’t found a clear pattern, e.g., better results when increasing or decreasing the train set size. Indeed the sizes tested were 7200 (full dataset we were given), 4000, 2000
and 500 and the best results were given when training with 4k images.



