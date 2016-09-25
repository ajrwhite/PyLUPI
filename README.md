# PyLUPI
Add privileged information to image sets for Learning Using Privileged Information (LUPI)

Learning Using Privileged Information (LUPI) is a machine learning paradigm proposed by Vladimir Vapnik. In addition to (x, y) information supplied at the training stage (the standard supervised learning setting), the model is also supplied with additional information (x\*) which is somehow informative about the problem, but will not be available at the test stage.

There are many different suggested methods for harnessing the privileged information. This project is aimed at exploring what I call *Naive LUPI*, where the aim is simply to impute x\* on the test data.

One situation where this may be useful is in image classification, where we are able to indicate a small set of repeating features many times in a single image (e.g. edges, corners), by working with image patches. In this case, our effective training set is much larger than the overall number of images, and working with patches means that the input dimensionality is much lower.

This is similar to the concept of Convolutional Neural Nets (CNN), but this approach differs in two key ways:

1. We supply privileged information as an interim task, or series of interim tasks, to constrain the multi-level model.
2. There is no requirement to use a neural net or back propagation. Instead, the model resembles a "stack" or "ensemble" composed of any combination of traditional machine learning models (logistic regression, decision trees, etc.).

The challenge is identifying a privileged representation which meets the assumptions of *Naive LUPI*. The aim of this program is to demonstrate on the famous MNIST handwriting dataset that such a privileged representation can be generated fairly straightforwardly.
