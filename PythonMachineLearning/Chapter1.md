Classification is subcategory of supervised learning.
	- Based on past observations.
	- Discrete, unordered values. - understood as group memberships.
	- Email-spam detection - example of binary classification task (only two possible class: spam or not spam)
	- Multi-class classification examples: handwritten character recognition
	- Unable to correctly recognize say digits 0-9 cause they are not part of our training set.


Regression for predicting continuous outcomes

Reinforcement Learning - (something like chess)

In supervised learning, we know the right answer beforehand in the form of reward

In unsupervised learning, we are dealing with unlabeled data or data with unknown structure.

Problem: limited storage space and computational performance of machine learning algorithms.

Solution: Unsupervised dimensionality reduction - common approach in:
	1. Feature preprocessing
	2. Remove noise from data
	3. Compress data onto smaller dimensional subspace
		a. Can also be used to visualize data. 3D to 2D lots

Preprocessing

	- Selected features may be highly correlated and therefore redundant.
	- Solution: Dimensionality reduction!
	- Less storage space required
	- Learning algorithm can run much faster.
	- Must also generalize well to new data.

Predictive Modeling

	- Different cross validation techniques can be used - training datasheet is further divided into training and validation subsets in order to estimate the generalization performance of the model.
	- Cannot assume that software libraries are optimal for our specific problem task. - NEED hyperparameter optimization techniques.
	- Constantly worry about feature scaling and dimensionality

Evaluating Models and Predicting Unseen Data Instances
Make sure to reuse previous procedures such as feature scaling and dimensionality reduction.
