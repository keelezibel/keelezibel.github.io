---
layout: single
title: Digit Recogniser using Keras
categories: Coding
tags: 
- keras
- deep learning
- image recognition
header:
  overlay_image: /assets/posts/2017-07-23-DigitRecogniser/digits.png
---

This post is based on a tutorial: Optimizing Neural Networks using Keras (with Image recognition case study) from [Analytics Vidhya](https://www.analyticsvidhya.com/blog/2016/10/tutorial-optimizing-neural-networks-using-keras-with-image-recognition-case-study/). <br />
<br />

# Background of Keras
Keras is a deep learning high level library that does all the heavy lifting with an easier interface to Tensorflow or Theano as its backend. It 
is used to build neural network models. Keras is compatible with Python 2.7 and 3.5. <br />

Limitations of Keras: <br />
- Dependent on low level libraries like Theano/Tensorflow
- Less flexible, since it completely abstracts the low level languages
- Relatively new

<br />

# When to use Neural Networks
I like how the author mentioned that not every problem requires a Neural Network model to solve. Perhaps traditional algorithms can already solve
the problem. Simplicity is more important than complexity. And there is a list of steps to adopt when using Neural Network. <br />

- Check if it is a problem where Neural Network gives you uplift over traditional algorithms (refer to the checklist in the section above)
- Do a survey of which Neural Network architecture is most suitable for the required problem
- Define Neural Network architecture through whichever language / library you choose.
- Convert data to right format and divide it in batches
- Pre-process the data according to your needs
- Augment Data to increase size and make better trained models
- Feed batches to Neural Network
- Train and monitor changes in training and validation data sets
- Test your model, and save it for future use

<br />

# Implementation
The code (notebook) and data can be found [here](https://github.com/keelezibel/DigitRecogniser). Clone the repo, unzip the Train folder
and you are good to go.<br />

There are seven slightly different models implemented. 
1. 1 layer with 50 neurons, 5 epochs (Multi-layer perceptron MLP)
2. 1 layer with 500 neurons, 5 epochs (MLP)
3. 5 hidden layers with 50 neurons, 5 epochs (MLP)
4. 5 hidden layers with 50 neurons, 5 epochs with dropout (MLP)
5. 5 hidden layers with 50 neurons, 50 epochs with dropout (MLP)
6. 5 hidden layers with 500 neurons, 25 epochs with dropout (MLP)
7. 5 epochs (Convolutional Neural Network)

<br />

# Result
I submitted the CNN results and viola! <br />
{% include figure image_path="/assets/posts/2017-07-23-DigitRecogniser/leaderboard.png" caption="Leaderboard result using CNN" %} 

<br />

# Parameters for NN
The author highlighted some parameters to tune for NN:
- Type of architecture
- Number of Layers
- Number of Neurons in a layer
- Regularization parameters
- Learning Rate
- Type of optimization / backpropagation technique to use
- Dropout rate
- Weight sharing

<br />

# Resources
- [List of Keras resources](https://github.com/fchollet/keras-resources)
- [Fundamentals of Deep Learning – Starting with Artificial Neural Network](https://www.analyticsvidhya.com/blog/2016/03/introduction-deep-learning-fundamentals-neural-networks/)
- [Understanding and coding Neural Networks From Scratch in Python and R](https://www.analyticsvidhya.com/blog/2017/05/neural-network-from-scratch-in-python-and-r/)
- [CS231n Convolutional Neural Networks for Visual Recognition](http://cs231n.github.io/neural-networks-3/#baby)
- [The Evolution and Core Concepts of Deep Learning & Neural Networks](https://www.analyticsvidhya.com/blog/2016/08/evolution-core-concepts-deep-learning-neural-networks/)
- [Deep Learning for Computer Vision – Introduction to Convolution Neural Networks](https://www.analyticsvidhya.com/blog/2016/04/deep-learning-computer-vision-introduction-convolution-neural-networks/)

<br />

# Conclusion
This tutorial is really helpful as a start to build Neural Networks in Keras. There is so much more things to learn in this area.