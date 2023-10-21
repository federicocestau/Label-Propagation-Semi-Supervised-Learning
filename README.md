# Label-Propagation-Semi-Supervised-Learning
Label Propagation is a relatively simple algorithm based on the assumption that closer data points have similar class labels. As a result, we can propagate these class labels through dense unlabeled data regions.

What is Semi-Supervised Learning?

Typically, we would use data with a specific target variable (labeled data) to build supervised models (e.g., classification, regression). Alternatively, we would build unsupervised models (e.g., clustering, dimensionality reduction) when we do not have labeled data.
However, sometimes we may find ourselves in situations with a small amount of labeled data and a significant amount of unlabeled data. That’s where Semi-Supervised Learning can help since it incorporates elements from both supervised and unsupervised techniques.

Label Propagation is a relatively simple algorithm based on the assumption that closer data points have similar class labels. As a result, we can propagate these class labels through dense unlabeled data regions.
The algorithm follows an iterative approach, which we can describe as a collection of the following steps:

1 - Create a connected graph by drawing edges (links) between different nodes (data points). Note that creating a fully connected graph on a large dataset may demand a high amount of resources from your machine. Hence, it is often beneficial to limit the number of neighbors that you want to join together
2 - Determine the weights for each edge, where edges for closer data points have larger weights (stronger connection), and edges for faraway points have smaller weights (weaker connection). Larger edge weights allow labels to travel through easier, increasing the probability of propagating the particular label. 
3-  Perform a random walk from each unlabeled point to find a probability distribution of reaching a labeled one. This random walk consists of many iterations and continues until convergence is reached, i.e., all paths have been explored, and probabilities no longer change.

Unlabeled points get their new labels assigned based on the probabilities found by the process above. Note that original labeled points never change since their labels are clamped (fixed).

The Label Propagation algorithm is able to propagate labels outwards through the network, making the best use of the entire data (labeled and unlabeled).

Another critical aspect of the Label Propagation algorithm is that we can view the corresponding probabilities in addition to hard labels after the algorithm has finished running. Hence, we could manually adjust the threshold and re-label some points if we were not happy with the boundary determined by the algorithm.
