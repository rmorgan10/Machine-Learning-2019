# Machine Learning 

## Jan. 28, 2019

### Machine Learning Tasks and Feature Space Representations

Each example or instance of a dataset is represented by a feature vector, where each entry in the feature vector describes a different property of the example. For feature vectors with length $d$, we can think of the dataset as being expressable in a $d$-dimensional space.

Features exist as a few different types:

- Nominal / Catagorical: Color, Boolean, ...
- Ordinal: There is an order to the feature values (small, medium, large)
- Numeric: Continuous values like real numbers
- Hierarchial: possible values are partially ordered in an ISA hierarchy


### The Supervised Learning Task

Problem setting:

- Set of possible instances: $X$
- Unknown target function: $f:X\rightarrow Y$
- Set of models (a.k.a. hypotheses): $H=\{ h | h: X\rightarrow Y\}$

When the class labels are discrete, we call this task classification. If the class labels are continuous, we call this task regression. In some cases, class labels might be structured objects such as sequences of labels and words.

Within supervised learning there are different styles of learning. One discrepancy is _Batch_ vs _Online_ learning. In the batch case, we give our algorithm all the training data at once and in the online case we introduce more data to our algorithm as time progresses.

We often assume that training instances are independent and identically distributed (i.i.d.), meaning they are sampled independently from the same unknown distribution. Later on, we'll discuss cases where this assumption fails. Some cases of this are:

- Cases where sets of instances have dependencies such as aamples from the same image
- Time Series
- Active Learning
- Changes in the target function over time

### The Unsupervised Learning Task

The goal of this task is to find interesting regularities or irregularities in the feature space without class labels. Some examples of this task are clustering, anomaly detection, and dimensionality reduction.

_Clustering_: Organize the instances based on a distance metric in the feature space. The objective is to find groups such that the instances in each group are similar to each other and dissimilar to the instances in the other groups.

_Anomaly Detection_: Given a set of training instances, determine whether an unseen instance is normal or an outlier.

_Dimensionality Reduction_: The model represents each feature as a lower-dimensional vector while still preserving key relationships between the instances.


### Generalization

We want the model that we train to be able to make accurate predictions on unseen data. Keep this in mind for now and we will touch on ways to approach this task later on.