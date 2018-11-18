# DEEP LEARNING

## Overview🌀

### Deep learning

> Yann Lecun, Yoshua Bengio, Geoffrey Hinton. Nature, 2015

> intricate, very complicated or detailed;  resisted, try to prevent by action or argument; carve, cut \(a hard material\) in order to produce an object, design, or inscription; illumination, light; derivative / partial derivative , in mathematics, it is a way to show rate of change; discrimination, the unjust or prejudicial treatment of different categories of people, especially on the grounds of race, age, or sex./ recognition and understanding of the difference between one thing and another; invariant, never changing; irrelevant, not connected with or relevant to something.; conventionally, in a way that is based on what is traditionally done or believed.; forsaken, abandoned or deserted.; configuration, an arrangement of parts or elements in a particular form, figure, or combination.; saddle point; remainder, a part, number, or quantity that is left over.; hierarchy, a system in which members of an organization or society are ranked according to relative status or authority.;

Representation learning is a set of methods that allows a machine to be fed with raw data and to automatically discover the representations needed for detection or classification.

The most common form of ML is **supervised learning**. The adjustable parameters in the machine are often called **weights**, which are real numbers that can be seen as knobs that define the input-output function of the machine. To properly adjust the weight vector, the algorithm computes a **gradient vector** for each weight, indicates by what amount the error would increase or decrease if the weight were increased by a tiny amount.

After training, the performance of the system is measured on a different set of examples called a **test set**. This serves to test the generalization ability of the machine, its ability to produce sensible answers on new inputs that it has never seen during training.

Many current practical applications of ML use **linear classifier** on top of hand-engineered features.

The network used for object recognition or natural language processing contain tens or hundreds of thousands of units. A deep-learning architecture is a multilayer stack of simple modules.

The backpropagation procedure to compute the gradient of an objective function with respect to the weights of a multilayer stack of modules is nothing more than a practical application of the chain rule for derivatives. The key insight is: the derivative of the objective with respect to the input of a module can be computed by working backwards from the gradient with respect to the output of that module.

Many applications of deep learning use **feedforward neural network architectures**. which the connections between the nodes do not form a cycle, it is different from recurrent neural networks. At present, the most popular non-linear function is the rectified linear unit \(ReLU\). The **hidden layers** can be seen as distorting the input in a non-linear way so that categories become linearly separable by the last layer.

For smaller data sets, unsupervised pre-training helps to prevent overfitting, leading to significantly better generalization when the number of labelled examples is small. Once deep learning had been rehabilitated, it turned out that the pre-training stage was only needed for small data sets.

#### **Convolutional neural networks**

**Convolutional neural networks \(ConvNets\)** are designed to process data that come in the form of multiple arrays. **There are four key ideas behind ConvNets** that take advantage of the properties of natural signals: **local connections, shared weights, pooling and the use of many layers**. Although the role of the convolutional layer is to detect local conjunctions of features from the previous layer, the role of the pooling layer is to merge semantically similar features into one. Since the early 2000s, convnets have been applied with great success to the **detection, segmentation and recognition** of objects and regions in image. **From image to text, CNN+RNN**. 

A **deep-learning architecture** is a multilayer stack of simple modules, most of which compute non-linear input-output mappings. Each module in the stack transforms its input to increase both the selectivity and the invariance of the representation.

#### Image understanding with deep convolutional networks

#### Distributed representations and language processing

#### The future of deep learning

Unsupervised learning - It is an far more important in the longer term even it is not widely used today. Creatures in this world are learning largely by unsupervised.

Human vision - We expect much of the future progress in vision to come from systems that are trained end-to-end and combine ConvNets with RNNs that use RL to decide where to look.

Natural Language understanding - We expect systems that use RNNs to understand sentences or whole documents.

















## NaN

