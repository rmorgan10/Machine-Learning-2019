# Machine Learning #
#### CS 760 ##
#### Instructors: Mark Craven, David Page ###

Some class notes put together by Scott Lucchini, Rob Morgan, and Alex Pizzuto for Sebastian Raschka's Deep Learning Class: STAT 479 at UW-Madison Spring 2019 ([2018 course website](https://www.biostat.wisc.edu/~craven/cs760/index.html)).

There is no required text for the course, but the following books may be useful:

* An Intorduction to Statistical Learning by Garreth James (Uses R not Python)
* The Elements of Statistical Learning: Data Mining, Inference, and Prediction by Trevor Hastie
* Understanding MAchine Leanring
* Machine Learning: A probabilistic perspective by Kevin Murphy

### Machine Learning ###

_Learning Objectives_

1. Understand what a learing system should do
2. Distinguish between supervised, unsupervised, reinforcement, and active learning
3. Employ a broad range of ML algorithms (decision trees, KNN, linear and logistic regression, neural nets, ensemble methods, etc.)
4. Learn the underlying theory (bias-varaince tradeoff, PAC learning, mistake-bound theory)
5. Learn to evaluate and compare learning systems

**_What it means to learn in the context of ML algorithms..._**

The algorithms improve their performance $P$ at some task $T$ with experience $E$. 

*ex: Spam Filtering*: There are multiple ways a filtering algorithm could operate. One is maximizing classification accuracy. However, another way to evaluate the performance is by minimizing misclassification cost. Do this by specifiying the cost of misclassification for all emails, maybe based on the importance of the email, and training the algorithm to minimize the total cost. **Takeaway: Choose the metric the algorithm uses to evaluate it's performance based on specific task it is meant to accomplish.**

*ex: Mammography*: **$T$** classify abnormalities as malignant vs. benign; **$P$** minimize misclassification costs; **$E$** previously encountered patient histories (mammograms + subsequent outcomes). Note that in this case, the cost of classifying a malignant abnormality as benign is probably much worse than that of classifying a benign abnormality as malignant. Adjust the misclassification costs to account for this difference.
 
*ex: Predictive Text Input*: **$T$** Given a partially typed word or sentence, predict what will be typed next; **$P$** minimize total misclassification; **$E$** previously typed words. Here we can just minimize total misclassifications because the cost of disregarding each suggestion is likely the same in the case of an incorrect text prediction. Note in this case, it is probably best to use a training set of words typed by the user instead of a general word bank because each person will have their own style of communicating.  **Takeaway: Select training data that will have the most relevance to the task at hand.**

*ex: Netflix*: **$T$** Given a user and movie predict what the use would rate the movie from 1 star to 5 stars; **$P$** Minimize the difference between predicted and actual ratingl **$E$** Histories of previously rated movies.

*ex: Reinforcement learning to control an autonomous helicopter*: Camera and accelerometers are used to assess the state of the system at a given moment in time. The ML algorithm then evaluates the state of the system and decides what to do next. This process repeats in a loop. **$T$** Measurement of current state of the system; **$P$** Maximize reward (intended trajectory + penalty function); **$E$** state, action, and rewards from previous flights. This training was done by having the algorithm watch an expert performing the tricks.
